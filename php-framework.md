### Table of Contents


  - [Server setting](#servelevel)
  - [Core features and updates](#CoreAndUpdate)
  - [Wordpress](#wordpress)
  - [CodeIgniter](#codeIgniter)
  - [Laravel](#Larvel)



### servelevel

```
php ini setting
memory_limit = 256M
max_execution_time = 300
post_max_size = 20M
upload_max_filesize = 20M

```

### Enable Cpanel Cache Module

```
Optimize Website
text/html text/plain text/xml text/css application/javascript image/png image/jpeg font/woff2


```

### wordpress

```
 post Content issue - increase the post max size
 * Disable if you want to use external SEO plugin like YOAST - In betheme while setup only else it will rework
 - https://developers.google.com/search/docs/crawling-indexing/url-structure  -  SEO Related Google Document
 - [Create Wordpress Customo content types and admin panel MU Plugin ](https://wordpress.org/documentation/article/must-use-plugins/) 
 -  Fetch Page Details Wp query

  global $post;
    $post_id = $post->ID;
    $fetch_info = get_post_field('post_name', $post_id);


```

### CoreAndUpdate

```

```

### codeIgniter

- htaccess file for local setup of live project keep in root project folder outside
```
RewriteEngine on

#RewriteCond $1 !^(index\.php|resources|robots\.txt)
RewriteCond $1 !^(index\.php|images|Downloads|css|js|asset|fonts|robots\.txt)

#RewriteCond %{REQUEST_FILENAME} !-f
#RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ /projectname/index.php/$1 [L,QSA] 


```

```
<?= date('Y-m-d h:m:s A', strtotime($val['inserted_date'])) ?>

```

### Larvel

```


```
    
#### Cpanel New Version 10 onwards php mailer issue of port solved ? Steps at cpanel level
http://150.242.12.174/


1. in WHM search TweakSetting in Server Configuration
2. In Tweak Setting Page click on the Mail tab
3. Search smtp in Mail tab
4. search for Restrict outgoing SMTP to root, exim, and mailman (FKA SMTP Tweak)
5. change the default on to off
6. Save the new setting
