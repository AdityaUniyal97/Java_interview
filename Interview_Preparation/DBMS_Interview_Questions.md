
# What is SQL
<u><b>SQL(Structure Querry Language)</b></u> Is a language to communcaite with the database . SQL , is used to create , retrieve , update and manages the data in a database . For example , you can use SQL to add data , get specific data or update exisiting data.

# What is DBMS ?
<u><b>DBMS(Data base Management System)</b></u> DBMS
# What are the adavntages of DBMS over traditional file-based systems ?
A Data Base Management System(DBMS) is much better than storing data in a regular file because it keeps all your data at one centralised place . This reduces have the same data in multiple files reducing the data redundency . It also make retriving and updating the data veyr easy task since we can use some powerful querries rather than manually searching it in multiple files. DBMS handles the data security and data authorization . 

# What are Super, Primary, Candidate and Foregn Keys ?
<u><b>Super-Key</b></u> is any set of column that can uniquley indentify any row in a table.
<u><b>Candidate-Key</b></u> it is minimal Super key meaning that it has no extra column that are'nt needed for uniquekly identification
<u><b>Primary Key</b></u> is the key that the data base uses it to identify the rows uniquely.
<u><b>Foregn-Key</b></u> is a column or the set of column that points to the primary key of the other table creating a link between two tables.

# What are the difference between the Primary Key and the Unique Key Constratins ?
<u><b>Primary Key</b></u> should always be inilistialised with some values (no NULL vlaues allowed) and we can only have one primary key as per the table .
<u><b>Unique Constraint</b></u> ensure that no two rows have the smae vlaue in that column , but it allows the NULL values . Also a table can have multiple unique constrains.

# What is a Database Normalisation ?
Database Normalisation is the process of organising the tables and comuns to reduce the data repeatation (or the Data redundancy) and other problems while inserting, updating or deleting the data.
What we do in Normalisation is that we split our two large tables into smaller linked tables , we make sure that each piece of data is stored only once in the best place .This helps to keep the data base consistent and makes it easier to make changes into it.

# Why is the use of DBMS recommended ? List Some major adavtanges.
<u><b>Controlled Redundency</b></u> Data is only stored once in a central location which avoid dupplications.
<u><b>Data Sharing</b></u> Many users can share the same data base without any confolicts
<u><b>Backup and Recovery</b></u> Automatic Backup system save your data from being lost if something goes wrong
<u><b>Integrety and Constraints</b></u> System apply some rules so that unknown data doesnt get stored into our data base

# What is the difference between the DDL , DML , and DCL in SQL ?
<u><b>DDL(Data Defiantion Language)</b></u> Commands like <u>CREATE</u> , <u>ALTER</u> , <u>DROP</u> that defines or chanegs your database structure.
<u><b>DML(Data Manipulation Language)</b></u> Commands like the <u>SELECT</u> , <u>INSERT</u> , <u>UPDATE</u> , <u>DELETE</u> that actually handles your data.
<u><b>DCL(Data Control Language)</b></u> Commands like <u> GRANT </u> and <u>REVOKE</u> that manages users permissions and access

# What is the difference between HAVING and WHERE clause ?
<u><b>WHERE</b></u>  is used to filter rows before grouping . It does not work with aggregte function like <u>SUM()</u> or <u>COUNT()</u> 
<u><b>HAVING</b></u> used to filter the groups after grouping . It can use aggregate functions to filter reult.

# How to print the dupplicate Rows in a table ?
We can use Group by clause combined with the Having Clause to find the dupplicates
```
SELECT column_name , COUNT(*)
FROM table_name
GROUP BY column_name
HAVING COUNT(*) > 1
```

# What is Join ?
A join combines rows from two or more tables based on common column in those table . For example If both table have a common column named as the <u>Enroll_No</u> , than join will line up the rows that share the smae <u>Enroll.No</u> 

# 
