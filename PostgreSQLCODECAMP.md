Documentaion: https://www.postgresql.org/docs/current/index.html


Installing....

Password Setup

GUI vs Terminal Component

Creating a DataBase:

exit out of psql



List of servers: list \l

Creating a database: 
before creating database, return out of psql
1)CREAT DATABASE databaseName; 


Connecting to DataBase: 
1)\c servername
another way to connect a database
2)psql -l localhost(use ip address if you trying to connect to a remote server) -p portNumber -U username name(isk why here is name again)

Deleting a database:
DROP DATABASE datbase name;   //  dangerous bcz all content lost, everthing

Creating Table: without constraints 
CREATE TABLE table_name ( 
	Coloumn name + data type + constraints if any
)

# Display table:
1) \d -> shows list of table
2) \d tableName
3) \dt 
4) SELECT * FROM person;


# Deleting a table: DROP TABLE tableName;

# Creating Table: with constraints 
CREATE TABLE tebleName(
Constraits 
NULL KEY: dont accept NULL value
PRIMARY KEY:
)

# id_sequence: will be generated if you are using BIGSERIAL: auto increment number, dont have to remember previous number.


# Insert into:
INSERT INTO tablename (parameters of table) // dont put simcolon
VALUES( crossposning values to paramters);



\i file path(with / slash)



# Select From:
SELECT * FROM tableName;     // * means every single coloumn from the table
SELECT colname FROM tableName;



# How to Sort:
#Using Order By
	Order By keyword = result will be ascending or descending, by default it will be Ascending
1 2 3 4 5 ASC
5 4 3 2 1 DESC
SELECT * FROM person ORDER BY nameOfColoumn ASC/DESC;



# Distinct: when we want a unique entity in colomn of a table
SELECT DISTINCT colomnName FROM tableName ORDER BY colomnName ASC/DSC;
Duplicate entities will be shown once/mot multipbe;



# Where Clause : filter data base on condition
SELECT * FROM tableName WHERE condition;
SELECT * FROM tableName WHERE gender = 'Female';

# Multiple Condition:
SELECT * FROM tableName WHERE condition AND condition ;




# Comparison Operators 
< , > 
<> => Not equal to 
SELECT 1<2;

# LIMIT KEYWORD : We want to select first 10 rows from table
SELECT * FROM tableNama LIMIT 10; // limit result by 10

# OFFSET actual limit: very first 5 rows after certain index/row;
SELECT * FROM tableName OFFSET 5 LIMIT 5; 
start from 5 + 5 more rows (check screen shot)

# fetch 
SELECT * FROM tableName OFFSET 5 FETCH FIRST 5 ROW ONLY;

# In
shortens the condtitinal statements 
SELECT * FROM person WHERE coloumnName IN('CHAINA','FRANCE','BRAZIL')
ORDER BY coloumnName;

# Between: Select data from range;
SELECT * FROM tablename WHERE coloumn name BETWEEN 'range' AND 'range';

#Like and iLiken: match text patterns
SELECT * FROM tableName LIKE 'pattern'; (screen shot)
'%.com' => any chracter followed by .com
'%@gmail.com' => any chracter followed by @gmail.com

lets say we want to check gmail users from country france

SELECT * FROM person WHERE email LIKE '%gmail.com' AND first_Name LIKE '%S';

# % called wild card

another method is _ underscore: says this has to match single characters 
e.g., 
WHERE email LIKE '_____@gmail.com'

# iLike Ignores the CASE Sensitive











