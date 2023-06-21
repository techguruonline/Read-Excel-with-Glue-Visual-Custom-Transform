# Read-Excel-with-Glue-Visual-Custom-Transform

AWS Glue is a serverless data integration service that makes it easy for analytics users to discover, prepare, move, and integrate data from multiple sources

Under Glue service, there are different components such as Data Catalog, Data Integration and ETL

### Data Catalog

 1. AWS Glue Data Catalog is a centralized and unified metadata repository. It is a managed service where you can store, search, share metadata with various AWS services. You catalog your databases, table definitions or schema, runtime metrics in the data catalog.
 2. With AWS Glue, you can discover and connect to more than `70 diverse data sources` and manage your data in a centralized data catalog.
 3. You create connections to your data sources like JDBC, you create the connection once providing the user credentials, data catalog stores the connection details for you and can be reused across jobs
 4. Crawlers lets you crawl through your data stores, scans your tables and adds table definition and schema to your data catalog automatically.

### Data Integration and ETL

 1. Glue offers interface for virtually very persona
 2. AWS Glue Studio is a graphical interface for those who prefer to develop their jobs with no code and run them on Apache Spark-based serverless ETL engine.
 3. Interactive sessions using Notebook - For those who prefer to author their jobs with builtin notebook, who like to write their own code
 4. Triggers are used within a workflow to trigger a job on-demand or on schedule or on events.
 5. And lastly using workflow, you can design a complex multi-job ETL process, execute and monitor the jobs with Glue

Glue provides more than 30 ready to use built-in advanced transforms such as Join, Aggregate, Filter, SQL Query etc to transform your data part of your ETL pipeline.
What if you want a specific functionality that isn't part of AWS Glue built-in transform offering? What if you want to built a custom transformation yourself much like a UDF?
Well, AWS Glue has an answer for you through Visual Custom Transform. Custom visual transforms allow you to create transforms and make them available for use in AWS Glue Studio jobs. Custom visual transforms enable ETL developers, who may not be familiar with coding, to search and use a growing library of transforms using the AWS Glue Studio interface.

I am going to show you step by step on how to develop your own transformation and make it available for others in your organization to reuse it for their ETL pipeline development
In this example we are going to develop a Visual Custom Transform for reading a Excel file that is stored on Amazon S3 and make it available in Glue studio for others to reuse.

### Pre-requisite

1. AWS Account
2. S3 Bucket for Storing the Source excel file, Python script, config JSON file
3. Editor for developing Python code (I am using VS Code)

Please refer to the official [documentation](https://docs.aws.amazon.com/glue/latest/ug/custom-visual-transform.html) on AWS Glue custom visual transforms for more details!

First we need to develop a Python code with a function to parse and read the excel file. 
Lets examine the below code, I have also provided the python file in the repo, please feel to use it for your purpose.

1. List all the objects in the S3 path
2. Go in loop to find the excel file form the list of objects
3. Get object from S3 using boto3
4. Read excel using pandas `read_excel` method and `openpyxl` engine
5. Finally, return a DynamicFrame from a Pandas DataFrame

![Screenshot of Python Code](https://github.com/techguruonline/Read-Excel-with-Glue-Visual-Custom-Transform/blob/main/Images/PythonCode.png)


Now we have the backend code ready, to pass the arguments from within the Glue Studio, we need to create a config file
![Screenshot of config JSON file](https://github.com/techguruonline/Read-Excel-with-Glue-Visual-Custom-Transform/blob/main/Images/ConfigFile.png)




![Below screenshot of the ETL Job developed using Glue Studio Visual](https://github.com/techguruonline/Read-Excel-with-Glue-Visual-Custom-Transform/blob/main/Images/GlueJob.png)
