# Intro to Wordpress Theme Development








-
-
## Lecture Overview
* How to create an empty theme
* What are the minimum assets?
* Topic 3







-
-
### How to create wordpress themes
1. Navigate to the `wp-content` directory from the `wordpress` root.
* Create a new folder whose name is the new theme name (i.e. `My Theme`)
* Create an `index.php` file in the `My Theme` root.
* Create `style.css` file in the `My Theme` root
* Navigate to `http://localhost:8888/wordpress/wp-admin/themes.php`
	* `My Theme` becomes an available theme















-
-
### Creating base theme assets
* The following files should be created in the `My Theme` root directory.
  * `archive.php`
  * `footer.php`
  * `header.php`
  * `index.php`
  * `page.php`
  * `single.php`
  * `style.css`




-
-
#### `header.php`
* file executed by Wordpress to generate _header_ of theme


-
### What is a _header_?
* The `<header>` element represents a container for introductory content or a set of navigational links.
* A `<header>` element typically contains:
    * one or more heading elements (`<h1>` - `<h6>`)
    * logo or icon
    * authorship information
* You can have several `<header>` elements in one document.

-
### quick tips
* Use proper `DOCTYPE`
* Add a call to `wp_head()` before the closing `</head>` tag.
  * Plugins use this _action hook_ to add their own scripts, stylesheets, and other functionality.
* Do not link the theme stylesheets in the Header template.
  * Use the `wp_enqueue_scripts` action hook in a theme function instead.


-
#### Example

```html
<!DOCTYPE html>
<html <?php language_attributes(); ?>>
    <head>
        <meta charset="<?php bloginfo( 'charset' ); ?>" />
        <title><?php wp_title(); ?></title>
        <link rel="profile" href="http://gmpg.org/xfn/11" />
        <link rel="pingback" href="<?php bloginfo( 'pingback_url' ); ?>" />
        <?php if ( is_singular() && get_option( 'thread_comments' ) ) wp_enqueue_script( 'comment-reply' ); ?>
        <?php wp_head(); ?>
    </head>
```





-
-
#### `footer.php`
* Discussion point 2B.1
* Discussion point 2B.2
* Discussion point 2B.3


-
#### Sub-topic 2C
* Discussion point 2C.1
* Discussion point 2C.2
* Discussion point 2C.3













-
-
### Topic 3
* Sub-topic 3A
* Sub-topic 3B
* Sub-topic 3C



-
#### Sub-topic 3A
* Discussion point 3A.1
* Discussion point 3A.2
* Discussion point 3A.3


-
#### Sub-topic 3B
* Discussion point 3B.1
* Discussion point 3B.2
* Discussion point 3B.3


-
#### Sub-topic 3C
* Discussion point 3C.1
* Discussion point 3C.2
* Discussion point 3C.3













-
-
## Lecture Summary
* Topic 1 Summary
* Topic 2 Summary
* Topic 3 Summary
