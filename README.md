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

🧸💬 Implementation of the select case and where cause selection, create utility store procedure for the ```selective case``` and ```condition values return```. The SQL program can working with ```multiple of data sources``` or ```data tables``` when it create of clean code by removed of duplicated data joined and conditions by simplify of calling method by target program and parameters. </br>
🦭💬 There is a trick and you can use them for new application developers, working with program is server codes and resource manage. Query for ```row_id``` and ```insert``` or ```update``` is correct but working with ```server resource management``` sometimes it is preserved delays process working with records. You can manage clients by ```time schedule``` or ```manual process``` for last update record or ```server manage resources```. </br>

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

🐑💬 ➰ Python code has the advantage of ```short-form``` iteration and ```alpha function``` when you can manage this dataset with simple code and easy to understand. There is a data header you can read from the return object property but its values are aligned on the execution object. Extraction of columns header values from the columnnames property is possible but we need to sort by preferable order as in report form. Creating the ```configuration file settings``` with column names and required field names is suitable and helps when ```application migration```. </br>
🧸💬 You can create many temporary tables and programs as long as ```sufficient resources``` and ```disk space``` for target system resource management. Sometimes applications have slower calculation speeds that are because they cannot create temporary tables and they need to do their operation records in the ```existing temporary table```, we need to have a process to validate and ```create a table for calculation```. </br>
🐐💬 Some applications require to ```create object permission``` that is because of ```recourse issues``` and ```user authority```. Without using temporary tables or programs that is application works for dataset return and SQL command operations. The security level can determine SQL execution commands by the filter and can categorize command execution by the table name, join operation, condition, and where cause. ```How much intention to use target system for survival operations police have some desirable plan to determine from this method. 👮``` </br>

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

## Increase of connection pool size ( make sure you have client and server codes managed)

🧸💬 It is not speed hacking or connectivity bandwidth expansion, sometimes the updated number of current connectivity changes because of the increased number of connection pool sizes. There is an SQL command to reset all sessions and start counting a number of connectivity or update the data tables but that is not a good practice. You should add the connection pool sizes after a new connection or restart of the services. </br>
🦭💬 You can assign of data property into the connection or username or interactive fields as the connection object is a group of objects, properties, and activity updates. Sometimes we use the connection object to communicate with programs or external applications we manage them as messages. These messages are not only text and property because of interactions objects are a group of objects and properties with pre-defined values and manage that sufficiently to create responses in the same manner. ```Observe the API property they are designed for the same communication method response``` and connection and can perform database connectivity and database communication with error codes and status codes. </br>
</br>
🐐💬 This is a trick for communication API or opening an incident ticket to confirm with IT technical support because of good start makes your codes managible. </br>
</br>
🐑💬 ➰ The example of an ```internal function``` that I can remove at any time and aware by programmers ```pool._set_pool_size(5);``` . This means a programmer of API allows you to manage application property or resources but it is internally managed and can be removed at any time. ```Quite is works easy.``` </br>

```
connection = None;
guests = ["Anna", "Marcos", "Diana", "Joakim", "Hiroki"];

pool = MySQLConnectionPool( pool_name="little_lemon_pool", pool_size=3, host="localhost",
		database=database, username=username, password=password );

for i in range( pool.pool_size ):

    try: 
        connection = pool.get_connection();
        if connection.is_connected() :
            cursor = connection.cursor();
        else :
            connection  = connector.connect( user=username, password=password );

        print( "Poolname: ", pool.pool_name, " number of connection(s): ", i, " user: ", guests[i] );

    except connector.Error as errorcodes :
        if errorcodes.errno ==  errorcode.ER_ACCESS_DENIED_ERROR :
            print( connection.is_connected(), "ER_ACCESS_DENIED_ERROR" );
        elif errorcodes.errno ==  errorcode.ER_BAD_DB_ERROR :
            print( connection.is_connected(), "ER_BAD_DB_ERROR" );
        else :
            print( errorcodes.errno, errorcodes.msg );

print( "Current connection(s) in pool: ", pool.pool_size );
current_users = pool.pool_size;
pool._set_pool_size(5);

new_connection  = connector.connect( user=username, password=password );
new_connection_2  = connector.connect( user=username, password=password );
pool.add_connection( new_connection );
pool.add_connection( new_connection_2 );

for i in range( pool.pool_size - current_users ):

    try: 
        connection = pool.get_connection();
        if connection.is_connected() :
            cursor = connection.cursor();
        else :
            connection  = connector.connect( user=username, password=password );

        print( "Poolname: ", pool.pool_name, " number of connection(s): ", current_users + i, " user: ",
		guests[current_users + i] );

    except connector.Error as errorcodes :
        if errorcodes.errno ==  errorcode.ER_ACCESS_DENIED_ERROR :
            print( connection.is_connected(), "ER_ACCESS_DENIED_ERROR" );
        elif errorcodes.errno ==  errorcode.ER_BAD_DB_ERROR :
            print( connection.is_connected(), "ER_BAD_DB_ERROR" );
        else :
            print( errorcodes.errno, errorcodes.msg );

print( "Current connection(s) in pool: ", pool.pool_size );
```

### Results output

```
Poolname:  little_lemon_pool  number of connection(s):  0  user:  Anna
Poolname:  little_lemon_pool  number of connection(s):  1  user:  Marcos
Poolname:  little_lemon_pool  number of connection(s):  2  user:  Diana
Current connection(s) in pool:  3
Poolname:  little_lemon_pool  number of connection(s):  3  user:  Joakim
Poolname:  little_lemon_pool  number of connection(s):  4  user:  Hiroki
Current connection(s) in pool:  5
```

## Analysis reports

💃( 👩‍🏫 )💬 ```Analysis report``` is a tool for ```data extraction``` from prepared statements and data information, SQL program can create ```multiple data dimensions``` by its programming like behavior, conditions, and where causes. </br>
🦤💬 Analysis reports they are using in ```automation processes``` such as summarize or total reports, simple data records variation is compared with aggregated data from different sources or methods. Import and ```aggregate data``` results have error record numbers or total numbers that can ```automatically be detected``` and then compared to each record whenever required. </br> 
💃( 👩‍🏫 )💬 This method is an interesting method and some verification records methods such as sample records and find records uniqueness by ```statistics methods``` such as records ```quantization``` or ```data records representing percentile```. </br>
🦤💬 On program screen results there are a few columns resultset with numbers representing a percentile of random selection unique records, minimum, maximum, and target summarized. ```Acceleration of calculation speed``` is a trick of quantization statistics and ```enabled program functions``` in ```R``` and ```Python language``` function enabled for their dataset. </br>

### Summary report

🧸💬 Basics ```store procedure``` with ```Python language``` basics statistics function, selection of appropriate function, and use of the procedure for ```delays response process```. Selection by procedure has an ```advantage over queue messages``` for data selection from target objects in the database. </br>
🐑💬 ➰ By application ```insert``` and ```update``` data records operations are using SQL procedure, benefits of the delayed message, access control, ```server manage resources```, ```success results return guarantee```, and ```multiple-session accessibility```. Creating a store procedure for data selection is performed in one of the item checklists for ```database process task optimization```. </br>
🐐💬 You know about system procedures and user program procedures that applications create for ```data services``` and ```reports```, they are insert of data fields with ```indexes``` and ```unique names``` for control of data manipulation and insertion of ```random selection codes``` as one of the objectives to ```prevent external code specification```. Applicable them also control of ```user access``` and ```user response``` for different user groups and authorized users. 👻👻👻 Booo.~  </br>

```
# Task 4:
# Create a stored procedure named BasicSalesReport that returns the following statistics: 
import statistics;

# Total sales

# Average sale

# Minimum bill paid

# Maximum bill paid

cursor.execute("DROP PROCEDURE IF EXISTS BasicSalesReport;");

Role = "Manager";
SQL_database_bookings_pc_basicsalesreport = f"""
CREATE PROCEDURE BasicSalesReport(  ) 
	BEGIN  
        SELECT OrderID, TableNo, Quantity, BillAmount
        FROM Orders;
    END
"""

try:
    current_connection = get_connection_frompool( );
    cursor = current_connection.cursor();

    cursor.execute( SQL_database_littlelemon_use );
    result = cursor.fetchall();

    cursor.execute( SHOW_TABLES );
    tables = cursor.fetchall();

    if "Orders" not in [ x[0] for x in tables ] :
        print( "Please create database table Orders." );
        quit;
    else:

        #### Execution SQL query statements by Python program. ######################
        cursor.execute( SQL_database_bookings_pc_basicsalesreport );
        cursor.callproc("BasicSalesReport");

        resultset = next(cursor.stored_results());
        resultset = resultset.fetchall();

        columnnames = [ x.description for x in cursor.stored_results() ];
        columnnames = [ a for ( a, b, c, d, e, f, g, h, i ) in columnnames[0] ];

        Maximum_billamount = max([ BillAmount for OrderID, TableNo, Quantity, BillAmount in resultset ]);
        Minimum_billamount = min([ BillAmount for OrderID, TableNo, Quantity, BillAmount in resultset ]);
        Average_billamount = statistics.mean([ BillAmount for OrderID, TableNo, Quantity, BillAmount in resultset ]);
        Summary_billamount = sum([ BillAmount for OrderID, TableNo, Quantity, BillAmount in resultset ]);

        print( "Report name: ", " SQL_database_bookings_pc_basicsalesreport ");
        print( columnnames );
        print( resultset );
        print( "#############################################################################" );
        print( "Maximum_billamount: ", round(Maximum_billamount * 1.000, 2), " $" );
        print( "Minimum_billamount: ", round(Minimum_billamount * 1.000, 2), " $" );
        print( "Average_billamount: ", round(Average_billamount * 1.000, 2), " $" );
        print( "Summary_billamount: ", Summary_billamount, " $" );
        #############################################################################
    
except current_connection.Error as errorcodes : 
    print( errorcodes.errno, errorcodes.msg );
```

### Results output

```
Report name:   SQL_database_bookings_pc_basicsalesreport 
['OrderID', 'TableNo', 'Quantity', 'BillAmount']
[(1, 12, 2, 86), (2, 19, 1, 37), (3, 15, 1, 37), (4, 5, 1, 40), (5, 8, 1, 43)]
#############################################################################
Maximum_billamount:  86.0  $
Minimum_billamount:  37.0  $
Average_billamount:  48.6  $
Summary_billamount:  243  $
```

### Plain-text report

🧸💬 ```CHAR NUMBER``` is one method for print text-report creation, there is some understanding about character fields even in programming language, and the data selection display screen needs to indicate the number of characters to display from target fields as naturally perform as a file-based system. </br>
🐐💬 ```DO NOT exceed``` the input number but the analysis field enabled the verification method because exceeding the range of the number may create a negative number for the next summarization and display, enable the analysis feature, or disable and compare. </br>
🐑💬 ➰ ```LIMIT``` the number of resultsets returned to save the process of performance when working with the file system because most of the application users locked files when using them, they can request for authorization but when the user is a process the authorized user is important. </br>

```
# Task 5:
# Little Lemon needs to display the next three upcoming bookings from the Bookings table on the kitchen screen to notify
# their chefs which orders are due next.

# Get a connection from the pool.
current_connection = get_connection_frompool( );

# Create a buffered cursor.
cursor = current_connection.cursor(buffered=False);

# Combine the data from the Bookings and the Employee tables. Sort the retrieved records in ascending order.
# Then display the information of the first three guests.

SQL_database_booking_employee_TOP3 = """
SELECT Bookings.BookingID, Bookings.TableNo, Bookings.GuestFirstName, 
    Bookings.GuestLastName, Bookings.BookingSlot, Employees.Name, Employees.Role

FROM Bookings, Employees
WHERE Bookings.EmployeeID = Employees.EmployeeID

ORDER BY BookingSlot, BookingID
LIMIT 3;
"""

try:
    cursor.execute( SQL_database_littlelemon_use );
    result = cursor.fetchall();

    cursor.execute( SHOW_TABLES );
    tables = cursor.fetchall();

    if "Employees" not in [ x[0] for x in tables ] :
        print( "Please create database table Employees." );
        quit;

    if "Bookings" not in [ x[0] for x in tables ] :
        print( "Please create database table Bookings." );
        quit;
    else:

        #### Execution SQL query statements by Python program. ######################
        cursor.execute( SQL_database_booking_employee_TOP3 );
        resultset = cursor.fetchall();

        print( cursor.column_names );
        
        for item in resultset :
            ( BookingID, TableNo, GuestFirstName, GuestLastName, BookingSlot, EmployeeName, EmployeeRole ) = item;
            
            CHARNUM = 25;
            GuestFullNmae = GuestFirstName + " " + GuestLastName;
            GuestFullNmae = GuestFullNmae + "".join( [" "] * ( CHARNUM - len(GuestFullNmae) ) );

            EmployeeName = EmployeeName + "".join( [" "] * ( CHARNUM - len(EmployeeName) ) );
            
            # print( "BookingID: ", str(BookingID).zfill(2), " TableNo: ", str(TableNo).zfill(2), " GuestFullNmae: ",
	    # GuestFullNmae, " BookingSlot: ", BookingSlot,
            #        " EmployeeName: ", EmployeeName, " EmployeeRole: ", EmployeeRole);


            message = f"""
            [{ BookingSlot }]

            [{ GuestFullNmae }]

            [Assigned to: { EmployeeName } [{ EmployeeRole }]]
            """
            print( message );

    
except current_connection.Error as errorcodes : 
    print( errorcodes.errno, errorcodes.msg );

current_connection.close();
```

### Results output

```
Poolname:  pool_b  number of connection(s):  2
('BookingID', 'TableNo', 'GuestFirstName', 'GuestLastName', 'BookingSlot', 'Name', 'Role')

            [15:00:00]

            [Vanessa McCarthy         ]

            [Assigned to: Giorgos Dioudis           [Head Chef]]
            

            [17:30:00]

            [Marcos Romero            ]

            [Assigned to: Fatma Kaya                [Assistant Chef]]
            

            [18:00:00]

            [Anees Java               ]

            [Assigned to: John Millar               [Receptionist]]
```
