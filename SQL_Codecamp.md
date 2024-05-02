# password is password


# (not working) popSQL text editor interactive for SQL
# instead use MYSQL Workbench

# Basic Database info 

SELECT @@PORT AS 'Port', @@VERSION AS 'Version';   => port on running 
SHOW VARIABLES LIKE 'hostname';
SHOW VARIABLES LIKE 'host';
SELECT USER();    => user name used to connect ot MYSQL server 




# DATA TYPES 
INT 
DECIMAL(M,N) M IS THE TOTAL NUMBER OF DIGIT AND N IS DIGITS AFTER DECIMAL 
VARCHAR(L)
BLOB => large amount of binary data like IMAGES etc
DATE => YY-MM-DD
TIMESTAMP  => YY-MM-DD HH-MM-SS


USE DATABASE;
SHOW DATABASES; //DATABASE RUNNING ON SQL SERVER

# SOME BASIC SETTINGs

1.SET SQL_SAFE_UPDATES = 0; => while using UPDATE

# CREATING SCHEMA
CREATE TABLE TABLE_NAME(colomn name DATATYPE,colomn name DATATYPE....);

ALTER TABLE TABLE_NAME ADD COLOMN_NAME DATATYPE;

ALTER TABLE table_name DROP COLUMN column_name;

DESCRIBE TABLE_NAME;

SHOW TABLES;


# Constraints 

NOT NULL, comumn cannot be left NULL
UNIQUE, all entries must be unique like not two same ids
PRIMARY KEY : NOT NULL and also UNIQUE

DEFAULT 'value to insert'    => Giving default values when value is NULL automatically assgined

AUTO_INCREMENT   => data well get automatically increment 
 

Example: Fig 1

attributes:
id 
count
name
major
sem
cgpa

CREATE TABLE student(
id INT PRIMARY KEY UNIQUE,
cnt INT AUTO_INCREMENT UNIQUE,
nme varchar(20) NOT NULL,
major varchar(20) DEFAULT 'Undecided',
sem VARCHAR(5),
cgpa DECIMAL (3,2)
);



# Update 

UPDATE table_name 
SET column_name = 'to change', column_name2 = '2nd change'  => multiple colomn can be changed 
some condition like WHERE major = 'SE';   

Example Fig 2
UPDATE student 
SET major = 'IT MAIN'
WHERE sem > 4;

# DELETE 

DELETE FROM student
WHERE  logic/cocndition;

# OR AND >= <= ==  logic 

<>  THIS IS NOT EQUAL TO 

-- COMMENTS 

# GETTING INFORMATION FROM DATABASE  // SELECT KEYWORD

ORDER BY column_name DESC or ASC;  => Alphabetical or ascen or descend

LIMIT somenumber;   => Limiting result 

IN (group of values);
 
------------------->    Fig 4 IN

SELECT * FROM srtudent WHERE name IN(VALUES);  // select these values from student colomn name







