
This is the source code/files for the ehcache.org website.  The files in this repository are source files, some of which include templating and other raw bits that need to be "compiled"/"built" in order to have files that are suitable to go onto a webserver.

### Instructions for building/previewing

* On Mac OS X, install Xcode command line tools by executing: `xcode-select --install`

* Install Jekyll if you have not - follow instructions on the Jekyll home page (after first installing Ruby)
[http://jekyllrb.com/](http://jekyllrb.com/)

* Run `gem install bundle`

* Clone this repository to your local system (if you're going to contribute content, fork it first, and clone that)
* cd into the "ehcache.github.io" directory
* "git checkout ehcache.org" to switch to this branch

* Install dependencies with: `bundle install`

* To generate the *full* site including Ehcache 3 docs, you need to do the following:
  * within the root your clone of this repository, the contents of ehcache3 repository needs to be linked/or copied as "_eh3"
  * within the root your clone of this repository, the contents of ehcache3 repository's docs/src/docs/asciidoc/user folder needs to be linked/or copied as "documentation/3.0"

* To generate and view (locally serve) the site "bundle exec jekyll serve -w"   ( then point your browser at http://localhost:4000" )

* To simply generate the site "jekyll build"

---


### TODOS:

* "About" -> "Features" page:
  * could still use some love, but isn't so bad anymore

---

### Making Changes to the content

If you want to make changes to the website, make them here (in this repository) - as this is where all the source/files for the website are kept.

For instance:

* If there is a new release being made, generated javadoc (from the product build) should be put into the "apidocs" directory
* New official docs should be put into the "documentation" and/or "generated" directories as appropriate
* Pay attention to the content of the _config.yml file in the root of this repository as there are properties there that control various things just as which exact version of javadoc to show for what (e.g. at the time of this writing we link to "2.8.5" javadoc for all "2.8" documentation).


* After making your changes, commit them (remember to do your work in a branch) and create a pull request.

---

### Deploying changes to the live webserver

ehcache.org is served/hosted by github.   The webserver does NOT serve the content from this repository.  It serves the exact content of the repository at:  https://github.com/ehcache/ehcache.github.io

* Build the site content according to the directions above (using the source files from this (ehcache.org-site) repository)
* After the site content is built, it will be in the _site directory
* Clone a local copy (or if you have one already, pull in all updates) of the ehcache.github.io repository
* Create a branch for your updates, and switch to (checkout) that branch
* Copy all content from the _site directory you just built from this repository into the root of your new branch of the other repository - this will mean some existing files get overwritten, and some new files get added.  If you need to remove files (if you removed files on the source side which are no longer in the built site - you'll need to manually delete them from your branch).   Note that you should not end up with a directory called "_site" in the destination - the stuff inside the "_site" folder after building with jekyll is what goes at the root of the website content.
* Commit your changes and make a pull request to get the content of that branch into the master branch of the ehcache.github.io repository (which will then make it "live").


### Contributing a blog post

1. Ensure you first edit `_data/authors.yml` to add you information

2. Create a new ASCII Doc file under `_posts/blog`. The file should be named with the following format: `yyyy-MM-DD-title-in-lowercase.adoc`

3. Add a header in your file. Modify the fields according to your post, especially for the title, headline, tags, authors and date

```
layout: post
title: "Your blog post title"
headline: "Your blo post headline"
categories: blog
hidden: false
author: your_author_key
tags: [ehcache, website]
date: 2016-05-04T18:00:00-05:00
modified:
```

4. Send your pull request :+1:

### Contributing an external resource

Same rules apply as above, except that you have to put your file into `_posts/resources` and add a header like this one:

```
title: "Ehcache 3: JSR-107 on steroids"
headline: "Ehcache 3: JSR-107 on steroids at Devoxx Morocco by Louis Jacomet"
categories: resources
date: 2015-11-18T00:00:00-00:00
``

__IMPORTANT:__ Yout content MUST be short! Links, headline, title, that's all.


