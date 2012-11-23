# Front-End QA Process

This document contains details of things to check on all projects before they launch.

## Validation

### Validate HTML

Use the [W3C HTML Validation](http://validator.w3.org/) service to ensure all pages / templates pass validation. Some errors caused by third-party iframes, such as Facebook Like buttons are unavoidable.

### Validate CSS

The [W3C CSS Validation](http://jigsaw.w3.org/css-validator/) service should be used to test all CSS. The results should be reviewed for errors, but CSS3 warnings can be ignored.

### Validate JavaScript

All JavaScript should be free of console errors and console logs. It should also be checked with [JSHint](http://www.jshint.com/) to conform to set best practices. Ensure all JS conforms to our [JavaScript Style Guide](https://github.com/bengourley/js-style-guide).


## Testing

### Browser Testing

All projects have an agreed level of required browser support. Ensure you know what it is, then test all pages and functionality on all of these browsers. Be sure to test major browsers on multiple operating systems.

## Device / Media Testing

If the project is responsive, check all breakpoints across multiple desktop, tablet and mobile devices running different operating systems, at different versions - not just Apple devices.

Ensure buttons and links are large enough to be used on touch based devices. Due to differing pixel densities, the recommended minimum size is around 7mm. Whilst this is not always possible, it's a good target to aim for.


## Accessibility

### CSS3 Fallbacks

Ensure all CSS3 has suitable fallback styling in place. Gradients should fallback to a sensible colour, content should still be usable without animations or transitions. If partially supported features, such as box-sizing have been used, supply a suitable polyfill.

### JavaScript Fallbacks

Reliance on JavaScript without fallbacks should be avoided. Ensure fallbacks provide a suitable experience and don’t leave non-JS users with missing content.

### Keyboard Navigation

It should be possible to tab through all relevant elements on a page. Focus styles should be noticeable enough that you can keep track of your location.

Keyboard navigation should also be enabled for JavaScript functionality where possible, for example pressing 'esc' on overlays and 'left' and 'right' within slideshows.

###Interaction

Buttons, links and other elements with interactions should have appropriate and noticeable hover, focus and active states. Ensure these are more than just a subtle colour change.

### Hiding Elements

Using `display: none;` in your CSS is the same as removing that content from the page completely. Ensure this is what you actually intend before using it. For text replacement, using the text-indent method or positioning an element off-screen would be a more suitable option.

### Print Stylesheets

Provide a simple print stylesheet for pages with important content, for example a news story or blog post. The stylesheet should remove superfluous layout elements to leave only the required content and minimal branding.


## Document Head

### Meta Tags

Ensure good use of the keywords and description meta tags. These should be bespoke on major pages / sections. Also make use of the author meta tag.

### Page Titles

Ensure these are relevant and make sense. Use a site description or strapline on the homepage and a reverse breadcrumb style elsewhere.

### Doctype / Character Encoding

Use the HTML5 doctype and UTF-8 character encoding.

### Extras

Ensure a favicon has been added and correctly linked

### Device Specific Enhancements

Ensure the site has mobile / tablet home-screen icons. Enable web-app capabilities and include multiple sizes of startup image.

### JavaScript

There should be as little JavaScript in the document head as possible, for example an HTML5 shim. If a Modernizr style script has been used, ensure it is only including and using the modules needed.


## Performance

### JavaScript

JavaScript files should be minified and potentially concatenated. If an external plugin is used, always include the minified version. If using external libraries such as jQuery UI, only include the specific modules needed. Load common assets such as jQuery from a CDN where possible.

### CSS

CSS files should be combined and minified. Consider whether 1 large file, or a few smaller files is appropriate for the project.


### Images

All images should be run through a lossless image compressor, such as [ImageOptim](http://imageoptim.com/). Make full use of image sprites whenever possible. SVGs should be optimised to remove Adobe bloat.

### Loading Resources

Ensure all resources on the page are loading correctly. There should be no 404 messages.

### Testing Performance

Use [Yahoo YSlow](http://developer.yahoo.com/yslow/) and [Google Pagespeed](https://developers.google.com/speed/pagespeed/) to check the performance of the site across all pages / template types. Aim to act on every possible recommendation and inform the Tech team if any improvements are reliant on them.

### Additional Pages / Content

Ensure that error pages for 404, 403, and 500 errors are set up. These should clearly explain what has happened and should give suggestions for other content or actions to assist the user.

