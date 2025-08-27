same for this also ## Data 
- Data referes to raw , unprocessed facts and figures . 
- It can exists in forms such as number , text , symbols , images and sound
- Data doesn't carry speicifc meaning by itself
## Information 
- Information is the data that is processed and organised in a way that it becoems meaningfull
## DataBase
- DB is like a container that stores the related data
- DataBase are of two types :=>
- **Structured** Hese the data is organised into the form of Rows and coulmns , RDBMS(Relation Data Base Management System) , ex = IRTC
- **Unstructured**  is the data which is not have any predefined arrangemement , like WEB PAGE which have image , text , number etc
## DBMS
DBMS is a management system through which we can perform CURD operation into our relational data base
ex = SQL Server , Oracle , MySql

**Advatnage of DBMS**
- Data Sharing = Multiple users can access the same data base
- Data Security = Access control and authentication system , keeps the data secure
- Reduce data Redundency = Avoid data repetations 
**Diadvantage of DBMS**
- High Cost = mainting the dbms software can be expnesive tasks
- Complexity = Complex system
- Maintainence Requires = Require regular backups 
## File System vs DBMS
**File System**
- Stores the data in files and folders
- Has high data redundency(means data repeatness)
- No strong security anyone with access can see the data
**DBMS**
- Stores the data in the databases software for management
- No data redundency
- Searching of data is fast due to the Sql Commands
- Strong Security only authorized users are allowed to access the data.

## DBMS Architecture 
DBMS architecutre is designed in a way to make the data structure and organised
### Layers of DBMS
**Tier One Architecture** 
- Here the data base is directly accessed by the user  without interacting with any layers
**Two Tier Architecture** 
- It has two layers Clients and DataBase.
- The client directly communicate with the databse
- It is simple and fast for small systems but less secure
**Three Tier Architecture**
- It has three layers Client , Application Server , data base
- The Client talks to the application server , which than communicate with the data base
- It is more secure , scalabale for large multi user application 

## Data Abstraction
- Data Abstraction means hiding the complexities of data base and exposing only essential feature to the user
- It allows the uses to interact with the data base without needed to understand the underlying complixities

**Levels of Data Abstraction** 
- **Physical Level(Internal  Layer)** = defines how the data is stored in the data base , including storage methods , indexing and file organisation . It foucses on the low level details.
- **Logical Level(Conceptual Layer)** = defines what data is stored and the relationships between them without specifying how they are stored
- **View Level(External Layer)** = this level is the heighest level of data abstraction that provide user specific view of the data. 

## Data Base Schemas 
   It is a structural design that defines how the data is organised , stored and accessed within a data base
- **Physical Schema** Defines how the data is physically stored in the storage devices.
    EX - Files Paths , Indexing methods
- **Logical Schema** Defines the table , attribute , data types , relationship 
- **View Schema** Defines how user sees the data
    EX = A student can see their marks , while teacher can see all the students marks

## Data base USERS 
### Types of the Data base users

**1 DataBase Administrator(DBA)** 
A DBA is a person responsible for managing , controlling and maintaing the  data base systems.
They make sure the database is:
- Secure
- Available
- Efficient
- Reliable
**Main Functions of DBA**
**Data base Design** 
- Helps in creating schemas , tables and relationship
- Ensure the design supports bussiness requirements
**User Access & Security**
- Creates the user accounts 
- Grants the permission(who can read / write / update / delete)
**Backup & Recovery**
- Maintains regular backups 
- Restores data base in case of crash , data loss or corruption
**2 End Users**
End users are the people who actually uses the database to perfrom operations like , retriving , entering , or updating data
**Types of End Users**
**Naive Users** 
- Use the predefined application
- Dont know the SQL or databse details
- Ex = Railway ticket booking system
**Casual Users**
- Acess the data base occasionally
- run simple querries 
- Ex = Student checking thier result
**3 Appplication Programmers** 
- they write the complex SQL queires
- Knows how the data will work internally
- EX = DATA Scientist analyszies the data
**4 Specialized Users**
- Works on the special purpose data bse like AI , ML etc
- Write thier own program to interact with the DB
- EX = Research