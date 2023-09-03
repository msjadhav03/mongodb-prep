# MongoDB
<p>  
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/MongoDB_Logo.svg/2560px-MongoDB_Logo.svg.png" alt="Mongodb Logo" height="260">
</p>

# 1.Introduction
Open Source, NoSQL database, designed to store and manage large volumes of data across distributed systems. Data Stored in JSON-like objects. MongoDB is well suited for application with constantly changing requirements.
#### features
 1. ACID Transaction
 2. Community and Enterprise Version
 3. Security Feature
 4. Schema Flexibility
 5. Document Oriented
 6. Dynamic Queries
 7. Replication
 8. Indexing
 9. Aggregation Framework
 10. Full Text Search
 11. Geospatial Queries 

# Structure of MongoDB Document
- Open Source
- NoSQL Database
- Designed to store large Volume of data
- Well suited for application constantly changing requirements

# BSON Data Format
- Binary JSON
- Compact and efficient for storage and transmission
- easy to parse
- elements within the objects are ordered
- Data Type
    1. String - textual data
    2. Interger - whole number
    3. Double - floating point number
    4. Boolean - true or false value
    5. ObjectId - unique identifier, 12-byte value, represented hexadecimal
    6. Date - specific point in time
    7. Array - list if values
    8. Binary Data - binary data such as images, audio files and more
    9. Null - null or empty values
    10. Regular Expression - regular expression for pattern matching
    11. Timestamp - used to store timestamp
    13. Decimal128 - decimal number with high precision
    14. MinKey and MaxKey - special values use to compare against the smallest and largest values of other data types
    15. Symbol - string that's used as unique identifier for a specific value within the database
    
# Indexing in MongoDB
- Improve performance of database queries
- creating datastructure that allow faster fetching of data
- Type 
    1. Single Field Index - index on a single field
    2. Compound Index - index on multiple field
    3. Text Index - indexes for text search
    4. Geospatial Index - indexes for geospatial queries, query based on geographical coordinated
    5. Hashed Index - indexes that hash the indexes value, suitable where distribution of values is important
- creating index
`createIndex()`
```js
db.collection_name.createIndex({field:1, field : -1})
// 1 Ascending order
// -1 Descending order
```
`Note : Too many indexes can slow down performance for insert, update, delete`
- Best Practices for Indexing
    1. Index only frequently used field
    2. priotize queries, with equality, range and sort
    3. avoid too many indexes
    4. monitor performance and adjust the indexes
    5. `explain()` method to analyze query execution
- Indexing strategies
    1. Covering Index - Index all fields needed to fulfil the query
    2. Sparse Index - index that only include documents with specific fields 
    3. WildCard Index - index that match field based on
- Drop Index
`dropIndex()`
```js
db.collection_name.dropIndex({"name":  1})
```
- List Indexes
`getIndexes()`
```js
db.collection_name.getIndexes()
```
# Primary Key in MongoDB
# Replica Set and Shareded Cluster
# Basic CRUD
- Create Database
```js
use database_name
```
- Drop Database
```js
db.dropDatabase()
```
- Drop Collection
```js
db.collection_name.drop()
```
- Insert document
```js
db.collection_name.insertOne({"name":"Manisha"})
```
- Update Document
```js
db.collection_name.updateOne({"name":"Manisha"},{$set: {"age":24}})
```
- Delete Document
`deleteOne()`
```js
db.collection_name.deleteOne({"name":"manisha"})
```
- Delete Many Documents
`delete()`
```js
db.collection_name.delete({})
```
- Find Document
`.find()`
```js
db.collection_name.find({"age":{$gte:23}})
```

# Aggregation
# Schema Migration and Versioning
# ObjectId Data type in MongoDB
# MongoDB high availability and Fault Tolerance
# MongoDB write Concern
# MongoDB read preference
# GridFs in MongoDB
# Concurrency and Locking
# Security in MongoDB and Best Practices
# Optimizing the Performance of Queries
# Tools or Techniques to monitor and diagnose performance issues in MongoDB
# Data Import and Export in MongoDB
# Use cases of MongoDB

# What is MongoDB?
- Open Source
- NoSQL database
- Stores large volume of data
- Stores data in JSON like object format named BSON - binary JSON
- Data Types
    1. Date
    2. TimeStamp
    3. String
    4. Regular Expression
    5. Symbol
    6. Integer
    7. Double
    8. Decimal128
    9. ObjectId
    10. Null
    11. MinKey and MaxKey
    12. Array
    13. Binary Data
    14. Boolean

# Key Features of MongoDB
 1. ACID Transaction
 2. Community and Enterprise Version
 3. Security Feature
 4. Schema Flexibility
 5. Document Oriented
 6. Dynamic Queries
 7. Replication
 8. Indexing
 9. Aggregation Framework
 10. Full Text Search
 11. Geospatial Queries
 12. Change Stream - real time notifications about the changes made to the data in MongoDB collection 
# When to Use MongoDB
1. Document Oriented Data - unstructred data, undefined data model
2. Large Amount of data 
3. Real Time Data Analysis
4. Content Management System
5. Catalogs and E-Commerce
6. Logging and Time Series Data
7. Geospatial Data
8. IoT - data generated by IoT devices
9. Content Delievery Network


# MongoDB vs Traditional SQL Database

# Creating Database and Collection

# Inserting Documents
    - Inserting One Document
`insertOne()`
```js
    db.collection_name.insertOne({"field1": "value","field2":"value2"})
```
    - Inserting Many Documents
`insertMany()`
```js
db.collection_name.insertMany([
    {
    // document 1 
        "field1": "value","field2":"value2"
    },
    {
    // document 2 
        "field1": "value","field2":"value2"
    },
    {
    // document n 
        "field1": "value","field2":"value2"
    }
])
```

# Querying Documents

# Updating Documents
`updateOne()` - Update One Document
`updateMany()` - Update Many Document
```js
// Updating One Document
db.collection_name.updateOne({
    // filterCondtion
    "name":"Manisha"
},{
    // Updation Fields
    $set:{
        "age":25
    }
})

// Upating Many Documents
db.collection_name.updateMany({
    // filterCondtion
    "age":{
        $gte:24
    }
},{
    // Updation Fields
    $set:{
        "profession":"working" 
    })
```
# Deleting Documents
`deleteOne()` - delete Single Document
`deleteMany()` - delete Many Documents
```js
// Single Document Deletion
db.collection_name.deleteMany({ condition})
db.collection_name.deleteOne({_id:ObjectId("...")})
db.collection_name.deleteOne({"name":"manisha"})

// Multiple Document Deletion
db.collection_name.deleteMany({condition})
db.collection_name.deleteMany({"age":{
    $lte : 248055
}})
```
# Document structure and Schema Design


# Embedded vs Referenced Documents

# One-toOne, One-to-Many and Many-to-Many relationships

# Index types and creation
- Improve performance of database queries
- creating datastructure that allow faster fetching of data
- Type 
    1. Single Field Index - index on a single field
    2. Compound Index - index on multiple field
    3. Text Index - indexes for text search
    4. Geospatial Index - indexes for geospatial queries, query based on geographical coordinated
    5. Hashed Index - indexes that hash the indexes value, suitable where distribution of values is important
- creating index
`createIndex()`
```js
db.collection_name.createIndex({field:1, field : -1})
// 1 Ascending order
// -1 Descending order
```
`Note : Too many indexes can slow down performance for insert, update, delete`

# Indexing strategies
`Covering,Sparse,wild card` 

- Indexing strategies
    1. Covering Index - Index all fields needed to fulfil the query
    2. Sparse Index - index that only include documents with specific fields 
    3. WildCard Index - index that match field based on
- Creating index
`createIndex()`
```js
db.collection_name.createIndex({"field1":1})
```
# Query Optimization

# Profiling and Performance Monitoring

# Introduction to aggregation

# Aggregation pipeline Stages

# Grouping, Filtering, Projecting

# Profiling and Performance monitoring

# Introduction to Aggregation

# Aggregation Pipeline Stages

# Grouping, Filtering, Projecting

# Aggregation Operators

# Data import and export

# Backup and Restore Strategies

# Data Migration

# ACID Properties

# Transactions in MongoDB

# Handling Concurrency Issues

# Geospatial Indexes

# Querying Geospatial Data

# Location-Based Applications

# User Authentication and Authorization

# Role based Access Control

# Security Best Practices

# Replica Set: Concepts and Configurations

# Failover and Automatic Recovery

# Read Preference Modes

# Sharding Concepts

# Sharding setup and Configurations

# Balancing Data and Ranges

# Text Indexes

# Text Search Operators

# Building a full-Text Search Engine

# Using Indexes with Aggregation

# Aggregation Pipeline Optimization

# Aggregation Pipeline Operators for performance

# Montioring Tools

# MongoDB Atlas and Cloud Soultions

# Maintenance and Upgrades

# Schema Design Patterns

# Error Handling and Exception Management

# Writing Efficient Queries

# Aggregation Stages

1. **$addFields**
2. **$bucket**
3. **$bucketAuto**
4. **$collStats**
5. **$count**
6. **$facet**
7. **$geoNear**
8. **$graphLookup**
9. **$group**
10. **$indexStats**
11. **$limit**
12. **$listLocalSessions**
13. **$listSessions**
14. **$lookup**
15. **$match**
16. **$merge**
17. **$out**
18. **$planCacheStats**
19. **$project**
20. **$redact**
21. **$replaceRoot**
22. **$replaceWith**
23. **$sample**
24. **$set**
25. **$skip**
26. **$sort**
27. **$sortByCount**
28. **$unionWith**
29. **$unset**
30. **$unwind**


# Aggregation Operators

**Accumulators:**
- `$addToSet`
- `$avg`
- `$first`
- `$last`
- `$max`
- `$min`
- `$push`
- `$stdDevPop`
- `$stdDevSamp`
- `$sum`

**Array Operators:**
- `$arrayElemAt`
- `$arrayToObject`
- `$concatArrays`
- `$filter`
- `$in`
- `$indexOfArray`
- `$isArray`
- `$map`
- `$objectToArray`
- `$range`
- `$reduce`
- `$reverseArray`
- `$size`
- `$slice`
- `$zip`

**Boolean Operators:**
- `$and`
- `$not`
- `$or`

**Comparison Operators:**
- `$cmp`
- `$eq`
- `$gt`
- `$gte`
- `$lt`
- `$lte`
- `$ne`

**Conditional Operators:**
- `$cond`
- `$ifNull`
- `$switch`

**Date Operators:**
- `$dateFromParts`
- `$dateFromString`
- `$dateToParts`
- `$dateToString`
- `$dayOfMonth`
- `$dayOfWeek`
- `$dayOfYear`
- `$hour`
- `$isoDayOfWeek`
- `$isoWeek`
- `$isoWeekYear`
- `$millisecond`
- `$minute`
- `$month`
- `$second`
- `$toDate`
- `$week`
- `$year`

**Literal Operators:**
- `$literal`

**Math Operators:**
- `$abs`
- `$add`
- `$ceil`
- `$divide`
- `$exp`
- `$floor`
- `$ln`
- `$log`
- `$log10`
- `$mod`
- `$multiply`
- `$pow`
- `$sqrt`
- `$subtract`
- `$trunc`

**Object Operators:**
- `$mergeObjects`
- `$objectToArray`

**Set Operators:**
- `$allElementsTrue`
- `$anyElementTrue`
- `$setDifference`
- `$setEquals`
- `$setIntersection`
- `$setIsSubset`
- `$setUnion`

**String Operators:**
- `$concat`
- `$indexOfBytes`
- `$indexOfCP`
- `$ltrim`
- `$regexFind`
- `$regexFindAll`
- `$regexMatch`
- `$rtrim`
- `$split`
- `$strLenBytes`
- `$strLenCP`
- `$strcasecmp`
- `$substr`
- `$substrBytes`
- `$substrCP`
- `$toLower`
- `$toUpper`
- `$trim`

**Text Search Operators:**
- `$meta`
- `$search`
- `$text`

**Trigonometry Operators:**
- `$sin`
- `$cos`
- `$tan`
- `$asin`
- `$acos`
- `$atan`
- `$atan2`


# Practice Queries
- Show Database
```js
show dbs
```
- Switch Database
```js
use database_name
```
- Create Database
```js
use database_name
```
- Drop Database
```js
db.dropDatabase()
```
- Drop Collection
```js
db.collection_name.drop()
```
- Insert document
```js
db.collection_name.insertOne({"name":"Manisha"})
```
- Update Document
```js
db.collection_name.updateOne({"name":"Manisha"},{$set: {"age":24}})
```
- Delete Document
`deleteOne()`
```js
db.collection_name.deleteOne({"name":"manisha"})
```
- Delete Many Documents
`delete()`
```js
db.collection_name.delete({})
```
- Find Document
`.find()`
```js
db.collection_name.find({"age":{$gte:23}})
```
- Check Server Status
`.serverStatus()`
```js
show serverStatus()
```
- Count documents
`countDocuments()`
```js
db.collection_name.countDocuments({"age":{$gte : 14}})
```
- Explain Query Plan
`.explain("executionStats")`
```js
db.collection_name.find({"age":{$gte : 24}}).explain("executionStats")
```