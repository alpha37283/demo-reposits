# password is password


# (not working) popSQL text editor interactive for SQL
# instead use MYSQL Workbench

# -----------------------Basic Database info----------------------- 

SELECT @@PORT AS 'Port', @@VERSION AS 'Version';   => port on running 
SHOW VARIABLES LIKE 'hostname';
SHOW VARIABLES LIKE 'host';
SELECT USER();    => user name used to connect ot MYSQL server 

DESCRIBE table; //  shows colomn used

SHOW DATABASES;  // shows list of databases




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

ALTER TABLE table_name RENAME COLOMN prev_name TO new_name;

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









# -------------------------COMPANY DATABASE STARTS-----------------------


FOREIGN KEY => stores PRIMARY KEY of another table 
COMPOUND PRIMARY KEY OR COMPOSITE KEY => mixture of 2 keys making Unique key 




# Queries Fig 5

CREATE TABLE Employee( emp_id INT PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
birth DATE,
sex VARCHAR(1),
salary INT,
supid INT,
branch_id INT);

SELECT * FROM employee;

CREATE TABLE branch(branch_id INT PRIMARY KEY, 
branch_name VARCHAR(20) NOT NULL, mgr_id INT,
mgr_start_date DATE NOT NULL,
FOREIGN KEY (mgr_id) REFERENCES employee(emp_id) ON DELETE SET NULL 
);


ALTER TABLE employee ADD FOREIGN KEY (branch_id) REFERENCES branch(branch_id);
ALTER TABLE employee ADD FOREIGN KEY (supid) REFERENCES employee(emp_id) ON DELETE SET NULL;


CREATE TABLE client (client_id INT PRIMARY KEY,
client_name VARCHAR(50) NOT NULL,
branch_id INT,
FOREIGN KEY (branch_id) REFERENCES branch(branch_id) ON DELETE SET NULL);




CREATE TABLE works_with( 
emp_id INT,
client_id INT,
total_sales INT,
PRIMARY KEY(emp_id, client_id),
FOREIGN KEY (emp_id) REFERENCES employee(emp_id) ON DELETE CASCADE,
FOREIGN KEY (client_id) REFERENCES client(client_id) ON DELETE CASCADE);

CREATE TABLE branch_supplier(
branch_id INT,
supplier_name VARCHAR(50),
supplier_type VARCHAR(50),
PRIMARY KEY(branch_id, supplier_name),
FOREIGN KEY (branch_id) REFERENCES branch(branch_id) ON DELETE CASCADE);



# INSERRTING DATA IN ORDER




INSERT INTO employee (emp_id, first_name, last_name, birth, sex, salary, supid, branch_id) VALUES 
(100, 'Alice', 'Smith', '1985-05-15', 'F', 90000, NULL, NULL);

INSERT INTO employee (emp_id, first_name, last_name, birth, sex, salary, supid, branch_id) VALUES 
(106, 'Bob', 'Johnson', '1991-09-22', 'M', 85000, 106, NULL);

INSERT INTO employee (emp_id, first_name, last_name, birth, sex, salary, supid, branch_id) VALUES 
(102, 'Carol', 'Williams', '1987-11-30', 'F', 80000, 102, NULL);

INSERT INTO branch (branch_id, branch_name, mgr_id, mgr_start_date) VALUES (1, 'CORPORATE', 100, '2006-10-06');
INSERT INTO branch (branch_id, branch_name, mgr_id, mgr_start_date) VALUES (2, 'SCRANTON', 102, '2005-11-19');
INSERT INTO branch (branch_id, branch_name, mgr_id, mgr_start_date) VALUES (3, 'STAMFORD', 106, '1998-02-13');



INSERT INTO employee (emp_id, first_name, last_name, birth, sex, salary, supid, branch_id) VALUES
(101, 'JAN', 'LEVINSON', '1961-05-11', 'F', 110000, 100, NULL),
(103, 'Michael', 'Scott', '1964-03-15', 'M', 95000, 102, NULL),
(104, 'Dwight', 'Schrute', '1970-01-20', 'M', 85000, 106, NULL),
(105, 'Jim', 'Halpert', '1978-10-01', 'M', 78000, 100, NULL),
(107, 'Pam', 'Beesly', '1979-03-25', 'F', 60000, 102, NULL),
(108, 'Ryan', 'Howard', '1983-05-05', 'M', 50000, 106, NULL),
(109, 'Andy', 'Bernard', '1973-07-16', 'M', 65000, 100, NULL),
(110, 'Stanley', 'Hudson', '1958-02-19', 'M', 72000, 102, NULL),
(111, 'Kevin', 'Malone', '1968-06-01', 'M', 62000, 106, NULL),
(112, 'Angela', 'Martin', '1971-11-11', 'F', 68000, 100, NULL);



# -----------------------SOME KEYWORDS-----------------------

1. LIMIT
2. AS
3. DISTINCT  -> categorizes the same like if there are multiple F AND M 

4. MODIFY to modify table datatypes and constraints


# ----------------------SQL FUNCTIONS-----------------------


1. COUNT(emp_id) will tell how many employee ids are there
Find number of employee 

SELECT COUNT (emp_id) from employee;

2. Count number of females born after 1970 

SELECT COUNT(emp_id) from employee WHERE SEX = 'F' AND birth > '1970-01-01';

3. AVG(column_name)
4. SUM(column_name like salary)

5. AGGREGATE Functions

how many males and females are there

SELECT COUNT(sex), sex from employee GROUP BY sex or column;

SUM OF TOTAL SALESMAN SALES

SELECT SUM(total_sales), emp_id FROM works_with
GROUP BY emp_id;



# ---------------------WILD CARDS-------------------------

LIKE KEYWORDS WITH wildcards use to find marching pattern  


%-> any numbers any characters but ends with SOMETHING 
_-> one character


SELECT * FROM client WHERE client_name LIKE 

'%LLC' -> present at the end 

'% LLC%' -> present somewhere

for dates someone born in OCTOBER
'_____-10%' -> 4 characters and then -10



# ------------------------UNIONS------------------------

Combine information of two columns 

rule.
i.  same number of columns must be select
ii. similar data types of columns 

SELECT ALL SUPPLIER AND CLIENTS NAMES;

FIND THE MONEY COMPANY EARNED AND SPENT

SELECT salary FROM employee UNION SELECT total_sales from works_with; 


# ------------------------JOINTS------------------------

combines two or more rows based on JOINED COLOMNS related 

INSERT INTO branch(4, 'BUFFALO',NULL, NULL);

    Q. FIND ALL BRANCHES AND THEIR MANAGERS

SELECT employee.emp_id, employee.first_name, employee_last_name FROM employee JOIN branch ON branch.mgr_id = emp_id;   // manager of some branch is some person 


4 types of JOINS

1. GENERAL JOIN or inner join
when some column has same common or shared
2. LEFT 
all of the rows inclued from the left column like here emp_id 

3. RIGHT 
OPPOSITE of the left 
ALL ROWS FROM THE RIGHT table column 

4. FULL OUTER JOIN not implemented in SQL 

# -------------NESTED QUERIES-------------------

multiple select statements to get a piece of statements

Q.  find names of all employees who have sold more then 30000 to a client single 


USING OTHER KEYWORDS LIKE IN(another query)


Q. find with which client manager id 102 works  with

first we find at which branch manager 102 works 

then 

SELECT branch.branch_Id WHERE manager_id = 102;

SELECT client_name FROM client WHERE branch_id = (SELECT branch.branch_id WHERE mgr_id = 102);


# -------------ON DELETE-----------------------

deleting entries when entries are associated with other foreign keys 

ON DELETE SET NULL => if we delete on employee then other foreign key is going to set NULL

ON DELETE SET NULL => instead the whole associated ROW is going to be deleted