
### Table of Contents

  - [Validation](#validation)
  - [Error Handling](#Errorhandling)
  - [Updates](#Updates)
  - [Query Way](#Querying)
  - [Short Cut](#ShortCut)  


### Validation
  
-While using express validator package If you'd like to skip validations when the value is null, undefined, false, zero or an empty string, you can do this:
```
check('name').optional({ checkFalsy: true }).trim().isLength({ min: 3, max: 30 }),

```

### Errorhandling

- File Upload using postman error multer solution handle in diskstorge function [Refer](https://stackoverflow.com/questions/48726473/postman-raw-data-works-but-form-data-not-works-on-post-request-in-node)

- Mongodb Playground[Refer](https://mongoplayground.net/)


  
```


```


### Updates

  -  while upgrading aws s3 from v2 to version 3 error of location path how is solved using change function[Refer](https://stackoverflow.com/questions/77184519/unable-to-get-the-public-link-to-s3-bucket-object-after-uploading-from-node-js)
```
const baseurl =  ${req.protocol}://${req.get('host)}/public/uploads


```

### ShortCut

- Node Code Style [Refer](https://github.com/felixge/node-style-guide?tab=readme-ov-file#2-spaces-for-indentation) 

```


```
