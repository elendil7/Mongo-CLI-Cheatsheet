<div align=center>
  <h1>Mongo-CLI-Cheatsheet</h1>
</div>

## 🔍 Table of Contents
- [💼 Introduction](#-introduction)
- [⚡ Quick Access Power User Commands](#-quick-access-power-user-commands)
- [🚀 Commands](#-commands)
  - [🐳 Docker](#-docker)
  - [📦 Database](#-database)
  - [📁 Collection](#-collection)
  - [📄 Document](#-document)
  - [📄 Document Query](#-document-query)
  - [📄 Document Query Operators](#-document-query-operators)
  - [📄 Document Query Logical Operators](#-document-query-logical-operators)
  - [🔄 Misc Query Chaining Functions](#-misc-query-chaining-functions)
- [📚 Resources](#-resources)

# 💼 Introduction
This repo was designed to be a quick reference for the most common MongoDB CLI commands. It is not meant to be a comprehensive guide, but rather a quick reference for the most common commands.

# ⚡ Quick Access Power User Commands
```bash
show dbs # Show all databases
use <database> # Switch to a database
db # Show current database
show collections # Show all collections in the database you're in
db.<collection>.find() # Show all documents in a collection
db.<collection>.find().sort().pretty() # Show all documents in a collection, sorted, and pretty printed
```

# 🚀 Commands
## 🐳 Docker
```bash
docker exec -it <container> mongo --port 27017 # Enter a docker container, then enter the mongo shell at port 27017

# Example:
docker exec -it mongodbcontainer mongo --port 27017
```

## 📦 Database
```bash
show dbs # Show all databases
use <database> # Switch to a database
db # Show current database
show collections # Show all collections in the database you're in
db.dropDatabase() # Delete current database
```

## 📁 Collection
```bash
show collections # Show all collections
db.createCollection("<collection>") # Create a collection
db.<collection>.drop() # Delete a collection
```

## 📄 Document
```bash
db.<collection>.find() # Show all documents in a collection
db.<collection>.insertOne({<document>}) # Insert a document
db.<collection>.insertMany([{<document>}, {<document>}]) # Insert multiple documents
db.<collection>.deleteOne({<document>}) # Delete a document
db.<collection>.deleteMany({<document>}) # Delete multiple documents
db.<collection>.updateOne({<document>}, {$set: {<document>}}) # Update a document
db.<collection>.updateMany({<document>}, {$set: {<document>}}) # Update multiple documents
```

## 📄 Document Query
```bash
db.<collection>.find({<document>}) # Find a document
db.<collection>.find({<document>}).sort({<document>}) # Find a document and sort
db.<collection>.find({<document>}).limit(<number>) # Find a document and limit
db.<collection>.find({<document>}).skip(<number>) # Find a document and skip
db.<collection>.find({<document>}).count() # Find a document and count
```

## 📄 Document Query Operators
```bash
db.<collection>.find({<document>: {$eq: <value>}}) # Equal
db.<collection>.find({<document>: {$gt: <value>}}) # Greater than
db.<collection>.find({<document>: {$gte: <value>}}) # Greater than or equal
db.<collection>.find({<document>: {$in: [<value>, <value>]}}) # In
db.<collection>.find({<document>: {$lt: <value>}}) # Less than
db.<collection>.find({<document>: {$lte: <value>}}) # Less than or equal
db.<collection>.find({<document>: {$ne: <value>}}) # Not equal
db.<collection>.find({<document>: {$nin: [<value>, <value>]}}) # Not in
db.<collection>.find({<document>: {$exists: <boolean>}}) # Exists
db.<collection>.find({<document>: {$type: <type>}}) # Type
```

## 📄 Document Query Logical Operators
```bash
db.<collection>.find({$and: [{<document>: <value>}, {<document>: <value>}]}) # And
db.<collection>.find({$or: [{<document>: <value>}, {<document>: <value>}]}) # Or
```

## 🔄 Misc Query Chaining Functions
```bash
db.collection.find().sort().limit().skip().count().pretty() # Chaining functions

# Each chained method explained:
db.collection.find() # Find a document (base query)
db.collection.find().sort(1) # Sort the documents in ascending order
db.collection.find().sort(-1) # Sort the documents in descending order
db.collection.find().sort({ title: 1 }) # Sort the documents by title in ascending order
db.collection.find().limit(5) # Limit the documents to 5 (max)
db.collection.find().skip(5) # Skip the first 5 documents
db.collection.find().count() # Count the number of documents
db.collection.find().pretty() # Pretty print the documents
```

# 📚 Resources
- [MongoDB Docs](https://docs.mongodb.com/manual/reference/mongo-shell/)
- [MongoDB Cheatsheet](https://gist.github.com/bradtraversy/f407d642bdc3b31681bc7e56d95485b6)