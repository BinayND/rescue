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

```


```
    
