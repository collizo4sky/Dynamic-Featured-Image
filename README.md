Dynamic Featured Image
======================

Dynamically adds multiple featured image (post thumbnail) functionality to posts, pages and custom post types.


### Installation

  1. Unzip and upload the `dynamic-featured-images` directory to the plugin directory (`/wp-content/plugins/`) or install it from `Plugins->Add New->Upload`
  2. Activate the plugin through the `Plugins` menu in WordPress.



### How it works?

1. After successfull plugin activation go to `add` or `edit` page of posts or pages and you will notice a box for second featured image.

   ![Snapshot 1](http://ankitpokhrel.com.np/dfi/1.jpg)

2. Click `Set featured image`, select required image from media popup and click `Insert to post`.
   ![Snapshot 2](http://ankitpokhrel.com.np/dfi/2.jpg)

3. Click on `Add New` to add new featured image or use `Remove` link to remove the featured image box.
   ![Snapshot 3](http://ankitpokhrel.com.np/dfi/3.jpg)

4. After adding featured images click `publish` or `update` to save featured images.

###### _Note: The featured images are only saved when you publish or update the post._


### Retrieving Images in a Theme

* To get featured images of specific post

```
if( function_exists('dfiGetFeaturedImages') )
   $featuredImages = dfiGetFeaturedImages($postId);
```

* To get featured images in a post loop.

```
<?php 
   while ( have_posts() ) : the_post();

   if( function_exists('dfiGetFeaturedImages') ) {
       $featuredImages = dfiGetFeaturedImages();
   }
   
   endwhile;
?>
```

* The data is returned as an array that contain selected image and full size path to the selected image.

```
array
  0 => 
    array
      'thumb' => string 'http://your_site/upload_path/yourSelectedImage.jpg' (length=50)
      'full' => string 'http://your_site/upload_path/yourSelectedImage_fullSize.jpg' (length=69)
  1 => 
    array
      'thumb' => string 'http://your_site/upload_path/yourSelectedImage.jpg' (length=50)
      'full' => string 'http://your_site/upload_path/yourSelectedImage_fullSize.jpg' (length=69)
  2 => ...
```
