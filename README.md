# mongodb
* insert
db.<collectionName>.insertOne()
db.<collectionName>.insertMnay([
<document1>,
<document2>,
<document3>
])
* find ($eq,$in)
use $in method  within find () method find ({name:"vicky"}) or find({name:{$eq:"vicky"}}) , find({name:{$in:["vicky","arun"]}}) $in array of possibilites will return documents where the name is either "vicky" or "arun".
* comparison operator
  - $gt
  - $gte
  - &lt
  - &lte
  - $nin: Not in a specified array.
* sub documents means {ites:[{}]) nested property or field is call sub document
* logic operator
  - $and: Performs a logical AND operation on an array of two or more expressions and selects the documents that satisfy all the expressions in the array.
  - $or: Performs a logical OR operation on an array of two or more expressions and selects the documents that satisfy at least one of the expressions.
  - $not: Performs a logical NOT operation on the specified expression and selects the documents that do not match the expression.db.collection.find({
  field: { $not: { $eq: value } }
})
- the $elemMatch operator is used to query array elements within documents
- { field: { $elemMatch: { <query1>, <query2>, ... } } }
- db.collection.find({
    $and: [
        { age: { $gt: 25 } },
        { score: { $gt: 80 } }
    ]
});

- db.collection.find({
    $or: [
        { age: { $lt: 20 } },
        { score: { $gt: 90 } }
    ]
});
  
- when include same operator more than once you need use explicity $and db.collection.find({
    $and: [
        {
            $or: [
                { age: { $lt: 20 } },
                { score: { $gt: 90 } }
            ]
        },
        {
            $or: [
                { status: "active" },
                { role: "admin" }
            ]
        }
    ]
});
-   $and: [
        {
            $and: [
                { age: { $gt: 25 } },
                { score: { $gt: 80 } }
            ]
        },
        {
            $and: [
                { status: "active" },
                { role: "admin" }
            ]
        }
    ]
* update and deletion procress
  - replace a document in mongo db ->to replace single document method called replaceOne() this will accept three argument(filter,replacement,option),
  - update operation  updateOne() with two update operators $set , $ push and upsert three argument(filter,replacement,option)
  - $set operator  new filed and add value or update feild and value in existing one
  - $push push the value into an array
  - no need to give whole values only need to give certain value and field that need to upadate and replaceOne() is opposite you have to give the whole update docs,
  - here important one filter option does not ans conditions so we can use the upsert method that put that doc in collection
  - findAndModify() this will update and return the doc just has been updated
  - update many() syntx=>(filter document,update document,option)
  - db.collection.updateMany(
  <filter>,
  <update>,
  <options>)
  - $set: Sets the value of a field in a document.
    $unset: Removes the specified field from a document.
    $inc: Increments the value of a field by a specified amount.This operator is particularly useful in scenarios where you need to adjust numeric values without overwriting them
    Likes or Votes: Adjust the number of likes or votes for a post, comment, or product.
    $currentDate: Sets the value of a field to the current date.
* delete one and delete many  deleteOne({}) and deleteMany()
* sorting is pending
