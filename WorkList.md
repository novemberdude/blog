# Thu, 10/12/2020
+ pip install -r requirements.txt
+ pip install -e
+ cx_Oracle is a Python extension module that enables access to Oracle Database. It conforms to the Python database API 2.0 specification with a considerable number of additions and a couple of exclusions. (customer experience)
+ from pprint import pprint --> in những dữ liệu có cấu trúc một cách dễ đọc (preaty print - có lùi dòng, xuống dòng hợp lý thay vì in trên một dòng như print())
+ The coloredlogs package enables colored terminal output for Python’s logging module.
+ lxml is a Pythonic, mature binding for the libxml2 and libxslt libraries. It provides safe and convenient access to these libraries using the ElementTree API.
+ MinIO Python SDK is Simple Storage Service (aka S3) client to perform bucket and object operations to any Amazon S3 compatible object storage service
+ The Python Imaging Library adds image processing capabilities to your Python interpreter.
+ ProxyBroker is an open source tool that asynchronously finds public proxies from multiple sources and concurrently checks them.
+ proxy
+ reputa
+ exactly one, checkpointing in spark structured streaming.
+ thread
+ import logging --> https://realpython.com/python-logging/
+ thread in python: https://realpython.com/intro-to-python-threading/

# Wed, 9/12/2020
 + dzone.com
 + read write config files in python
 + "migrate" term --> if you migrate your server to a new host
 + lấy slide đẹp trên https://slidesgo.com/theme/long-distance-christmas-calls
 + 5 greate data engineering online course
 + stop all queries in spark.streams.active: [q.stop() for q in spark.streams.active]
 + `Cannot start query with id 455a4ffd-cbce-403d-be1d-ba3e501fb16f as another query with same id is already active. Perhaps you are attempting to restart a query from checkpoint that is already active.` 
 + hackathon: cuộc thi lập trình
 + hackerank.com: trang web luyện tập, xếp hạng lập trình.
 + wordcount with DataFrame: df = spark.read.text(path) --> df.select(F.explode(F.split(F.col('value'), ' ')).alias('word')).groupBy('word').count().orderBy('count', accending=False).
 + tham khảo sentiment analysis with tweeter tại: https://github.com/kaantas/spark-twitter-sentiment-analysis
 + elasticsearch: https://topdev.vn/blog/elasticsearch-la-gi/: Người ta cũng có thể dùng ES là DB chính nhưng thường không ai làm thế vì cái gì cũng có nhiệm vụ riêng biệt của nó. ES không mạnh trong các thao tác CRUD, nên thường sẽ dùng song song với 1 DB chính (SQL, MySQL, MongoDB …).
 --> ES có cơ chế đặc trưng để xử lý tìm kiếm text (ví dụ: tìm kiếm từ, tìm kiếm không dấu)
 + tìm kiếm mờ (fuzzy), tức là từ khóa tìm kiếm có thể bị sai lỗi chính tả hay không đúng cú pháp thì vẫn có khả năng elasticsearch trả về kết quả tốt


 + Apache Lucene: Lucene là phần mềm mã nguồn mở, dùng để phân tích, đánh chỉ mục và tìm kiếm thông tin với hiệu suất cao bằng Java. Lucene được phát triển đầu tiên bởi Doug Cutting được giới thiệu đầu tiên vào tháng 8 năm 2000. Tháng 9 năm 2001 Lucene gia nhập vào tổ chức Apache và hiện tại được Apache phát triển và quản lý: https://kipalog.kaopiz.com/posts/Lucene
 + Spark Streaming vs Structured Streaming

# Tue, 8/12/2020
+ install kibana, elasticsearch used docker
+ why docker eates too much space on disk: https://cntnr.io/whats-eating-my-disk-docker-system-commands-explained-d778178f96f1
+ run pyspark by pointing to SPARK_HOME (without install package `pyspark` additionally): --> import findspark/findspark.init()/import pyspark --> (set $SPARK_HOME in .bashrc file)
 --> `error`: *Error: Missing application resource.*,
 			  *Exception: Java gateway process exited before sending its port number* ===> Used scala 11 instead of 12 and used pyspark --packages ...
+  In short, Structured Streaming provides fast, scalable, fault-tolerant, end-to-end exactly-once stream processing without the user having to reason about streaming.
+ github.com/trending - collections - topics, githubuniverse.com
+ socket, Netcat( nc -lk 9999)
+ explode in DataFrame
+ Structured tSreaming: The key idea in Structured Streaming is to treat a live data stream as a table that is being continuously appended.
+ postman
+ rdd.pprint()



# Mon, 7/12/2020

+ ssh in git clone option
+ config user.name and user.email per Repository: https://crunchify.com/how-to-set-github-user-name-and-user-email-per-repository-different-config-for-different-repository/
+ .gitignore: https://www.pluralsight.com/guides/how-to-use-gitignore-file
+ push a new project to github
+ F.lag
+ pyspark.sql.window: https://knockdata.github.io/spark-window-function/
+ os.environ object in Python: https://www.geeksforgeeks.org/python-os-environ-object/#:~:text=environ%20in%20Python%20is%20a,and%20their%20values%20as%20value.
	--> OS module in Python provides functions for interacting with the operating system
	--> `os.environ` in Python is a mapping object that represents the user’s environmental variables. It returns a dictionary having user’s environmental variable as key and their values as valu
+ pyspark in Jupyter:	
	https://www.sicara.ai/blog/2017-05-02-get-started-pyspark-jupyter-notebook-3-minutes
	1. 2 ways to get PySpark available in a Jupyter Notebook
		+ Configure PySpark driver to use Jupyter Notebook: running `pyspark` will automatically open a Jupyte Notebook
		+ Load a regular Jupyter Notebook and load PySpark using findSpark package
+ learn Jupyter, compare Jupyter vs Ipython, what is IPython
+ symbolic link: $ ln -s /opt/spark-1.2.0 /opt/spark̀
+ virtualenv: môi trường ảo --> cho phép làm việc với các package của python mà không ảnh hưởng đến các package đã cài, tách biệt các môi trường giữa các project khác nhau.Mỗi "môi trường ảo" về bản chất chỉ là một thư mục, khi dùng pip để cài package, các package sẽ được cài vào thư mục này.
	1. https://kipalog.com/posts/Gioi-thieu-Virtual-Environment-trong-Python
	--> Cài đặt và sử dụng Virtual Enviroment trên Python:
		+ Cài: pip3 install virtualenv
		+ Tạo: virtualenv [project_name_env]
		+ Sử dụng: source [project_name_env]/bin/activate
		+ Thoát: deactivate
		+ Xóa môi trường ảo: đơn giản là xóa thư mục: rm -rf [project_name_env]
		+ Đồng bộ môi trường ảo.
	2. https://pymi.vn/blog/virtualenv/#:~:text=virtualenv%20l%C3%A0%20m%E1%BB%99t%20ph%E1%BA%A7n%20m%E1%BB%81m,c%C3%A0i%20v%C3%A0o%20th%C6%B0%20m%E1%BB%A5c%20n%C3%A0y.
	--> pip show ipython -> thông tin
	3. https://etuannv.com/huong-dan-su-dung-moi-truong-ao-virtual-environments-trong-python/


# Fri, 4/12/2020

- Vấn đề: 
+ không connect được vào kafka từ Structured Streaming trên Pycharm
+ đã connect được vào kafka từ Structured Streaming trên pyspark (chú ý phiên bản package: --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.2.0 và phiên bản spark 2.4.7). Tuy nhiên, dùng pyspark thì không biết hiển thị dữ liệu treaming như thế nào