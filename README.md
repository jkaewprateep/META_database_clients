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
