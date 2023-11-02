# FOREIGN KEY AND JOINS
: WE CAN HAVE A FULL TABLE WILL car AND person ATTRIBUTES

FOREIGN KEY: links two primary keys that must be same data types

# ADDING RELATIONSHIPS BETWEEN TABLES

check coding Screen shot;

# UPDATING VALUES (embedding)

UPDATE person SET (colomnofsecondtable) id = 1 WHERE id = 1;

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