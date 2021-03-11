# Một số khái niệm nhập môn:
- graph: đồ thị: một tập các đỉnh (node), nối với nhau bởi các cạnh (edge), cạnh có thể có hướng hoặc không có hướng

# GraphDB là gì:
 - Là một csdl dạng đồ thị, là một tập hợp các đỉnh và các cạnh nối giữa các đỉnh, các cạnh có thể có hướng hoặc không.
 - Node: danh từ (person, place_thing), mỗi node có properties
 - relationship giữa các node

--> Mỗi liên hệ giữa các đối tượng, tìm đường đi ngắn nhất, phát hiện gian lận ()
+ thực hiện giải thuật đồ thị (graph algorithm): community detection, pagerank, 

# Tại sao cần GraphDB:
 - Đặc điểm của GraphDB:
 + điểm nối bật là MỐI QUAN HỆ giữa các đối tượng, được biểu diễn bằng các CẠNH
--> Khi gặp một bàn toán cần kết nối nhiều đối tượng thì với RMDBS quen thuộc chắn không phải là một giải pháp hay vì:
	+ Việc biểu diễn quan hệ dưới dạng bảng không phải là một cách trực quan (thế nào là trực quan)
	+ Các phép join tốn nhiều chi phí (cần có số liệu)

# GraphDB vs RMDBS, NoSQL database
# Ứng dụng của graphDB
# Các công nghệ

# Query language - Ngôn ngữ truy vấn
- Không dùng SQL, vì SQL được thiết kế cho RMDBS, not built for highly connected data.
+ Neo4j có ngôn ngữ Cypher
+ ArangoDB có AQL (Arange Query Language)

## Intro:
- Giống như SQL, AQL là một delarative language (mô tả lấy gì, not lấy như thứ nào)
- So sánh với SQL:
+ Hỗ trợ đọc, sửa dữ liệu
+ Là data manuplation language (DML), không phải một data definition language (DDL - tạo xóa, database, collections, indexes) data control langugae (DCL)

## Tutorial:

1. CRUD:
- Create Documents: INSERT document INTO collectionName (document là một đối tượng JSON)
+ AQL không có chèn nhiều document một lần, phải dùng for
+ Khi tạo 1 document, được thêm 3 trường: _key, _id, _rev (system attribute  with _ is read only)
- Keyword: 
+ LET: định nghĩa một biến
+ FOR variableName IN expression : lặp trọng một mảng
- Read Documents: 

+ ```FOR c IN Characters
    RETURN c```

+ ```RETURN DOCUMENT("Characters", "2861650")
// --- or ---
RETURN DOCUMENT("Characters/286165```

- Update document:
+```UPDATE documentKey WITH object IN collectionName```
+ `REPLACE`

- DELETE document:
+ `REMOVE "2861650" IN Characters`


2. Match CRUD
+ `FILTER c.name == "Ned"
   FILTER c.age > 13`
condition: ==, >= 
+ FILTER condition1 AND/OR condition2, hoặc FILTER condtion1 FILTER condition2 (== AND)

3. Sorting and limmit:
`LIMIT`, `SORT`

4. Joining together
- docs: https://www.arangodb.com/docs/stable/aql/index.html

`FOR c IN Characters
    RETURN DOCUMENT("Traits", c.traits)`

`FOR c IN Characters
    RETURN DOCUMENT("Traits", c.traits)[*].en`

`FOR c IN Characters
    RETURN MERGE(c, { traits: DOCUMENT("Traits", c.traits)[*].en } )`

*Join another way* ???

5. Traversal
- Trong ArangoDB, hai document có thể được link bởi một edge document, edge documents được lưu trong edge collections và có thêm 2 attribute bổ sung laf _from, _to_)

`INSERT { _from: "Characters/robb", _to: "Characters/ned" } INTO ChildOf`

- traverse to children
- traverse to parents
- traverse to grandchidren 
- traverse with variable depth

6. Geospatial queries

## How to invoke AQL
+ web interface, `db` object, raw HTTP API (There are always calls to the server’s API under the hood)

## AQL fundamental
1. AQL Syntax
2. Data types
3. Bind parameter: ???
4. Type and values Order
5. Accessing data from collections
5. Query result
6. Query errors
7. Limitation: ???

## OPERATOR

## Data queries:
2 type: access data (reads document), modify data (create, update, replace, delete document)
Restction ???

## Graph in AQL

1. Traversal explained
2. Traversals
+ There are two slightly different syntaxes for traversals in AQL, one for
--> named graphs and another to
--> specify a set of edge collections (anonymous graph).

# FAQ:
1. GraphDB có phải là NoSQL: 
 - Đúng, graph db là một loại NoSQL database, được tạo ra để giải quyết các giới hạn của CSDLQH. Mô hình đồ thị tập trung thể hiện rõ ràng mqh phụ thuộc lẫn nhau giữa các node dữ liệu, còn CSDLQH và các CSDL NoSQL khác liên kết dữ liệu bằng các *IMPLICIT CONNECTION*

2. So sánh GraphDB vs RMDBS:
+ RMDBS: lưu trữ dữ liệu dưới dạng bảng, quan hệ thông qua phép join
+ GraphDB: lưu trữ dữ liệu dưới dạng đồ thị
+ Dữ liệu được lưu trữ thực tế ntn? (of course not in tables)

3. Named graph vs annonymous graph
- Named graph:
+ quản lý bởi arangodb
+ transaction modification
+ edge consistentcy
+ edge clean up
+ graph module (arangos, drivers)
--> ưu điểm: chỉ cần chỉ tên graph trong traversal query, không phải chỉ ra các collection liên quan như trong anonymous graph
- anonymous graph:
+ flexible access
+ no edge definition/consistency
+ client-side consistency

--> ưu điểm: phải 

# Tài liệu:
+ https://www.youtube.com/watch?v=REVkXVxvMQE
+ https://en.wikipedia.org/wiki/Graph_database#:~:text=Graph%20databases%20are%20a%20type,the%20data%20by%20implicit%20connections.