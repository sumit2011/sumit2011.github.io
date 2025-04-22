# MongoDb Basics

***Navigation system works on the concept of linked list.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## 1. Introduction:
mongo db is kind of database it is a nosql database it stores data in the form of files. the data is not structured which is a main advantage of this database.

### Database Catagories
  1. RDBMS: Mysql, oracle, Sql server (handle only structured data)
  2. NoSQL: mongodb, redis

mongo db is a popular open source Nosql database management system

### what is Nosql?
  Not only sql(nosql) databases is designed to handle structured semi structured and unstructured data.

### difference between rdbms and nosql
rdbms: store data in the form of table 
       it is designed to handle structured data
       note: structured data means predefined and fixed schema
       it use the relational model where data is stored in the tables with rows and columns.



nosql: store data in the form of document
       bunch of documents called collection
       designed to handle structured semi structured and unstructured data.
       it use a variety of flexible data models such as document, columnar and graph.

### when to use rdbms and to use nosql db?
rdbms: critical finance and banking and ecommerce, it is suitable for application that require complex trancasaction and data intigrity.

nosql: social media , gaming, large database, it is designed to handle large volume of data with high speed read and write operations such as social media,IOT and gaming. 

### what are document and collection in nosql?
a document is a semi structured data structure(XML, Json format) that stores information in a nosql database it is similar to a row in a table in rdbms.

a collections is group of documents that are stored together in a Nosql database. it is similar to a table in a rdbms.

### what are crud in mongodb
c: create: inserting new document into the mondodb collection
r: read: retriving data from a mongodb collection
u: update: modifying existing document
D: delete: removing document form the collection

### how to connect to mongodb server from node js app


### what are query operator in mongodb?
query operators are special keywords or symbls to perform operations like comparison, logical operations in queries.

### what is projection in mongodb? How to implement it?
projection is way of specifying which fields should be returned in the query results.
projection can be implemented by using the project method.

### what are indexes in mongodb? How indexing make data retrieval faster?
indexes are data structure that improve the speed of data retrival operations on the coll
ections
By default index is automatically created on _id field.

mongodb automatically updates the index tree as document are inserted, updated or deleted ensuring the index remains accurate.

when querying with indexed fields, mongodb uses the index to efficiently locate matching documents avoiding a full collection scan.

### what is mongoose? what are the advantages of using it?
mongoose is an object data modeling (ODM) library for mongodb and node js
mongoose provides schema-based solution to model application data

### what is the role of schema in Mongoose? how to define it?
A schema in mongoose defines the structure, validation rules, and behaviour of mongodb documents, ensuring data consistancy and intigrity.
it is defined using the mongoose.schema() function.






