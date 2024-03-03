
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
#### Joi Package > YUP > Express validator

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
- Create Mock Dummy Data Latest [Version -8](https://fakerjs.dev/api/faker.html)
- Always convert if mongodb _id field to string value compare

```
// console.log(
    //   `Exce ${typeof existingTrip.driver_accepted_by.toString()} : by ${typeof driver_id}`
    // );

```


```


```

[Code Seperation](https://www.infoq.com/articles/separation-concerns-nodejs/)

if face error node in terminal node- v not showing 'node' is not recognized as an internal or external command,
operable program or batch file.
[How to switch cmd to powershell in vscode ](https://stackoverflow.com/questions/42729130/visual-studio-code-how-to-switch-from-powershell-exe-to-cmd-exe)
 - Kill terminal > Restart vscode

Installing Node Version LTS on machine first time or updating
error 
The term node is not recognized as the name of a cmdlet, function, script file, or operable program. [Refer]( https://www.codewithharry.com/blogpost/solving-node-not-recognized-error-windows/)

  - DateTime Conversion To System Machine
```
    const mongoDate = new Date("2024-02-06T11:10:31.323Z");
    const localDate = mongoDate.toLocaleString();
    console.log(localDate);
    return false;
```


