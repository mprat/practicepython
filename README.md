practicepython
==============

markdown notes for the practice python blog: http://practicepython.blogspot.com

Exercises published:
* Jan 27, 2014 - 1-character-input.md
* Feb 5, 2014 - 2-odd-or-even.md


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
