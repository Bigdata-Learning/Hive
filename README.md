Hive is a datawarehousing layer above Hadoop.
It gives SQl like semantics over Hadoop data(HDFS).
Although now many SQl engine over hadoop like Impala,Drill,Presto has come but Hive was the original SQL engine on top of Hadoop.


1. Sample create table in Hive -

CREATE TABLE IF NOT EXISTS employee ( empid int, name String,
salary String, destination String)
COMMENT ‘Employee details’
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ‘\t’
LINES TERMINATED BY ‘\n’
STORED AS TEXTFILE;

Exp - the row format delimited mentions how the data in HDFS will be. 
In this case it will be tab delimited.
Each row will be delimited by new line(\n).

TextFile is basic format of Hive/HDFS.Later we will look into Avro and Parquet format which is gaining low of popularity.

2. Inserting data into table

LOAD DATA INPATH 'usr\emp' INTO employee

Exp- It will load the data present in HDFS path usr\emp into the table that was created.

3. External table - 
