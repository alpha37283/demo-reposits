

# Relational databases

Entity 
Attributes 

# Database Integrity or data integrity

Entity integrity 
Referentaial integrity 
Domain inegrity // domain ->acceptable value for a column, range of inputs or available datatypes 

# Atomic values

like from changing only NAME to first name, last name, and mid name

# Database Relationships 

# Designing relationships 

1:1
both entities in same table

1:N
entities separate in two tables, FK used

M:N
- we face the issue of empty spaces left like in student and classes example 
# sol break them into 1:N relationships 
1. use intermediary table or JUNCTIONS 


# -------------Keys-------------

keep everything unique

# Look up TABLE 
we create another table for reference of some sold stored data, solid means 
fixed or constant that we dont want to change. Like we can store subject and their ids in a table name sub and then student which is main table can reference to it. 

# Super key 

collection of one or more column with attribute which forces every row to be UNIQUE 


# Candidate key 
least number of columns 

like minimum number of columns to make a row unique for example in user table user_name is enough to make a row unique 

Q to be ask : can every row be unique -> how many columns do we need to make it unique (min/least)

# Primary key and Alternate keys

pk : unique, not changing, not null 

ak : candidate keys that aren't selected as primary keys (alternative/ can be used)


# Surrogate and natural (categories of primary keys )

sorrogate : factless key 


# ---------- Foreign key ---------

foreign key references PRIMARY KEY

and that is the reason we want it sometimes NOT NULL  
# NOT NULL PRIMARY KEYS 
Primary values never change 
FK values can change 
# FK Constraints 

1. what happens to parent also happens to child 
ON DELETE : when update parent we want to children to do something 
ON UPDATE : when update parent childeren also updated

2. only child takes affect 
RESTRICT 
CASCADE : both takes affect child and parent 
SET NULL 

ALL three works with upper two like 
ON DELETE RESTRICT : stop being delete the parent 

# Simple, Composite and Compound keys 

Composite : common with natural keys, two or more coloumns 

Compound keys : when a key has multiple columns and those are all keys. All columns has to be keys 
like in junction or intermediary table 