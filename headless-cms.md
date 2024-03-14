
 ### Strapi Headless CMS
 
 ```
 yarn develop
 yarn build - admin panel

```

- To acess via api first create api token and assign content type rules.

### How to write request

Add header as Authorization
-  http://localhost:8888/api/api-id    //api-id you will get contents data -left side

- Content type - section which can be used to add records
- Component - are small block of code that need to be added in content type 
- Giving name without Space is helpful used lowercase better api fetch meta variables

- Wait after create Component and restart
Spaces not allowed while create Compontent and linking

- Components - are small chunks piece of code elements to be used in places
Creating button component

- Content-type -> dynamic zone -> Add to dynamic zone on main -> collection types

- Content types =>consider it as single landing page and add block components elements to it.

[Query Tool](https://docs.strapi.io/dev-docs/api/rest/interactive-query-builder)

How to export data => yarn strapi help support => yarn strapi export  --no-encrypt -f backup1403 
How to import data => yarn strapi help import =>yarn strapi import -f backup1403.tar.gz // keep the file in same directory.


Reference Video
 

https://www.youtube.com/watch?v=RceLeh9D85o

https://www.youtube.com/watch?v=gS-l96dQAKk  

[Customized Functions](https://github.com/strapi/strapi/blob/main/packages/core/admin/admin/src/translations/en.json)
