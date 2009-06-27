---
title: Railfrog
---

## Railfrog

Railfrog is a user-friendly, open-source website deployment and content management system built with Ruby on Rails, producing well structured and standards-compliant pages with Web 2.0 goodness.  Railfrog makes it easy for developers, designers, webmasters, or just about anyone else to deploy and manage a website.

**NOTE: These notes are TOTALLY out-of-date - please see work in progress at <http://github.com/railfrog/railfrogcms> for updates.**

If you're a Rails developer wanting to use Railfrog as an engine inside your project, there's probably enough information in these notes and `railfrogcms/README.md` to get started. If you do attempt this, please post to the mailing list with any problems. 

Much of the material below is liable to change as we port Railfrog from Rails 2.0 to Rails 2.3.

----

**Older docs**

  ruby script/plugin install http://svn.rails-engines.org/engines/trunk/

* Install acts_as_nested_set plugin:

  ruby script/plugin install http://svn.rubyonrails.org/rails/plugins/acts_as_nested_set/

* Install upload_progress plugin:

  ruby script/plugin install http://svn.rubyonrails.org/rails/plugins/upload_progress/

* Install Railfrog plugin:

  ruby script/plugin install http://svn.versiondude.net/railfrog/cms/railfrog/trunk

* Add following line to config/environment.rb, just after the require of Rails' boot file:

  require File.join(File.dirname(__FILE__), '../vendor/plugins/engines/boot')

* Add following line to config/routes.rb, just after first line:

  map.from_plugin :railfrog

* Run:

  ruby script/generate plugin_migration && rake db:migrate


### Configuration

* To enable Xinha editor add following line to your config/environment.rb
  
  Railfrog.xinha_enabled = true

_Update 2009-06-26: the xinha code now needs an `git submodule update --init` in the plugins/railfrog dir to pull in Xinha.


### How to use Railfrog

Start service by running script/server and open http://localhost:3000/admin

TBD


### How to create new site

You can find an example at vendor/plugins/railfrog/db/sites/railfrog 

To load example site from the file system run 

  rake railfrog:site:load SITE=vendor/plugins/railfrog/db/sites/railfrog


### Localization of Railfrog Control Panel

By default you get the English version of the Railfrog Control Panel. If you'd like 
to have a localized version of UI you can easily localize Railfrog. Railfrog uses 
the Globalite plugin (http://code.google.com/p/globalite/). To localize Admin UI 
you can just copy one of existing localization files eg:

  cp vendor/plugins/railfrog/lang/ui/ru.yml lang/ui

and add following line to your config/environment.rb file:

  Globalite.language = :ru

If you'd like to contribute a localization file please send it to railfrog mailing list:

  railfrog-dev@googlegroups.com


### History

Railfrog has been under development since June 2005, six months before
Rails 1.0 was released. That means there's a lot of cruft, which we try
to clear out and/or keep up to date -- but we need help with this :-)

You'll find previous experimental work on GitHub:

    <http://github.com/railfrog/railfrog-archive>

and the original code is also still in Subversion on CVSDude svn:

    svn -r 434 co https://svn.versiondude.net/railfrog/cms/railfrog/branches




