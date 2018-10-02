### Sqoop
## Importing data from Database to HDFS
- Sqoop is a tool with import/export capability to move data between hadoop HDFS and Database.
- For example, Below command will import EMP table from Database to HDFS
>sqoop import \
>--connect jdbc:mysql://localhost/userdb \
>--username root \
>--table emp --m 1
- To verify the imported data in HDFS
> $ $HADOOP_HOME/bin/hadoop fs -cat /emp/part-m-*
- if you want to import to target folder then provide below --target-dir parameter to import command
> --target-dir <new or exist directory in HDFS>
- if you want to import subset of data then --where is used with import commond
> --where “city =’Mumbai’” \

## Exporting data from HDFS to Database
>$ sqoop export \
>--connect jdbc:mysql://localhost/db \
>--username root \
>--table employee \ 
>--export-dir /emp/emp_data