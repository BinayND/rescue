


-  Select specific field => db.trips.findOne({tripNo:2},{tripNo: 1, _id: 0 }) // skip _id field
- Logical And = >db.coll.find({
  $and: [
    {$or: [{qty: {$lt :10}}, {qty :{$gt: 50}}]},
    {$or: [{sale: true}, {price: {$lt: 5 }}]}
  ]
})

- for single document only => db.coll.findOne() // returns a single document
- db.coll.find()    // returns a cursor - show 20 results - "it" to display more
- db.coll.find().pretty()
- Delete one records db.coll.deleteMany({ id: 7 })


## Reference 

[Complex Function such as aggregation] (https://www.youtube.com/watch?v=4EjKroJCpFA&list=PLA3GkZPtsafZydhN4nP0h7hw7PQuLsBv1)  
