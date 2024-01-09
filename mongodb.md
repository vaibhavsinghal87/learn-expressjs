

# Summary of udemy course by [Maximilian Schwarzmüller](https://www.udemy.com/course/mongodb-the-complete-developers-guide/#instructor-2)

## Mongodb Storage Engine - Wired Tiger
![Storage Engine](./mongodb-storage-engine.png)

## Mongodb shell commands - 

- show dbs
- use shop - creates databse if it doesn't already exists
- db.products.insertOne({name: "A book", price: 10}) - creates collection if it doesn't already exists
- db.products.find() - retrieves first 20 documents inside collection products. Doesn't returns all the documents. Instead returns a cursor when documents are more than 20. Cursor - Type "it" for more.
- db.products.updateOne({price: 10}, {$set: {description: "good read"}}) -  $set is required here. Without $set error will be thrown.
- db.products.updateMany({}, {$set: {description: "good read"}}) - $set is required here. Without $set error will be thrown.
- db.products.insertMany([{name: "A shirt", price: 20}, {name: "A bag", price: 30}]) - Array of json documents. Mongodb maintains the order here.
- db.products.find({price: {$gt: 10}}) - Find documents whose price is greater than 10.
- db.products.findOne({price: {$gt: 10}})
- db.products.find().toArray() - Mongodb returns first 20 documents when plain find query is executed. toArray() forces find() to fetch all documents and will not stop at first 20 documents. Not optimal if there are a lot of documents.
- db.products.find().forEach((item) => {printjson(item)})

Collection is equivalent to tables in structured DB.

## Refs
- [Mongodb Cursor methods](https://www.mongodb.com/docs/v4.2/reference/method/db.collection.find/#available-mongo-shell-cursor-methods)
- [Mongodb Collection methods](https://www.mongodb.com/docs/v4.2/reference/method/js-collection/#collection-methods)