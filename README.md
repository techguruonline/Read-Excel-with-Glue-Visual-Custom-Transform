# Read-Excel-with-Glue-Visual-Custom-Transform

AWS Glue is a serverless data integration service that makes it easy for analytics users to discover, prepare, move, and integrate data from multiple sources

Under Glue service, there are different components such as Data Catalog, Data Integration and ETL

### Data Catalog

 1. AWS Glue Data Catalog is a centralized and unified metadata repository. It is a managed service where you can store, search, share metadata with various AWS services. You catalog your databases, table definitions or schema, runtime metrics in the data catalog.
 2. You create connections to your data sources like JDBC, you create the connection once providing the user credentials, data catalog stores the connection details for you and can be reused across jobs
 3. Crawlers lets you crawl through your data stores, scans your tables and adds table definition and schema to your data catalog automatically. 

### Data Integration and ETL

 1. Glue offers interface for virtually very persona
 2. AWS Glue Studio is a graphical interface for those who prefer to develop their jobs with no code and run them on Apache Spark-based serverless ETL engine. 
 3. Interactive sessions using Notebook - For those who prefer to author their jobs with builtin notebook, who like to write their own code
 4. Triggers are used within a workflow to trigger a job on-demand or on schedule or on events.
 5. and lastly using workflow, you can design a complex multi-job ETL process, execute and monitor the jobs with Glue
