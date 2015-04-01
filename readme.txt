=== genius 404 ===

Donate link: http://atastypixel.com/blog/wordpress/plugins/genius-404/
Tags: 404, search, redirection,genius 404 
Requires at least: 2.6
Tested up to: 4.1.1
Stable tag: 1.0

Automatically redirect to the content the user was most likely after, or show suggestions, instead of showing an unhelpful 404 error.

== Description ==

Save your visitors from unhelpful 404 errors!

Instead of quickly giving up when a visitor reaches content that doesn't exist, make an effort to guess what they were
after in the first place.  This plugin will perform a search of your posts, pages, tags and categories, using keywords from the requested
URL.  If there's a match, redirect to that content instead of showing the error.  If there's more than one match, the
404 template can use some template tags to provide a list of suggestions to the visitor.



== Installation ==

1. Unzip the package, and upload `genius404` to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Place `<?php genius404_suggestions() ?>` in your 404 template to list suggested posts, or see 'Template tags' for more information.

== Template tags ==

*`genius404_has_suggestions`*

Returns true if there are some suggestions, false otherwise

*`genius404_get_suggestions`*

Retrieve an array of post objects for rendering manually.

*`genius404_suggestions`*

Draw a list of suggested posts.

Pass the parameter "list" to render suggestions as a list.

*`genius404_loop`*

Query posts for use in a Loop. Eg:

`<?php genius404_loop(); ?>
<?php while (have_posts()) : the_post(); ?>
 	<h2><a href="<?php the_permalink() ?>"><?php the_title(); ?></a></h2>
 	<?php the_excerpt(); ?>
<?php endwhile; ?>`

Note that the loop will not display pages correctly, as it is not built to support them. It is recommended that if you use
a loop like that above, do not enable searching of pages.

*`genius404_get_search_terms`*

Retrieve an array of search terms used to populate the suggestions list, for use with contextual highlighting, etc.

