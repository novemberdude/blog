# Fri, 08/01/2021
+ with open('../../keywords_for_searching_hashtags', 'r') as file:
    records = file.read().split('\n')


# Thu, 07/01/2021
+ buit-in magic command in Python
+ magic command (%) có thể chạy trên jupyter notebook hoặc pycharm trong python console with conda.
	-> python console không phải là Ipython
+ truncate vs delete, khi truncate với bảng có key được tham chiếu từ bảng khác thì có thể dùng tạm delete.

# Wed, 06/01/2021
+ Oracle: chỉ thay đổi được thứ tự cột trong bảng khi tạo bảng, sau khi tạo thì không sửa được (đây là một cách để bảo vệ sự không thống nhất giữa các phiên bản)
+ Sau khi commit() là không rollback được, vậy rollback thực sự làm gì?
+ sử dụng executemany() khi fail một bản ghi thì sẽ fail toàn bộ batch
+ Oracle: sysdate=26-DEC-20
+ why alias of context manage can still be refered outside with scope


# Tue, 05/01/2021
+ cur.execute(statement,(*tuple*)) / cur.executemany(statement, [(*tuple*)])
+ When you make execute Data Manipulation Language or DML statements, such as the insert I use in this post, those changes are only visible to your current connection or session. https://learncodeshare.net/2015/06/26/insert-crud-using-cx_oracle/

# Mon, 04/01/2021
+ Should I use additional column for key instead of multiple column? https://stackoverflow.com/questions/2204381/what-are-the-pros-and-cons-of-using-multi-column-primary-keys
+ Oracle don't have boolean data type, use NUMBER(1,0) instead.
+ varchar vs varchar2 in oracle: https://stackoverflow.com/questions/1171196/what-is-the-difference-between-varchar-and-varchar2-in-oracle
+ char vs varchar: VARCHAR is variable-length, CHAR is fixed length: https://www.databasestar.com/char-varchar-varchar2/
+ You should see the max length provided for a VARCHAR column as a kind of constraint (or business rule) rather than a technical/physical thing. https://stackoverflow.com/questions/8295131/best-practices-for-sql-varchar-column-length
+ SMALLINT is NUMBER(38): Note that INT, SMALLINT, NUMERIC, and DECIMAL are just aliases. They are not the real data types. Internally, Oracle maps these aliases to the corresponding NUMBER data type.


--------------------------------------------------------------------------
--------------------------------------------------------------------------
--------------------------------------------------------------------------
--------------------------------------------------------------------------

# Thu, 31/12/2020
+ sql naming convention: https://www.sqlshack.com/learn-sql-naming-conventions/

# Wed, 30/12/2020
+ SplashRequest return response.data['html'] không có gì khi không có js, không giống vnexpress trả về html có sẵn dữ liệu.
+ localhost:8050 --> không dùng được(https://stackoverflow.com/questions/58556759/how-to-enable-javascript-in-splash) --> bỏ dùng thử selenium xem sao
+ XHR in Network tab (F12): XMLHttpRequest: https://completejavascript.com/xmlhttprequest-tao-http-request-den-server-trong-javascript

# Tue, 29/12/2020
+ requests.get('tiktok.com') -> response.text = ''

# Mon, 28/12/2020
+ loc, iloc in pandas: loc is label-based, which means that we have to specify the name of the rows and columns that we need to filter out/ On the other hand, iloc is integer index-based. So here, we have to specify rows and columns by their integer index
	data.loc[data.age >= 15]
	data.loc[(data.age >= 12) & (data.gender == 'M')]
	data.loc[1:3]
	data.loc[(data.age >= 12), ['city', 'gender']]
	data.loc[(data.age >= 12), ['section']] = 'M'
	data.loc[(data.age >= 20), ['section', 'city']] = ['S','Pune']
	data.iloc[[0,2]]
+ scrapy shell 'https://...'



--------------------------------------------------------------------------
# Fri, 25/12/2020
+ Indent, Unindent in sublime text: Ctrl+[/]
+ clean code - Robert Martin
+ https://moderatemisbehaviour.github.io/clean-code-smells-and-heuristics/
+ sphinx
+ https://kipalog.com/posts/Cach-tao-project-documentation-cho-codebase-Python-dung-Sphinx


# Thu, 24/12/2020
+ "If it isn't automated...it's broken", "If it isn't tested...it's broken": https://learn.datacamp.com/courses/command-line-automation-in-python
+ Concurency and Parallelism are not the same.
+ logging in python: https://realpython.com/python-logging/
+ https://realpython.com/python-pep8/

# Wed, 23/12/2020
+ file requirements.txt in a python project: package_name==version
+ Do datascientists use object oriented programming: https://www.quora.com/Do-data-scientists-use-object-oriented-programming
+ ??? Khi nào thì dùng database connection pools.
+ có thể copy thủ công cookie của 1 website từ browser này sang browser khác.
+ what is UTF-8? https://vi.wikipedia.org/wiki/UTF-8 8-bit Unicode Transformation Format - Định dạng chuyển đổi Unicode 8-bit --> có khả năng tương thích ngược với ASCII nên rất phổ biến.
+ req.headers['Content-Type'] https://code.tutsplus.com/vi/tutorials/using-the-requests-module-in-python--cms-28204, https://stackoverflow.com/questions/23714383/what-are-all-the-possible-values-for-http-content-type-header
+ pixabay.com

# Tue, 22/12/2020
+ **LỖI THƯ VIỆN cx_Oracle**: tải thư viện, extract, install libaio1, thêm environ ở edit configuration của pycharm (pycharm không đọc biến môi trường ở file ~ /.bashrc): https://gist.github.com/kimus/10012910
+ codementor.io
+ kiểu dữ liệu ngày tháng trong oracle: datetime (YYYY-MON-DD HH24:MI), timestamp (YYYY-MM-DD HH24:MI:SS.FF)
+ Async IO in Python: A Complete Walkthrough: https://realpython.com/async-io-python/
+ login use cookie

# Mon, 21/12/2020
+ Can't block by MAC address because MAC address (Media Access Control) is not included in HTTP headers: https://security.stackexchange.com/questions/1118/can-i-block-based-on-mac-address#:~:text=5%20Answers&text=In%20short%2C%20the%20answer%20is,could%2C%20it%20would%20be%20useless.&text=As%20you%20can%20see%2C%20the,which%20router%20it%20came%20from.
+ how to block an ip from accessing your service: https://mediatemple.net/community/products/dv/204405044/block-a-specific-ip-address-from-accessing-your-website
+ 10 tips to void getting blocked when scraping websites. https://www.codementor.io/@scrapingdog/10-tips-to-avoid-getting-blocked-while-scraping-websites-16papipe62
	--> you must have a pool of at least 10 IPs before making an HTTP request. To avoid getting blocked you can use proxy rotating services like Scrapingdog or any other Proxy services.
+ https://blog.iconosquare.com/best-time-to-post-on-tiktok/



----------------------------------------
# Fri, 18/12/2020
+ Headless browser: Trình duyệt không có đầu là trình duyệt web không có giao diện người dùng đồ họa. Các trình duyệt không có đầu cung cấp khả năng kiểm soát tự động một trang web trong môi trường tương tự như các trình duyệt web phổ biến, nhưng chúng được thực thi thông qua giao diện dòng lệnh hoặc sử dụng giao tiếp mạng.
+ token vs cookie: https://dzone.com/articles/cookies-vs-tokens-the-definitive-guide
+ JWTs: JSON Web Tokens
+ cookie của chrome lưu trong sqllite3 database ở thư mục `~/.config/google-chrome/default.`
+ transfering cookie: https://superuser.com/questions/186609/how-do-i-transfer-copy-cookies-from-one-browser-to-another-or-same-browser-fro?rq=1
+ `getopt` python package: The getopt module is the old-school command line option parser that supports the conventions established by the Unix function getopt(). It parses an argument sequence, such as sys. argv and returns a sequence of (option, argument) pairs and a sequence of non-option arguments
+ `async` keyword in python: https://realpython.com/async-io-python/
+ Concurrency is a slightly broader term than parallelism. It suggests that multiple tasks have the ability to run in an overlapping manner. (There’s a saying that concurrency does not imply parallelism.)


# Thus, 17/12/2020
+ Create an icon for .sh file https://www.youtube.com/watch?v=daadsaHhXB8
+ pycharm warnings "method maybe static"
+ @staticmethod decorator in python ???
+ Cronjob là các lệnh thực thi hành động đặt trước vào thời điểm nhất định. Crontab là nơi lưu trữ các cronjob. Cron là một tiện ích giúp lập lịch chạy những dòng lệnh bên phía server để thực thi một hoặc nhiều công việc nào đó theo thời gian được lập sẵn. Một số người gọi những công việc đó là Cron job hoặc Cron task.Cron là một chương trình deamon, tức là nó được chạy ngầm mãi mãi một khi nó được khởi động lên. Như các deamon khác thì bạn cần khởi động lại nó nếu như có thay đổi thiết lập gì đó. Chương trình này nhìn vào file thiết lập có tên là crontab để thực thi những task được mô tả ở bên trong. https://vinahost.vn/crontab-linux-la-gi
+ `config` python package
+ https://viblo.asia/p/nhung-thu-ban-nen-biet-ve-http-gGJ59eJa5X2 Công nghệ cốt lõi là HTTP - Hypertext Transfer Protocol. Nó là phương thức giao tiếp bạn sử dụng khi bạn lướt web.
+ https://quantrimang.com/cac-truong-header-trong-http-156082
+ https://breadcrumbscollector.tech/stop-naming-your-python-modules-utils/ Stop naming your python modules “utils”, Synonyms of utils, like helpers, commons, etc. are bad for the same reason.
+ from ..monitor.monitor import alert
+ import sys, sys.version
+ import glob: The glob module finds all the pathnames matching a specified pattern according to the rules used by the Unix shell, although results are returned in arbitrary order
+ chứng chỉ oracle OCA, OCB.


# Wed, 16/12/2020
+ fb crawl: crawl ntn, theo user? theo location? mỗi user có crawl bài đăng của bạn bè không, có crawl bài đăng của bạn bè của bạn bè không (recursive?)
+ tiktok-api python package by davidteather (github): --> crawl dữ liệu khá đầy đủ, tuy nhiên cần tìm hiểu kĩ công nghệ 
+ medium.com là gì? là một blog cộng đồng, một nền tảng lớn và đáng tin cậy, chất lượng, không hoàn toàn miễn phí (sau khi đọc nhiêu bài được đánh giá cao, nếu muốn đọc tiếp thì phải đăng ký gói tháng, nếu không muốn thì đăng xuất tài khoản ra, đăng kí với tài khoản với :d hoặc dùng extension): 
	https://sharengay.commeo-doc-medium-com-free-khi-bi-yeu-cau-dang-ky-membership/
+ WebDriver là một công cụ mã nguồn mở trong mảng test tự động, cho phép các ứng dụng web của chúng ta có thể hoạt động trên các trình duyệt. Nó cung cấp các chức năng giúp chúng ta đi đến các địa chỉ web, nhập dữ liệu đầu vào, xử lý các code JavaScript, và rất nhiều các thao tác mà người dùng họ có thể tác động khác nữa. Và ChromeDriver là chính là công cụ giúp WebDriver thực hiện các công việc đó trên trình duyệt Chrome. https://vananhtooo.wordpress.com/2017/10/05/selenium-khoi-dong-trinh-duyet-chrome-voi-chromedriver/ 
+ ??? tại sao dùng selenium để crawl fb mà không dùng scrapy
+ code android: Java là ngôn ngữ chính thức để phát triển Android. Đây là ngôn ngữ có sự hỗ trợ nhiều nhất từ ​​Google
+ Selenium Webdriver (Se driver) là một tool open source giúp việc thực thi các hành động lên trang web một cách tự động, tất nhiên là tùy vào mục đích và yêu cầu của người viết. 
+ Even though Scapy is a powerfl web scraping framework, i becomes useless with these dynamic websites.
+ Yandex là một công ty web của Nga với hơn 60% người dùng web ở Nga sử dụng. Yandex là công ty tìm kiếm lớn thứ 4 trên thế giới với hơn 150 triệu lượt tìm kiếm mỗi ngày và khoảng 50 triệu người dùng thường xuyên
+ Search Engine Optimization - Tối ưu hóa công cụ tìm kiếm (SEO) là quá trình tăng chất lượng và lưu lượng truy cập website bằng cách tăng khả năng hiển thị của website hoặc webpage [1] cho người dùng trên các máy truy tìm dữ liệu như Google, Bing, Yahoo
+ What will happen if I don't follow robots.txt while crawling? https://softwareengineering.stackexchange.com/questions/180108/what-will-happen-if-i-dont-follow-robots-txt-while-crawling#:~:text=The%20Robot%20Exclusion%20Standard%20is,you%20choose%20to%20ignore%20it.
+ Playwright is a Python library to automate Chromium, Firefox and WebKit browsers with a single API. Playwright delivers automation that is ever-green, capable, reliable and fast
+ proxy in TikTokApi
+ freecodecamp.org
+ cần xem hình dáng cookie như thế nào?
+ datatype clob in oracle: Stands for "Character Large Object." A CLOB is a data type used by various database management systems, including Oracle and DB2. It stores large amounts of character data, up to 4 GB in size.



# Tue, 15/12/2020
+ proxy
+ MIT licience
+ selenium vs scrapy
+ Captcha: Completely Automated Public Turing test to tell Computers and Humans Apart
+ $HOME/.cache folder: có thể xóa, ứng dụng cần thì sẽ tạo lại. --> khi pip install package trong venv, package sẽ lấy từ $HOME/.cache, nếu không sẽ install vào .cache rồi copy vào venv https://askubuntu.com/questions/102046/is-it-okay-to-delete-the-cache-folder
+ userAgent:  "Mozilla/5.0 (Windows NT 10.0; Win64; x64) "
            "AppleWebKit/537.36 (KHTML, like Gecko) "
            "Chrome/86.0.4240.111 Safari/537.36"
    --> Trong máy tính, user agent là phần mềm hoạt động thay mặt cho người dùng. Một sử dụng phổ thông của từ này đề cập đến một trình duyệt web cho một trang web biết thông tin về trình duyệt và hệ điều hành
+ https://www.whatismybrowser.com/, https://blog.cloud365.vn/linux/tong-quan-ve-user-agent/
Tới thời điểm hiện tại, các trình duyệt đều phát triển để giống một trình duyệt khác (Mozilla), dần dần chuỗi User Agent trở nên lộn xộn gây khó hiểu nhầm lẫn
+ cookie: Cookie đơn giản chỉ là một đoạn văn bản ghi thông tin được tạo ra và lưu trên trình duyệt của máy người dùng, https://nguyenthanhthuong.com/huong-dan-su-dung-cookies/
+ j2team cookie: https://www.junookyo.com/2017/07/j2team-cookies-chrome-extension.html?utm_source=extension&utm_medium=j2team_cookies: chia sẻ tài khoản mà không sợ lộ mật khẩu
+ https://medium.com/@david.teather
+ put an open source python package to PyPi: https://realpython.com/pypi-publish-python-package/





# Mon, 14/12/2020
+ random.sample(population, k) ->Return a k length list of unique elements chosen from the population sequence or set. Used for random sampling without replacement.
+ `re` package in python --> re — Regular expression operations
+ from datetime import datetime, timedelta --> datetime.now() + timedelta(hours=7) (timedelta độ dời)
+ (datetime.datetime) a_time.strftime("%Y/%m/%d %H:%M:%S") --> return a string
+ Shadows name 'posts' from outer scope  --> should avoid to prevent potential unexpected error (vd, dùng global variable instead of local variable)
+ token fb: https://j2teamnnl.blogspot.com/2019/01/token-facebook-la-gi-va-cach-bao-mat-no.html
+ không đăng xuất tài khoản trong thời gian dài --> dùng token à???
+ Vụ bê bối dữ liệu Facebook–Cambridge Analytica -  87 triệu người sử dụng Facebook
+ titok api
+ seminar
+ sdk vs api https://rapidapi.com/blog/api-vs-sdk/
+ ffmpeg: là một dự án phần mềm mã nguồn mở và miễn phí, bao gồm một bộ thư viện lớn và chương trình để xử lý video, âm thanh cũng như các tệp và luồng đa phương tiện (à một phần mềm xử lý audio, video đơn giản, miễn phí và hiệu quả.) -  Fast Forward MPEG (Motion Picture Experts Group)
+ ??? cookies trong crawl fb là gì
+ import sys/ sys.argv[0] là file python: --> sys.argv là môt danh sách [list] trong python, nó được sư dụng khi bạn chạy một lệnh command-line nào đó trên hệ thống. Và argument này được đẩy vào script python để thực thi khi chạy câu lệnh.


# Fri, 11/12/2020
+ python format string: https://realpython.com/python-f-strings/

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
+ Oracle SQL Developer Oracle SQL Developer is a free graphical tool that enhances productivity and simplifies database development tasks. Using SQL Developer, users can browse database objects, run SQL statements, edit and debug PL/SQL statements and run reports, whether provided or created.
+ devops
+ where ROWNUM <= *rownum*
+ Ngữ pháp SQL (ngữ pháp tiêu chuẩn cho mọi db) vs Ngữ pháp SQL riêng của Oracle: https://o7planning.org/vi/10231/huong-dan-hoc-sql-cho-nguoi-moi-bat-dau-voi-oracle
+ random.uniform(): https://www.geeksforgeeks.org/python-number-uniform-method/ Returns the generated floating point random number between lower limit and upper limit
+ Tại sao lại là thứ 2 mà không phải là thứ một: --> tên thứ 2 bắt nguồn từ Bồ Đào Nha, tạo cảm giác bớt ngại khi bắt đầu một tuần mới (thứ 2 rồi, không phải thứ 1 đâu)
+ time.time() --> tổng số giây kể từ time.gmtime(0): timestamp, UNIX epoch time. https://www.datacamp.com/community/tutorials/python-time-sleep
+ time.ctime(): local time in a nicely formatted version (instead of second or ticks)
+ time.sleep(): takes as arguments the number of seconds you want the program to halt or to be suspended before it moves forward to the next step
+ cursor.close(), con.close() sau mỗi function truy vấn: Just don't keep an open connection while you do other lengthy non-db work. Close it and re-open it; you may actually get the same underlying connection back, but somebody else (another thread) might have made use of it while you weren't.
+ telegram bot: https://blog.cloud365.vn/linux/tao-canh-bao-su-dung-telegram-python/
+ random.shuffle() --> trộn một list

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
