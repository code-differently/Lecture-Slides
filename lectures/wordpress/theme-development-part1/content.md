# Intro to Wordpress Theme Development








-
-
## Lecture Overview
* Creating an empty theme
* Creating base theme assets







-
-
### Creating an empty theme
1. Navigate to the `wp-content` directory from the `wordpress` root.
* Create a new folder whose name is the new theme name (i.e. `My Theme`)
* Create an `index.php` f ile in the `My Theme` root.
* Create `style.css` file in the `My Theme` root
* Navigate to `http://localhost:8888/wordpress/wp-admin/themes.php`
	* `My Theme` becomes an available theme






-
-
### Creating base theme assets
* The following files should be created in the `My Theme` root directory.
  * `archive.php`
  * `footer.php`
  * `front-page.php`
  * `header.php`
  * `index.php`
  * `page.php`
  * `single.php`
  * `style.css`




-
-
### `header.php`
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
* Add a call to `body_class()` to call to allow Wordpress to add its own classes to the body.
* Add a call to `wp_head()` before the closing `</head>` tag.
  * Plugins use this _action hook_ to add their own scripts, stylesheets, and other functionality.
* Do not link the theme stylesheets in the Header template.
  * Use the `wp_enqueue_scripts` action hook in a theme function insGinger Aled.


-
### Example

```html
<!DOCTYPE html>
<html <?php language_attributes(); ?>>
    <head>
        <meta charset="<?php bloginfo( 'charset' ); ?>" />
        <title><?php wp_title(); ?></title>
        <link rel="profile" href="http://gmpg.org/xfn/11" />
        <link rel="pingback" href="<?php bloginfo( 'pingback_url' ); ?>" />
        <?php if ( is_singular() && get_option('thread_comments'))
                  wp_enqueue_script('comment-reply'); ?>
        <?php wp_head(); ?>
    </head>
```















-
-
### `footer.php`
* file executed by Wordpress to generate _footer_ of theme


-
### What is a _footer_?
* The `<footer>` element represents a container for content at the _foot_ of the page.
* A `<footer>` element typically contains:
    * authorship information
    * copyright information
    * contact information
    * sitemap
    * _back to top_ links
    * related documents

-
### quick tips
* Use the `wp_footer()` call, to appear just before closing body tag.
  * Plugins use this _action hook_ to add their own scripts, stylesheets, and other functionality.

-
### Example

```html
<?php wp_footer(); ?>
</body>
</html>
```














-
-
### `front-page.php`
* file executed by Wordpress to generate _front page_ of theme


-
### What is a _front page_?
* The front page should be the first page that is exposed to a client upon visiting a website
* The front page should allow a client to navigate to any other part of the webservice.


-
### quick tips
* blah



-
### Example Code
```html
<?php get_header();?>
	<div class="container">
		<div class="row">
			<div class="col">
				Left Side
			</div>

			<div class="col">
				Right Side
			</div>
		</div>
	</div>
<?php get_footer();?>
```

















-
-
### `index.php`
* The main template. If your Theme provides its own templates, `index.php` must be present.
* Displays a list of posts in excerpt or full-length form.


-
### What is an _index_ page?
* Displays a list of navigational options to the client


-
### quick tips
* Include `wp_link_pages()` to support navigation links within posts.


-
### Example
```html
```




















-
-
### `archive.php`
* Display archive title (tag, category, date-based, or author archives).
* Display a list of posts in excerpt or full-length form. Choose one or the other as appropriate.
* Include `wp_link_pages()` to support navigation links within posts.


-
### What is an _archive_ page?
* blah


-
### quick tips
* blah

-
### Example
* blah



















-
-
### `page.php`
* The page template.
* Used when an individual Page is queried.


-
### What is a _page_?
* Displays title and content.


-
### quick tips
* Include `wp_link_pages()` to support navigation links within a page.
* Metadata such as tags, categories, date and author should not be displayed.
* Display an "Edit" link for logged-in users with edit permissions.

-
### Example
* blah




























-
-
### `single.php`
* The single post template.
* Used when a single post is queried.
* For this and all other query templates, `index.php` is used if the query template is not present.

-
### quick tips
* Include `wp_link_pages()` to support navigation links within a post.


-
### Example
* blah






















-
-
### `style.css`
* The main stylesheet.
* This must be included with your Theme, and it must contain the information header for your Theme.


-
### quick tips
* blah

-
### Example
* blah






-
-
### Viewing changes
* add content to `front-page.php`
* navigate to `http://localhost:8888/wordpress/` to view changes.
