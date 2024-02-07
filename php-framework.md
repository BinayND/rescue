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

```
<?= date('Y-m-d h:m:s A', strtotime($val['inserted_date'])) ?>

```

### Larvel

```


```
    
