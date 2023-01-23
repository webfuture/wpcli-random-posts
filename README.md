# WP CLI Random Posts Generator

This WP CLI posts generator, unlike the core generator in WP CLI, supports the following:

* Terms
* Term Counts
* Taxonomies
* Post Types
* Post Counts
* Post Author
* Post Status
* Featured Images ( via picsum.photos )
* Image Download sizes
* Multi-site ( specify site id if necessary )

**NEW** - using `wp wfs-random cleanup <options>` this script now cleans up after itself.

> Thanks to [Loripsum.net](http://loripsum.net/) for providing the API for the content

**This does NOT create Gutenberg blocks**

## What this does NOT do
Currently this CLI command does not support meta-data, mainly due to the amount of commands you would need to run for large sites. Still a great script if you need to generate some placeholder posts fast, especially with featured images and terms.

 

## Sample Commands

### Generate 50 posts, no feature image
Possibly the simplest way to use the generator.
* `wp wfs-random generate 50`

### Create 10 posts with featured business images for an author
First find the author you want to attach the Post to
* `wp user list`

Now you know the author ID just use the `--author` flag like so:
* `wp wfs-random generate 10 --author=13 --featured-image --img-type=business`

### Create 10 posts with categories, tags, and featured images ( the usual stuff )
_( `--tax-n` tells the script to also add 15 terms to each taxonomy )_
* `wp wfs-random generate 10 --featured-image --tax=category,post_tag --tax-n=15`

### Clean up posts, terms, and media that was generated
_( `--force-delete` permanently deletes posts and media instead of just trashing them )_
* `wp wfs-random cleanup --tax=post_tag,category --media --force-delete`
 