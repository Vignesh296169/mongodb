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
  
