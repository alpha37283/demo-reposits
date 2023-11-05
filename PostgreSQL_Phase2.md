# FOREIGN KEY AND JOINS
: WE CAN HAVE A FULL TABLE WILL car AND person ATTRIBUTES

FOREIGN KEY: links two primary keys that must be same data types

# ADDING RELATIONSHIPS BETWEEN TABLES

check coding Screen shot;

# UPDATING VALUES (embedding)

UPDATE person SET (colomnofsecondtable) car_id = 1 WHERE id = 1; // an example

# INNER JOINTS: Combines two tables 
: takes whatever common in both for example id then a + b = c c is new table

SELECT * from person
JOIN car ON person.car_id = car.id;

=>    /x expanded display on;

# LEFT joins
: crossponding relationship whether exist or not 

SELECT * from person
LEFT JOIN car ON person.car_id = car.id;

# DELETING RECORDS WITH FOREIGN KEY


# Exporting QUERY results to CSV

select data: MAKE A LEFT JOIN TO OTHER TABLE generate C TABLE 

/COPY command (JOIN TABLE C) TO '/Users/Desktopo/......./results.csv' DELIMITER ',' CSV HEADER;

# Serial and Sequences
big serial : auto increment numbers and that is integer

nextval('person_by_seq'::regclass); is a function that increments that BIGSERIAL;

ALTER SEQUENCE person_id_seq RESETART WITH value_of_Start;

# EXTENTIONS 
SELECT * FROM pg_a;   // basically are functions that provide extra funtionality to our database 

plv8
ssl


# Universally Uniqu Identifier 
- Different Versions
uuid__ossp
install exention for it

CREATE EXTENTION IF NOT EXISTS "uuid_ossp";
SLECECT * FROM pg_available_extentions;

# how to generate uuid with  Universally Uniqu Identifier 

to generate uuid we have to invoke a functions with command \df will show aviable function for uuid

we will invoke version 4

SELECT uuid_generate_v4(); // will always generate different id
could be use instead ids bigInt or Bigserial;

global unique: migrate data across databases without any conflict 







