# MongoDB
## Features and Intro
- MongoDB is an open-source document database and leading NoSQL database.
- high performance, high availability, and easy scalability. MongoDB works on concept of collection and document.
- Structure:
  - db
    - collection (similar to table)
      - documents (similar to rows - actual data)
        - fields (columns)
    - Embedded Documents (Joins)
    - Primary Key (Default key _id provided by MongoDB itself)

## Advantages of MongoDB over RDBMS
- Schema less − MongoDB is a document database in which one collection holds different documents. Number of fields, content and size of the document can differ from one document to another.
- Structure of a single object is clear.
- No complex joins.
- Deep query-ability. MongoDB supports dynamic queries on documents using a document-based query language that's nearly as powerful as SQL.
- Tuning.
- Ease of scale-out − MongoDB is easy to scale.
- Conversion/mapping of application objects to database objects not needed.
- Uses internal memory for storing the (windowed) working set, enabling faster access of data.
- Why Use MongoDB?
Document Oriented Storage − Data is stored in the form of JSON style documents.
- Index on any attribute
- Replication and high availability
- Auto-Sharding
- Rich queries
- Fast in-place updates
- Professional support by MongoDB

## Where to Use MongoDB?
- Big Data
- Content Management and Delivery
- Mobile and Social Infrastructure
- User Data Management
- Data Hub

## Data Modeling
- Embedded Modeling (kinda nested documents)
  - In this model, you can have (embed) all the related data in a single document, it is also known as de-normalized data model.
- Normalized Data Model (kinda relationships by giving reference)
  - In this model, you can refer the sub documents in the original document, using references.

## Datatype
- String
- Integer
- Boolean
- Double
- Min/ Max keys
- Arrays
- Timestamp
- Object
- Null
- Symbol
- Date
- Object ID
- Binary data
- Code
- Regular expression 

## Projection
- In MongoDB, projection means selecting only the necessary data rather than selecting whole of the data of a document. If a document has 5 fields and you need to show only 3, then select only 3 fields from them.

## Operations ```db.COLLECTION_NAME.*```
- ```find(CONDITION, )```
- ```findOne()```
- ```find({CONDITION_OBJECT}, {KEY: 1})```
- ```find().limit(NUMBER)```
- ```find().skip(NUMBER)```
- ```find().sort({KEY: 1/-1)```
- ```find().pretty()```
- ```update(SELECTION_CRITERIA, { $set: {UPDATED_DATA} }) // default: update single option: { multi: true }```
- ```save({_id:ObjectId(),NEW_DATA}) // Overwrite```
- ```findOneAndUpdate(SELECTION_CRITERIA, { $set: {UPDATED_DATA} })```
- ```updateOne(<filter>, <update>)```
- ```updateMany(<filter>, <update>)```
- ```remove(DELETION_CRITERIA)```
- ```remove(DELETION_CRITERIA, 1) // Delete One```
- ```remove({}) // remove all```

## Operators in conditions
- ```{ KEY: { $eg:   {} } }```
- ```{ KEY: { $lt:   {} } }```
- ```{ KEY: { $lte:  {} } }```
- ```{ KEY: { $gt:   {} } }```
- ```{ KEY: { $gte:  {} } }```
- ```{ KEY: { $ne:   {} } }```
- ```{ KEY: { $in:   [] } }```
- ```{ $and: [ { KEY: VALUE }, ...]] }```
- ```{ $or: [ { KEY: VALUE }, ...]] }```
- ```{ $not: [ { KEY: VALUE }, ...]] } // NOR```
- ```{ $NOT: [ { KEY: VALUE }, ...]] } // NOT```

## Relation
1. Embedded Relation
2. Referenced Relationship


## Indexing
- Indexes are special data structures, that store a small portion of the data set in an easy-to-traverse form. The index stores the value of a specific field or set of fields, ordered by the value of the field as specified in the index.
