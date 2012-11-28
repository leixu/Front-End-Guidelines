#Guidelines - HTML

##Overview

HTML is a markup language used to structure and display a content on the web. It is made up of text, headings, lists, links among other elements.

Writing semantic HTML is important. We should always write our optimal HTML before considering any CSS or JavaScript. It should always be possible to use and navigate a site without either of these things enabled. Content ordering and title hierarchy should be thought about and forms and links should all work.


##Best Practices

* Don't use `id` attributes, unless they are for anchor tags to target.
* HTML5 allows us to add attributes without quotes, but we always add them to increase consistency and readability.
* Avoid describing styles when deciding on class names: `class="button-primary"` is a better choice than `class="big-blue-button"`, especially when the time comes to redesign the site.


##Structure

* Keep use of nested `<div>` and `<span>` tags to a minimum. If you can't explain why you need it, get rid of it.
* Add an HTML comment to the closing tag of major elements. This will aid navigation of your source and will highlight nesting / indentation errors.


##Text

* Paragraphs of text should always be placed in a `<p>` tag. Never use multiple `<br/>` tags.
* `<br/>` tags should only be used for breaking text mid-paragraph, for example in an address.
* Use `<strong>` and `<em>` to add emphasis to text. `<b>` and `<i>` should be avoided.
* Avoid writing text in all caps or lowercase. Use CSS to achieve the same effect if required.


## Lists

* Use `<ul>`, `<ol>` and `<dl>` elements for information in list form – think carefully about which is most appropriate.
* Lists should 


##Tables

* Tables should be used for displaying tabular data – nothing else.
* Ensure all tables contain correct `<th>` headings and scope attributes


## Forms

* All form fields should have a suitable `<label>` element.
* Form fields shouldn't rely on a placeholder alone to indicate their intended content.
* Group sets of inputs in fieldsets, especially groups of radio buttons or checkboxes.


## Structure

We use the HTML5 doctype in all new projects. Within the `<head>` of the document, we define the character-set as UTF-8, and we use meta tags to define accurate page titles, descriptions and keywords.

After the metatags, we include relevant stylesheets, leaving any JavaScript to be included later on, before the closing body tag. Tracking and modernising JS is sometimes required in the head.

We add favicons and simple mobile-friendly information in the head too.

Any Facebook metadata resides within the head, but they invalidate the document so we only use these where necessary.


## HTML5

We try to use as much HTML5 as we can get away with, without relying on polyfills that force old browsers to work. The following HTML5 syntax will render gracefully in IE.

* New input types (date, number email, search tel, url) - Any browser incapable of rendering these elements will show a text input.
* Block level links.
* Input 'placeholder' attribute to provide information about required input - A label should still be visible.
* Use of the `<button>` element.

Some projects will require full HTML5 development, where old browsers are forced to render all new elements. This is not our current standard though.


## Accessibility

Accessibility is important for everything we produce. Here are some basic ways to ensure our products are accessible.

* Always provide alt text on images.
* Think about using microformats where possible – for example addresses and calendar events

[This section needs more information]


## Page Titles

Out format for page titles is:

**Homepage**

`<title>Site Name - A short description of the site</title>`

**Sub-Section Page**

`<title>Section Name / Site Name</title>`

**Article Page**

`<title>Article Name / Section Name / Site Name</title>`


## Validation

We always aim to achieve 100% valid HTML markup. It helps avoid bugs, affects a product's SEO and should be very carefully considered when building a site. The Web Developer extension for Firefox or Chrome allows you to easily validate locally running files.