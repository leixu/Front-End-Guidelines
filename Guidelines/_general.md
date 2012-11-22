# Guidelines - General

## Overview

This document outlines core processes we have in place, to ensure our work is to the highest possible standard. It should also help create a default state for our code, to make it seamless when passing work between members of the production staff.
Browser Support

Unless client requirements stipulate otherwise, our full list of browser support is the current version and 1 version previous of:

* Chrome
* Firefox
* Safari
* Opera
* Android Default Browser
* iOS Safari

Internet Explorer should be supported form IE7+ and we should endeavour to ensure this happens, even on projects which specify IE8+. IE6 should be considered, but does not need to function as fully as in the above – an acceptable level of usability is expected where possible though.

Everything we produce should be tested in all browsers available, on Windows, Mac as well as mobile browsers.


## Text Editor Setup

Choice of application is up to you. Most members of staff are currently using Sublime Text 2.

We use spaces for indentation, set to a two-space tab width. We also trim all trailing whitespace when saving (with the exception of Jade files). Please ensure these are both set correctly in your editor.

[Jackbrewer](https://github.com/jackbrewer) on GitHub has made some [HTML](https://github.com/jackbrewer/html-plus.tmbundle) and [CSS](https://github.com/jackbrewer/css-plus.tmbundle) bundles that speed up dev time in TextMate and Sublime. His [Sublime settings](https://github.com/jackbrewer/Sublime-Settings) are also available to aid with Sublime setup.


## Version Control

All our projects use Git for version control to ensure the team can efficiently work simultaneously on a project.

Our projects are hosted on [Github](http://github.com/clocklimited), or on a private server. For a good introduction to Git, visit [GitHub's Getting Started Guide](http://try.github.com/).


## Optimisation

The time taken for websites to load directly impacts user experience. There are lots of ways to optimise page speed, with the most common being minimising HTTP requests.

> "80% of the end-user response time is spent on the front-end. Most of this time is tied up in downloading all the components in the page: images, stylesheets, scripts, Flash, etc. Reducing the number of components in turn reduces the number of HTTP requests required to render the page. This is the key to faster pages."
>
>*Yahoo Developer Network*

One way to reduce HTTP requests is by being careful not to use too many scripts or stylesheets – we often combine multiple files before they are output to the browser.

Another way to increase page speed is to optimise images. We should always use image sprites to combine images where possible and all images should be run through a lossless image compressor such as [ImageOptim](http://imageoptim.com/) before being deployed.

## Accessibility

[This section needs writing]

## Useful Links

Mozilla Developer Network for [CSS](https://developer.mozilla.org/en/CSS) / [HTML](https://developer.mozilla.org/en/HTML).
Official jQuery documentation - [docs.jquery.com](docs.jquery.com).
Dochub - useful collection of [HTML](http://dochub.io/#html/), [CSS](http://dochub.io/#css/), [JavaScript](http://dochub.io/#javascript/), [jQuery](http://dochub.io/#jquery/) documentation (aggregated from other sources).