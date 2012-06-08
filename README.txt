=== Qtranslate Slug ===
Contributors: Carlos Sanz García
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=SYC46KSLRC4Q8
Tags: qtranslate, slug, multilanguage
Requires at least: 3.2
Tested up to: 3.3.2
Version: 1.0
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Allows to define a slug for each language and some qTranslate bug fixes

== Description ==

[Qtranslate](http://wordpress.org/extend/plugins/qtranslate/) is a nice plugin but unfortunately today is **outdated**. **Qtranslate Slug** is an addon to qTranslate, which adds support for permalinks translations and fix some qTranslate deficiencies.

**Version 1.0** has been written from scratch using OOP. The code has been structured better, the functions have been marked and commented and everything is better integrated with Wordpress API.

This plugin works with **Qtranslate** versions **2.5.8** and **2.5.9**.

= What is new? =

* new branch, the plugin has been rewritten: now the code is commented and wrapped inside a class, much code has change and the performance has been increased.
* no ID for slug type, then don't install `qtrasnlate_slug` table.
* slugs now are stored on meta tables, installation creates a termmeta table with some new *core functions* to access/save data, based on [simple term meta](http://wordpress.org/extend/plugins/simple-term-meta/).
* the plugin generates translated slug automatically from title in empty cases.
* the plugin checks if the slug already exists (per each language and `post_type`/`taxonomy`), and adds a progressive number in this case
* works on ajax requests for example when new taxonomies are created in edit post page.
* possibility to translate the base of permastructs for `post_types` and *taxonomies*, uses [$wp_rewrite](http://codex.wordpress.org/Class_Reference/WP_Rewrite).
* added some filters (see below).
* added plugin language textdomain (.pot file).
* new admin options page for save the base permastructs.
* import process when the plugin updates older versions.
* updated **Language selector Widget**.
* some bug fixes.
* some Qtranslate patches.

= Plugin filters = 

* `qts_validate_post_slug` : args( $post (object), $slug (string), $lang (string) ) / filter to process the post slug before is saved on the database.
* `qts_validate_term_slug` : args( $term (object), $slug (string), $lang (string) ) / filter to process the term slug before is saved on the database.
* `qts_current_url` : args ( $url (string), $lang (string) ) / filter to process the entire url after it has been generated.
* `qts_permastruct` : args ( $permastruct (string), $name (string) ) / filter to process the permastruct, used for change the base.

== Installation ==

**This plugins requires [Qtranslate](http://wordpress.org/extend/plugins/qtranslate/) installed previously, if not, it will not activate.**

1. Upload `qtranslate-slug` to the `/wp-content/plugins/` directory.
1. Activate the plugin through the 'Plugins' menu in WordPress.
1. That's all!

= Changing base permastructs =

1. In admin: navigate to `Settings`/`Slug options`.
1. Set the base permastructs for `post types` and `taxonomies` (If you setup a base permastruct for `categories` or `tags` in *Settings/Permalinks*, these will be overwritten).
1. Save settings and that's all!

== Frequently Asked Questions ==

= It works with posts and pages, but with other content type? =

This plugin allows to translate slugs of: posts, pages, custom post types, categories, tags and custom taxonomies.

= Do I have to configure anything? =

If you want to translate also the base permastructs (ex. **category**, **tag**, etc). Visit the plugin settings page in the admin **Settings** > **Slug options**

= How can i insert a language selector in my theme ? =

You can choose to:
* use **Qtranslate Slug Widget** in your sidebar.
* place in your template `<?php if (function_exists('qts_language_menu') ) qts_language_menu('text'); ?>`. Options are: `dropdown`, `text`, `image`, and `both`.

= Appears an error 404, what can i do? =

In the admin go to **Settings** > **Permalinks** or **Settings** > **Slug options** and save.

== Screenshots ==

1. This screen shot description corresponds to screenshot-1.(png|jpg|jpeg|gif). Note that the screenshot is taken from
the directory of the stable readme.txt, so in this case, `/tags/4.3/screenshot-1.png` (or jpg, jpeg, gif)
2. This is the second screen shot

== Changelog ==

= 1.0 =
* new branch, the plugin has been rewritten: now the code is commented and wrapped inside a class, much code has change and the performance has been increased.
* no ID for slug type, then don't install `qtrasnlate_slug` table.
* slugs now are stored on meta tables, installation creates a termmeta table with some new *core functions* to access/save data, based on [simple term meta](http://wordpress.org/extend/plugins/simple-term-meta/).
* the plugin generates translated slug automatically from title in empty cases.
* the plugin checks if the slug already exists (per each language and `post_type`/`taxonomy`), and adds a progressive number in this case
* works on ajax requests for example when new taxonomies are created in edit post page.
* possibility to translate the base of permastructs for `post_types` and *taxonomies*, uses [$wp_rewrite](http://codex.wordpress.org/Class_Reference/WP_Rewrite).
* added some filters (see below).
* added plugin language textdomain (.pot file).
* new admin options page for save the base permastructs.
* import process when the plugin updates older versions.
* updated **Language selector Widget**.
* some bug fixes.
* some Qtranslate patches.

= 0.9 =
* some wordpress qTranslate bug fixes
* adds a javascript solution for qTranslate Nav Menus

= 0.8 =
* added support por Categories
* added support por Tags
* added support por Taxonomies
* added support por Custom Post Types

= 0.7 ( enhanced by [Zapo](http://www.qianqin.de/qtranslate/forum/viewtopic.php?f=4&t=1049&start=50#p7499) ) =
* added suport for qTranslate TLD domain mode (en: domain.com | fr: domain.fr) visit 

= 0.5 and 0.6 enhanched by Marco Del Percio =

== Upgrade Notice ==

= 1.0 =
Major version, the plugin has been rewritten. Better performance, and some enhancements.

= 0.9 =
This version fix some bugs and allow multilanguage in nav-menus.

= 0.8 =
A lot of slugs content allowed

= 0.7 =
This version allows TLD domain option for a different Qtranslate fork maded by Zappo

== Todo ==

* add support to translate attachment slugs
* expand qtranslate for translate attachment names and descriptions ( useful for galleries )
* qtranslate integration with other plugins like Jigoshop, e-commerce, etc.
