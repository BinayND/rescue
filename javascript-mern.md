### Table of Contents


  - [Server setting](#servelevel)
  - [Core features and updates](#CoreAndUpdate)
  - [nodejs](#nodejs)
  - [Express js](#express)
  - [mongodb](#mongodb)



### servelevel

```
   
```

### CoreAndUpdate

```

```

## nodejs

```

```


### express

```
Create multiple schema in single model file MVC pattern style and how to access in controller file

const mongoose = require("mongoose");

const categorySchema = mongoose.Schema({
  category: {
    type: String,
    required: true,
    unique: true,
  },
  createdAt: {
    type: Date,
    default: Date.now,
  },
});

const SubCategorySchema = mongoose.Schema({
  cat: {
    type: String,
    required: true,
  },
  sub_cat: {
    type: String,
    required: true,
    unique: true,
  },
  createdAt: {
    type: Date,
    default: Date.now,
  },
});

// Create models based on the schemas
const Category_coll = mongoose.model("Category", categorySchema);    // Category_coll is identify variable which should be used in controller while access it.

const SubCategory_coll = mongoose.model("SubCategory", SubCategorySchema);

// Export the models
module.exports = {
  Category_coll,
  SubCategory_coll,
};

Below  code for controller file access way
const { Category_coll, SubCategory_coll } = require("../models/categoryModel");

const category = new Category_coll({
      category: req.body.category,
    });
    const cat_data = await category.save();

```

### mongodb

[Mongo db Reference ](https://www.mongodb.com/developer/products/mongodb/cheat-sheet/)
[Refer 1](https://gist.github.com/subfuzion/9236165)

Two package to install and require

- [validators](https://www.npmjs.com/package/validator)
- [types/validators](https://www.npmjs.com/package/@types/validator?activeTab=readme)

```
1 - Defining a schema


const mongoose = require('mongoose');

const ProductSchema = mongoose.Schema({
    sub_cat: {
        type: String,
        required: true,
        unique: true,
      },
      createdAt: {
        type: Date,
        default: Date.now,
      },
role: {
    type: string,
    enum: ["admin", "user", "operator"],
    default: "user",
  },
dob:{
  type:date,
  required:[true,'Enter valid calendar date'],
},
email:{
  type:string,
  unique:[true,'Email Already exists'],
  required:[true,'Enter email ID'],
  validate: validator.isEmail(),
},
{
timestamps:true
}


});

const Products_coll = mongoose.model("Products", ProductSchema);

module.exports = {

}

2 - Custom Error Messages

onst breakfastSchema = new Schema({
  eggs: {
    type: Number,
    min: [6, 'Must be at least 6, got {VALUE}'],
    max: 12
  },
  drink: {
    type: String,
    enum: {
      values: ['Coffee', 'Tea'],
      message: '{VALUE} is not supported'
    }
  }
});
const Breakfast = db.model('Breakfast', breakfastSchema);



```
    
