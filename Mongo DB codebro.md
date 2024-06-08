

# ------------- Install mongo db and mongosh -------------------


# ------------- basics 

show db 

use database_name

adding Collection 

db.createCollection("nameofcollection")  // like table 

db.dropDatabase()

2. Insert

let say stundent is a collection 

db.studentinsertOne(
    {
        name: "",
        age: 19,
        gpa: 3.2 
    }
)

db.student.find() // will print the collection in document
db.student.insertMany( 
    [               -> an array of collections 
        {           -> collection in array 

        },
        {

        }
    ]
)

3. Data Types

String 
int
Double
bool
Date
field of courses like list as value 
document  inside collection 

3. Sort and limit DOCUMENTS

db.student.find().sort(
    {
        name:1 or -1    -> name of field want to sort
    }
)

db.student.find().limit(n) n is number of documents

both SORT AND LIMIT at a time can be used