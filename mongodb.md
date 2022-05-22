
> Written with [StackEdit](https://stackedit.io/).
# Mongo DB Guide

cred
$=>reserved keyworld, used for any operations.
## Usage/Examples

### CREATE
insertOne(data, options)
  data is json object {}
insertMany(data, options)
  here data is array of json objects [{},{},{},{}]
### FIND
find(filter, options)
  In general find() method will will not give all array of objects if data is too big (>20), instead it will give a curser object. We need to iterate that object and get data. When are looping the iterator, it will re-fetch data and send to us. This will reduce data load on connection.
findOne(filter, options)
  Ex db.students.findOne({age:20}) / same for find
  Ex db.students.findOne({age:{$gt:25}}) /same for find


### UPDATE
updateOne(filter, newData, options)
  Ex updateOne({name:'ram}, {$set:{place:'Delhi'}})
  while updating allways pass second argument as obj with $set,
  if it already exist then it will update, else it add that key-value pair
updateMany(filter, newData, options)
replaceOne(filter, newData, options)
Never use update({},{}) //it will directly replace entire object, instead of updating some key-value. Instead use above 4 methods to update.


### DELETE
deleteOne(filter, options)
deleteMany(filter, options)

### PROJECTION
  While finding multiple objects, we can get only required field from each object 
  Ex db.students.find({},{name:1, address:0}) // 1=>give //0=>dont give
  This means from each collection take/projection only required key-value pairs. So that unnecessary key-value pairs of data from each object is reduced,    before sending it back.
  

> using $gt will limit the number of documents. 
>   using projection will limit the number of fields inside document.


###   finding nested objects
db.students.find({" class.physics":"pass"})
while finding for nested objects, must use double cotes .

    enter code here
    {
    name:"akhil",
    visited:[
		    {place:"hyd", times:1},
		    {place:"delhi", times:9},
		    {place:"pak",times:2}
		    ]
    }

  db.collectionName.deleteMany({"visited.place":"pak"})
  it will delete collection object who visited pak.
  Even though it is array of objects, it will still search inside each array of each object.
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
