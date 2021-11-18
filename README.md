practicepython
==============

markdown notes for the practice python blog: http://practicepython.com


Local installation
==================
Linux:

```
sudo apt-get install ruby ruby-dev
sudo gem install bundler
sudo gem install jekyll
```

To build locally using Jekyll
===================
The first time you clone the repo, to make sure you have the `github-pages` gem installed:

```
bundle install
```

Every time you want to preview the site. By default, will watch for changes.
```
bundle exec jekyll serve
```
