# Fault Tolerance Semantics
- Every streaming source is assumed to have offsets (similar to Kafka offsets, or Kinesis sequence numbers) to track the read position in the stream. The engine uses checkpointing and write-ahead logs to record the offset range of the data being processed in *each trigger*.

# API using Datasets and DataFrames
## Creating streaming DataFrames and streaming Datasets
#### Input Sources
- Socket source: be used only for testing as this does not provide end-to-end fault-tolerance guarantees.
- df.printSchema()

### Schema inference and partition of streaming DataFrames/Datasets

## Operations on streaming DataFrames/Datasets

### Basic Operations - Selection, Projection, Aggregation
 `df.isStreaming()`

### Window Operations on Event Time

	`words = ...  # streaming DataFrame of schema { timestamp: Timestamp, word: String }

	# Group the data by window and word and compute the count of each group
	windowedCounts = words.groupBy(
	    window(words.timestamp, "10 minutes", "5 minutes"),
	    words.word
	).count()`


However, to run this query for days, it’s necessary for the system to bound the amount of intermediate in-memory state it accumulates. This means the system needs to know when an old aggregate can be dropped from the in-memory state because the application is not going to receive late data for that aggregate any more. To enable this, in Spark 2.1, we have introduced watermarking, which lets the engine automatically track the current event time in the data and attempt to clean up old state accordingly. You can define the watermark of a query by specifying the event time column and the threshold on how late the data is expected to be in terms of event time. For a specific window ending at time T, the engine will maintain state and allow late data to update the state until (`*max event time seen by the engine* - late threshold > T)`. (filtered_event > event time lớn nhất xem được - interval)

Since, it is still ahead of the watermark 12:04 in the trigger, the engine still maintains the intermediate counts as state and correctly updates the counts of the related windows. However, when the watermark is updated to 12:11, the intermediate state for window (12:00 - 12:10) is cleared, and all subsequent data (e.g. (12:04, donkey)) is considered “too late” and therefore ignored. Note that after every trigger, the updated counts (i.e. purple rows) are written to sink as the trigger output, as dictated by the Update mode.

However, the partial counts are not updated to the Result Table and not written to sink. The engine waits for “10 mins” for late date to be counted, then drops intermediate state of a window < watermark, and appends the final counts to the Result Table/sink. For example, the final counts of window 12:00 - 12:10 is appended to the Result Table only after the watermark is updated to 12:11. --> Trên event time > watermark --> drop

? Ví dụ, interval = 10min, now=12:10, last_event_time_receive=12:01 ==> new_event_time_receive=11:55 có được nhận không hay bị drop???

##### Conditions for watermarking to clean aggreation state
- Output mode must be Append or Update
- The aggregation must have either the event-time column, or a window on the event-time column.
- withWatermark must be called on the same column as the timestamp column used in the aggregate.
- withWatermark must be called before the aggregation for the watermark details to be used

##### Semantic Guarantees of Aggregation with Watermarking
A watermark delay (set with withWatermark) of “2 hours” guarantees that the engine will never drop any data that is less than 2 hours delayed. In other words, any data less than 2 hours behind (in terms of event-time) the latest data processed till then is guaranteed to be aggregated.

However, the guarantee is strict only in one direction. Data delayed by more than 2 hours is not guaranteed to be dropped; it may or may not get aggregated. More delayed is the data, less likely is the engine going to process it.

### Join Operations
`Structured Streaming supports joining a streaming Dataset/DataFrame with a static Dataset/DataFrame as well as another streaming Dataset/DataFrame.`

### Streaming Deduplication
You can deduplicate records in data streams using a unique identifier in the events. The query will store the necessary amount of data from previous records such that it can filter duplicate records. Similar to aggregations, you can use deduplication with or without watermarking.

### Policy for handling multiple watermark

### Arbitrary Stateful Operations

### Unsupported Operations

## Starting Streaming Queries

#### Output modes
- Append(default): where only the new rows added to the Result Table since the last trigger will be outputted to the sink. This is supported for only those queries where rows added to the Result Table is never going to change. Hence, this mode guarantees that each row will be output only once (assuming fault-tolerant sink). For example, queries with only select, where, map, flatMap, filter, join, etc. will support Append mode
- Complete: The whole Result Table will be outputted to the sink after every trigger. This is supported for aggregation queries.
- Update (available since Spark 2.1.1)

#### Output Sinks

##### Using Foreach and ForeachBatch
- The foreach and foreachBatch operations allow you to apply arbitrary operations and writing logic on the output of a streaming query. They have slightly different use cases - while foreach allows custom write logic on every row, foreachBatch allows arbitrary operations and custom logic on the output of each micro-batch. Let’s understand their usages in more detail.
- With foreachBatch, you can do the following.

Reuse existing batch data sources - For many storage systems, there may not be a streaming sink available yet, but there may already exist a data writer for batch queries. Using foreachBatch, you can use the batch data writers on the output of each micro-batch.
Write to multiple locations - If you want to write the output of a streaming query to multiple locations, then you can simply write the output DataFrame/Dataset multiple times. However, each attempt to write can cause the output data to be recomputed (including possible re-reading of the input data). To avoid recomputations, you should cache the output DataFrame/Dataset, write it to multiple locations, and then uncache it. Here is an outlin

Note:

By default, foreachBatch provides only at-least-once write guarantees. However, you can use the batchId provided to the function as way to deduplicate the output and get an exactly-once guarantee.
foreachBatch does not work with the continuous processing mode as it fundamentally relies on the micro-batch execution of a streaming query. If you write data in the continuous mode, use foreach instead.

#### Triggers

## Managing Streaming Queries
`You can start any number of queries in a single SparkSession. They will all be running concurrently sharing the cluster resources. You can use sparkSession.streams() to get the StreamingQueryManager (Scala/Java/Python docs) that can be used to manage the currently active queries.`

## Revovering from Failures with Checkpointing
`In case of a failure or intentional shutdown, you can recover the previous progress and state of a previous query, and continue where it left off. This is done using checkpointing and write-ahead logs. `