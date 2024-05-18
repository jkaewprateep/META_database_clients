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
</br>
🐐💬 The conversation about not ```increasing the connection pool size is true``` because it had already been assigned and first introduced they had a known issue about return resources indicated ```known issue```. To use this trick you need to manage both MySQL resource pool and clients. </br>
</br>
💃( 👩‍🏫 )💬 Allowed me with this time error code is from database connector and they are enumerical form, you can convert them into number mapping with target error code and error status. This message enumerical number provides system default numbers for input return last error code found from target execution. </br>
🦤💬 These tangible numbers create responsive actions by application codes executing the operation, this is because they are planned by both client and server, selection of response and feedback actions and they are managed services this process is a priority value form. </br>
💃( 👩‍🏫 )💬 To action perform design authorized by priority, users authority, and communication effective of the process because at the time execution to fixed the issue with time all processes are the same importance and effective is defined. User authority should match the application or process priority, error code is one of the indicators of the process. Develop yourself for potential skills and potential management to have suitable authority. </br>

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

🐐💬 What is the most priority when there is ```ER_ACCESS_DENIED_ERROR``` and ```ER_BAD_DB_ERROR```⁉️ We still importing new house loans sequence ... </br>
🦭💬 It should filter and remarked by import process and concatenate tables. </br>

### Result as output from create connection pool and filled with connected client connection defined

```
Poolname:  pool_a  number of connection(s):  0
Poolname:  pool_a  number of connection(s):  1
Poolname:  pool_a  number of connection(s):  2
```

## Stroe procedures and import for MySQL Client

💃( 👩‍🏫 )💬 There are ```commit``` and ```uncommit``` SQL execution processes when all ```commit processes``` can cause a process time delay and you can be enabled of this behavior but utilize the resources the SQL process time can utilize temporary tables, programs, and store procedure to work with commit and uncommit ```execution```. </br>
🦤💬 By database design system temporary tables and third-party ```temporary tables``` are not ```statistics acquiring plans``` for execution because they are updated statistics with the ```target client``` and the client may inform you with an update message in some communication method different from the database. Many users from statistics are different because ```event listeners``` had information but the database is not ```up-to-date with the statistics``` values. This is not by the system design ```IT application support``` can answer this question and should have one source of information comparison as one priority. </br>

### Define store procedure and SQL statement

```
# Task 3: Implement a stored procedure GuestStatus
# Create and call a stored procedure named GuestStatus that outputs status of each guest’s order based on which
# employee is assigned to the order.

cursor.execute("DROP PROCEDURE IF EXISTS GuestStatus;");

SQL_database_littlelemon_use = """
USE little_lemon_db;
"""

SHOW_TABLES = """
SHOW TABLES;
"""

SQL_database_bookings_pc_gueststatus = """
CREATE PROCEDURE GuestStatus(  ) 
	BEGIN 
        SELECT Bookings.BookingID, Bookings.TableNo, CONCAT(Bookings.GuestFirstName,
            Bookings.GuestLastName) AS 'GuestFullName', Employees.Name AS 'EmployeeName', 
                
        CASE
            WHEN Employees.Role in ( 'Manager', 'Assistant Manager' ) THEN 'Ready to pay'
            WHEN Employees.Role in ( 'Head Chef' ) THEN 'Ready to serve'
            WHEN Employees.Role in ( 'Assistant Chef' ) THEN 'Preparing Order'
            WHEN Employees.Role in ( 'Head Waiter' ) THEN 'Order served'
            ELSE "UNKNOWN"
        END AS 'Status',
        
        MenuItems.Name AS 'MenuName', Orders.Quantity AS 'Quantity'

        FROM Bookings, Employees, Orders, Menus, MenuItems

        WHERE Bookings.EmployeeID = Employees.EmployeeID
        AND Bookings.BookingID = Orders.BookingID
        AND Bookings.TableNo = Orders.TableNo
        AND Orders.MenuID = Menus.MenuID
        AND Menus.ItemID = MenuItems.ItemID

        ORDER BY Bookings.BookingSlot, CONCAT(Bookings.GuestFirstName, Bookings.GuestLastName), Employees.Name;
    END
"""
```

### Import data into MySQL tables

```
try:
    cursor.execute( SQL_database_littlelemon_use );
    result = cursor.fetchall();

    cursor.execute( SHOW_TABLES );
    tables = cursor.fetchall();

    if "Bookings" not in [ x[0] for x in tables ] :
        print( "Please create database table Bookings." );
        quit;

    if "Employees" not in [ x[0] for x in tables ] :
        print( "Please create database table Employees." );
        quit;

    if "Orders" not in [ x[0] for x in tables ] :
        print( "Please create database table Orders." );
        quit;

    if "Menus" not in [ x[0] for x in tables ] :
        print( "Please create database table Menus." );
        quit;

    if "MenuItems" not in [ x[0] for x in tables ] :
        print( "Please create database table MenuItems." );
        quit;
    else:
        cursor.execute( SQL_database_bookings_pc_gueststatus );
        cursor.callproc("GuestStatus");
        
        resultset = next(cursor.stored_results());
        resultset = resultset.fetchall();

        columnnames = [ x.description for x in cursor.stored_results() ];
        columnnames = [ a for ( a, b, c, d, e, f, g, h, i ) in columnnames[0] ];
        print( columnnames )

        resultset = [ (x[0], x[1], x[2], x[3], x[4], x[5], x[6]) for x in resultset ];
        resultset = [ ( BookingID, TableNo, GuestFullName, EmployeeName, Status, MenuName, Quantity ) for BookingID, 
                        TableNo, GuestFullName, EmployeeName, Status, MenuName, Quantity in resultset ];

        for item in resultset :
            ( BookingID, TableNo, GuestFullName, EmployeeName, Status, MenuName, Quantity ) = item;

            print( ( BookingID, TableNo, GuestFullName, EmployeeName, Status, MenuName, Quantity ) )       
    
except conn.Error as errorcodes : 
    print( errorcodes.errno, errorcodes.msg );

print( "conn.is_connected: ", conn.is_connected() );
```
