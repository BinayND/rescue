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

** DateTime Conversion To System Machine
    const mongoDate = new Date("2024-02-06T11:10:31.323Z");
    const localDate = mongoDate.toLocaleString();

    console.log(localDate);
    return false;


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



## Check if route is working or not

```
check in index.js or server.js entry file have you include the route file or not app use code eg
const prd_routes = require("./routes/productRoute");
app.use("/api/", prd_routes);


Check debug the route
prd_route.post("/product/add-product", (req, res) => {
  console.log(req);
});

```

[Multiple Image Uplaod Code](https://github.com/Sameera-Perera/Express-Js-REST-API-Image-Uploade-Complete-Example)

## Npm Package Body parser is useful to get browser body data

const bodyParser = require("body-parser");
router.use(express.json());
router.use(bodyParser.json());
router.use(bodyParser.urlencoded({ extended: true }));


### mongodb

[Mongo db Reference ](https://www.mongodb.com/developer/products/mongodb/cheat-sheet/)
[Refer 1](https://gist.github.com/subfuzion/9236165)

[Comman Method ](https://www.mongodb.com/docs/v5.2/reference/method/)

Two package to install and require

- [validators](https://www.npmjs.com/package/validator)
- [types/validators](https://www.npmjs.com/package/@types/validator?activeTab=readme)

```
1 - Defining a schema


const mongoose = require('mongoose');

const ProductSchema = mongoose.Schema({

store_id: { type: mongoose.Types.ObjectId, ref: "stores" }, // stores is collection name
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

Search Query
db.products.find({ name: { $regex: "", $options: "i" } })

```

## pagination example     

```

const paginate = async (req, res) => {
  try {
    var page = req.body.page;
    var sort = req.body.sort;
    var pageLimit = 2;

    if (page <= 1) {
      skip = 0;
    } else {
      skip = (page - 1) * pageLimit;
    }

    if (sort) {
      var customersort;
      if (sort == "name") {
        customersort = {
          name: 1,
        };
      } else if (sort == "id") {
        customersort = {
          _id: 1,
        };
      }

      product_data = await Products_coll.find()
        .sort(customersort)
        .sort({ createdAt: -1 })
        .skip(skip)
        .limit(pageLimit);
    } else {
      product_data = await Products_coll.find()
        .sort({ createdAt: -1 })
        .skip(skip)
        .limit(pageLimit);
    }

    res.status(200).send({ success: true, msg: product_data });
  } catch (error) {
    res.status(400).send({ success: false, msg: error.message });
  }
};


```
