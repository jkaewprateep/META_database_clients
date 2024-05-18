# META database clients
META database clients

* Meta Database Engineer Professional Certificate [META]( https://coursera.org/share/0b7133ceaec8027d53af1c74b7d8e47d )
* Meta Back-End Developer Professional Certificate [META]( https://coursera.org/share/bc30f508bcf68936d9028e9d0d6b9dfc )
* HackerRank SQL (Advance) [HackerRank]( https://www.hackerrank.com/certificates/f225fa371510 )

<p align="center" width="100%">
    <img width="47%" src="https://github.com/jkaewprateep/META_database_clients/blob/main/meta_databaseclient_instructor.png">
    <img width="17.63%" src="https://github.com/jkaewprateep/META_database_clients/blob/main/image31.jpg"> </br>
    <b> META database clients | My favorite teacher 💃( 👩‍🏫 )  </b> </br>
    <b> Pictures from the Internet </b> </br>
</p>

## MySQL Client database connection pool

🧸💬 Data integration method does not connect and fast transfer rates of information but builds and extracts information suitable with clients, a manageable and sufficient method way in communication and replication. There are resources or data sources management when ```SQL``` and ```Non-SQL``` develop ```resource management``` help about data integrity with manageable when the user needs can manage of connectivity and utilized of database connectivity resources by their codes. Implementation ```resource pools``` are shared resources with tangible programming assignments for multiple ```user access``` and ```connectivity property``` parameters provided. </br>
🐑💬 ➰ Server - client database connectivity resources utilization on larger scales you need to manage the number of connectivity, connectivity timeout, security level, communication message encoder and decoder selection, connectivity speed, and accountibility. Microservices and temporary tables are one of the methods, client manage codes is another method, and resource management with queue and assignment is another method, queuing or file system is another method but ```MySQL``` and ```MongoDB``` come with a connection pool for resource utilization and you can create database adaptor for your application. For example, standard ```database.js``` or database connection adaptor in ```Django``` or ```Spring framework``` or ```java application``` can utilized with MySQL or MongoDB as it is a class with ```classes heritance property```. </br>

```
# 🧸💬 Library import
import mysql.connector as connector;
from mysql.connector import errorcode;
from mysql.connector.pooling import MySQLConnectionPool;

# 🧸💬 Parameterize connection variables input
username = "root";
password = "";
database = "little_lemon_db";

pool = MySQLConnectionPool( pool_name="pool_a", pool_size=3, host="localhost",
        database=database, username=username, password=password );

for i in range( pool.pool_size ):

    try: 
        conn = pool.get_connection();
        if conn.is_connected() :
            cursor = conn.cursor();
        else :
            conn  = connector.connect( user=username, password=password );

        print( "Poolname: ", pool.pool_name, " number of connection(s): ", i );

    except connector.Error as errorcodes :
        if errorcodes.errno ==  errorcode.ER_ACCESS_DENIED_ERROR :
            print( conn.is_connected(), "ER_ACCESS_DENIED_ERROR" );
        elif errorcodes.errno ==  errorcode.ER_BAD_DB_ERROR :
            print( conn.is_connected(), "ER_BAD_DB_ERROR" );
        else :
            print( errorcodes.errno, errorcodes.msg );
```

### Result as output from create connection pool and filled with connected client connection defined

```
Poolname:  pool_a  number of connection(s):  0
Poolname:  pool_a  number of connection(s):  1
Poolname:  pool_a  number of connection(s):  2
```
