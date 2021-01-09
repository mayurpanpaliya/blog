# Some interesting SQL queries 

## Task : Get 50% data from table 

* SQL -> ``` SELECT TOP 50 PERCENT * FROM Customers; ```
* PySpark -> ``` df.sample(False, 0.5).count() ```


## Task : Delete the duplicate data from table in single query 

1. SQL -> ``` DELETE p from Person p, Person q where p.Id>q.Id AND q.Email=p.Email ```
2. PySpark ->
```
    * df.dropDuplicates().show()
    * df.dropDuplicates(['name', 'height']).show()
```
## Task : Multi-dimensional rollup
Problem : 
1. SQL -> 
```
with
unbanned as ( select Users_Id  from Users where Banned = 'No' )  

select Request_at as Day , round(cancel / total,2) as `Cancellation Rate`
	from (
		select Request_at , 
		sum(if(Status='cancelled_by_driver' or Status='cancelled_by_client',cnt,0)) as cancel ,
		sum(if(Status is null,cnt,0 )) as total 
		from (
			select Request_at , Status ,  count(1) as cnt from Trips 
			where  Client_Id  in (select Users_Id from unbanned )
			and   Driver_Id   in (select Users_Id from unbanned )
			and  Request_at >= "2013-10-01" and Request_at <= "2013-10-03"
			GROUP BY Request_at , Status WITH ROLLUP
			)sq1
		group by Request_at
)sq2
where Request_at is not null
```
2. PySpark -> ``` df.rollup("name", df.age).count().orderBy("name", "age").show() ```

### Reference :
* https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf
* https://www.markdownguide.org/basic-syntax/
* https://www.w3schools.com/sql/sql_top.asp
* http://spark.apache.org/docs/2.1.0/api/python/pyspark.sql.html#pyspark.sql.DataFrame.sample
* https://leetcode.com/problems/delete-duplicate-emails/
* http://spark.apache.org/docs/2.1.0/api/python/pyspark.sql.html#pyspark.sql.DataFrame.dropDuplicates  
* http://spark.apache.org/docs/2.1.0/api/python/pyspark.sql.html#pyspark.sql.DataFrame.rollup
* https://leetcode.com/problems/trips-and-users/discuss/1006041/mysql-with-rollup
