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
DROP DATABASE database name;   //  dangerous bcz all content lost, everthing

Creating Table: without constraints 
CREATE TABLE table_name ( 
	Coloumn name + data type + constraints if any
)

# Display table:
1) \d -> shows list of table
2) \t tableName
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

# Like and iLiken: match text patterns
SELECT * FROM tableName LIKE 'pattern'; (screen shot)
'%.com' => any chracter followed by .com
'%@gmail.com' => any chracter followed by @gmail.com

lets say we want to check gmail users from country france

SELECT * FROM person WHERE email LIKE '%gmail.com' AND first_Name LIKE '%S';

# % called wild card

another method is _ underscore: says this has to match single characters 
e.g., 
WHERE email LIKE '_____@gmail.com'

iLike Ignores the CASE Sensitive

# Aggregate Functions like COUNT(*)


# GROUP BY and COUNT(*)

SELECT coloumnToGroup,COUNT(*) FROM person GROUP BY coulomnName;

# GROUP BY HAVING
: Provides extra filtering 
HAVING keyword must be before ORDER BY
SELECT coloumnToGroup,COUNT(*) FROM person GROUP BY coulomnName HAVING COUNT(*) > 5 ;  // COUNT(*) > 5 is a condition

# MAX(colomn name) MIN and AVG ROUND(AVG(price)) 
# SUM(price or coloumn name)

# Arthmetic Operators + - * / %
Arthmetic operators ROUND 

SELECT id,make,price,ROUND(price * .10) FROM car; 10 percent discount on a car;

check screenshots

# ALIAS : AS
: if we dont specify colomn name, it will use ?colomn? or name of function to solve this problem 

# COALESCE 
: default value in case first is not present 
SELECT COALESCE(coloumn name, condition if null);  (null,null,1) try first, second and then 1

# NULLIF 
tackle division by 0
takes two argument, return 1st if second is not equal to first SELECT NULLIF(n,n); => false else true

# TIME STAMPS AND DATES
1) NOW();
2) SELECT NOW() :: DATE;

Adding Subtracting Dates 

a. SELECT NOW() - INTERVAL '1 YEAR/DAYS/MONTHS ';

# EXTRACTING FIELDS 
SLECT EXTRACT (year from now());

# AGE FUNCTONS
SELECT all other feilds,AGE(NOW(), date of birth) AS current_age FROM person 





# PRIMARY KEYS: allows store unique records
drop constraint
ALTER TABLE person DROP CONSTRAINT person_pkey; // AFTER THIS WE CAN ADD similer colomn data

ADDING PRIMARY KEY // but first remove same data rows
ALTER TABLE person ADD PRIMARY KEY (array of value of coloumn); // again adding priary key

DELETE FROM person WHERE ID = 1;

# UNIQUE CONSTRAINTS different from primary key
why:  where we have DUPLICATE DATA 
making coloumn unique
ALTER TABLE ADD CONSRAINT 'unique_email_Address' UNIQUE (email);    // making constraint unique
ALTER TABLE person ADD UNIQUE (email coloumn name);

# CHECK CONSTRAINTS
: allows constraint base on boolean condition 
allow only female and male matching string 

// first delete hello
ALTER TABLE person ADD CONSTRAINT gender_constraint CHECK (gender = 'male' or gender = 'female'); 





# DELETE records 
use primary key most of the time while deleting 

DELETE FROM tablename;   will delete everything

task: delete 3 females from nigeria 

# UPDATE RECORDS
update coloumn: often base on where clause

UPDATE person SET email = '    ' WHERE id = 'specific primary key';

update multiple coloumn
UPDATE person SET firstName = '',lastname ='', email = '' WHERE id = '';

# ON CONFLICT DO NOTHING 
// e.g., insert with same id will show error: DUPLICATE KEY VALUE then

ON CONFLICT (id) DO NOTHING; // will do nothing 

# UPSERT check SS
if we want to do something else instead DO NOTHING on error 

DO UPDATE SET email = EXCLUDED.email 

task: change email of a specfic id




