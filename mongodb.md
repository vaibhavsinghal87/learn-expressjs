

# Summary of udemy course by [Maximilian Schwarzmüller](https://www.udemy.com/course/mongodb-the-complete-developers-guide/#instructor-2)

## MongoDB Storage Engine - Wired Tiger
![Storage Engine](./mongodb-storage-engine.png)

## MongoDB shell commands - 

- `show dbs`
- `use shop` - creates databse if it doesn't already exists
- `db.products.insertOne({name: "A book", price: 10})` - creates collection if it doesn't already exists
- `db.products.find()` - retrieves first 20 documents inside "products" collection. Doesn't returns all the documents. Instead returns a cursor when documents are more than 20. Cursor - Type "it" for more.
- `db.products.updateOne({price: 10}, {$set: {description: "good read"}})` -  _$set_ is required here. Without _$set_ error will be thrown.
- `db.products.updateMany({}, {$set: {description: "good read"}})` - _$set_ is required here. Without _$set_ error will be thrown.
- `db.products.insertMany([{name: "A shirt", price: 20}, {name: "A bag", price: 30}])` - Array of json documents. Mongodb maintains the _order_ here.
- `db.products.deleteMany({})` - Delete all documents in the collection.
- `db.products.find({price: {$gt: 10}})` - Find documents whose price is greater than 10.
- `db.products.findOne({price: {$gt: 10}})`
- `db.products.find().toArray()` - Mongodb returns first 20 documents when plain find query is executed. _toArray()_ forces find() to fetch all documents and will not stop at first 20 documents. Not optimal if there are a lot of documents.
- `db.products.find().forEach((item) => {printjson(item)})`
- `db.products.find({}, {name: 1, _id: 0})` - returns only name field from the documents. This is called _Projection_. Data transformation happens on the Mongodb server before it is transferred to client.
- `db.products.findOne({price: 20}).size` - Outputs size field of element after fetching document from mongodb.
- `db.products.findOne({size: "M"})` - Querying size Array - Outputs the document which has size equals "M". Mongodb is smart enough to return the document even if an array field is queried, i.e even if size field is an array it returns the document.
- `db.products.find({"status.description": "on-time"})` - Querying nested Documents/Objects - returns the Document that match the nested query. Dot notation allows to look into Embedded Documents.
- `db.dropDatabase` - Deletes the current database.
- `db.collectionName.drop()` - Deletes the collection by name "collectionName".
- `typeof db.products.findOne({price: 30}).name` - returns Data type of the value

Collection is equivalent to tables in structured DB.  
Cursor doesn't exists for insert, update and delete methods.  
Embedded Documents - Document inside Document. Can have upto 100 level of nesting. Arrays can also be present in nested documents.  
Use filters and operators to limit the number of Documents retrieved.  
Filters allow you to restrict the amount of documents and Projection then allows to restrict fields per Document.  

## Schemas and Relations - 



## Refs
- [MongoDB Documentation](https://www.mongodb.com/docs/)
- [MongoDB Drivers](https://www.mongodb.com/docs/drivers/)
- [MongoDB official Nodejs driver](https://www.npmjs.com/package/mongodb)
- [MongoDB Shell](https://www.mongodb.com/docs/mongodb-shell/)
- [MongoDB Shell Methods](https://www.mongodb.com/docs/mongodb-shell/reference/methods/)
- [MongoDB Data Types](https://www.mongodb.com/docs/manual/reference/bson-types/)