# Mosaico - Responsive Email Template Editor

## Introduction
This repository was forked to use a custom implementation of many features like changing UI colors, adding TinyMCE plugins and more.

Mosaico is a JavaScript library (or maybe a single page application) supporting the editing of email templates.
The great thing is that Mosaico itself does not define what you can edit or what styles you can change: this is defined by the template. This makes Mosaico very flexible.


![Mosaico Screenshot](res/img/screenshot.png)


At this time we provide a single template to illustrate some best practice examples: more templates will come soon!

## Integration
Whenever a change is made the `grunt` process generates minified resources based on the code in the `dist` folder. After finishing a feature and pushing to master those files and folders should be copied to the corresponding folders under `vendor` on the therapydia repository.

### Live demo
On https://mosaico.io you can see a live demo of Mosaico: the live deploy has a custom backend (you don't see it) and some customization (custom Moxiemanager integration, customized onboarding slideshow, contextual menu, and some other small bits), but 95% of what you see is provided by this library. You will also see a second working template there: we are still working to open source it. Stay tuned!

#### News

Subscribe to our newsletter to get updates: http://mosaico.voxmail.it/user/register

### More Docs from the Wiki

[Mosaico Basics](https://github.com/voidlabs/mosaico/wiki)

[Developer Notes](https://github.com/voidlabs/mosaico/wiki/Developers)

### Build/Run  [![Build Status](https://travis-ci.org/voidlabs/mosaico.svg)](https://travis-ci.org/voidlabs/mosaico)

You need NodeJS v6.0 or higher + ImageMagick

this may raise warnings about Knockout, ignore them. It will probably fail on some colorpicker dependency, just run it again and will work:
```
  npm install
```
if you don't have it, install grunt-cli globally
```
  npm install -g grunt-cli
```
compile and run a local webserver (http://127.0.0.1:9006) with incremental build and livereload
```
  grunt
```
*IMPORTANT* in order to use image uploading/processing feature in Node you need imageMagick installed in your environment.
e.g. running "convert" and "identify" on the command line should output imageMagick command line help (if you are on Windows and install imageMagick 7.x then make sure to install ["legacy utilities"](https://github.com/aheckmann/gm/issues/559)).

*NOTE* we have reports that default Ubuntu node package have issues with building Mosaico via Grunt. If you see a ```Fatal error: watch ENOSPC``` then have a look at https://github.com/voidlabs/mosaico/issues/82

### Docker

We bundle a small Dockerfile based on centos7 to test mosaico with no need to install dependencies.
```
docker build -t mosaico/mosaico .
docker run -p 9006:9006 mosaico/mosaico
```
then open a browser to point to the port 9006 of your docker machine IP.

