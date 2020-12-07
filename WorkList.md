# Fri, 4/12/2020

- Vấn đề: 
+ không connect được vào kafka từ Structured Streaming trên Pycharm
+ đã connect được vào kafka từ Structured Streaming trên pyspark (chú ý phiên bản package: --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.2.0 và phiên bản spark 2.4.7). Tuy nhiên, dùng pyspark thì không biết hiển thị dữ liệu treaming như thế nào

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