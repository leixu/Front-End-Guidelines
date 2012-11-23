# Guidelines - CSS

##Overview

We try to keep stylesheets as easy to read as possible, using line-breaks between rules. We aggregate our styles before they get output to the browser, removing any extra whitespace to save on file size.


###Code Formatting

* Use lowercase with hyphens for classes.
* Use 2 spaces to indent code.
* Put a space before { in rule declarations.
* Put a space after : in property declarations.
* Don’t add a unit to 0 (zero) values. 0px is the same as 0% or 0em, so there is no need to specify the unit
* Use hex colours. These should be in lowercase and shorthand where possible – for example: `#fff`. If you need transparency use rgba() but think about whether you need to supply a fallback hex colour for browsers which don’t provide support for the alpha channel.


**Good:**

    .button-action {
      padding: 0;
      color: #eee;
      background-color: #999;
      background-color: rgba(0, 0, 0, 0.8);
    }


## Shorthand

Shorthand can be used for properties that have integer or hex-based values, but background and font values should always be separated out into individual parameters to increase readability, reusability and decrease the temptation for over-repetition.

**Good:**

    padding: 2px 10px;
    background-image: url("/images/image.jpg");
    background-position: 0 50%;
    background-repeat: repeat;

**Bad:**

    padding-top: 2px;
    padding-right: 10px;
    padding-bottom: 2px;
    padding-left: 10px;
    background: url("/images/image.jpg") 0 50% repeat;


## CSS3

We embrace progressive enhancement – CSS3 is a big part of that. Using browser vendor prefixes, we add rounded corners, shadows, multiple background images, background sizes, angles, gradients, animations (and so on), to embellish a strong base level experience that older browsers can provide.

CSS3 is a powerful and lightweight way to reward more advanced users, but the most basic experience needs to be considered first and foremost.

Look out for CSS3 properties (such as border radius) which no longer need vendor prefixes. [html5please.us](http://html5please.com/) is a useful resource for checking current levels of browser support.


## Vendor Prefixes

To ensure maximum compatibility with all major browsers, we use four vendor prefixes for any CSS3 properties used – Webkit, Mozilla, Microsoft and Opera.

These should be indented with spaces so the properties line up. This allows for easier multi-line editing in text-editors. The unprefixed version of the property should always appear last.

    -webkit-transform: scale(2)
       -moz-transform: scale(2)
        -ms-transform: scale(2)
         -o-transform: scale(2)
            transform: scale(2)


## Web Fonts

Wherever possible we use web fonts instead of image sprites, Flash or JavaScript techniques on our sites. It saves on creating large image sprites or relying on plugins. It also makes content management much easier.

When using non-websafe fonts, we make use of CSS @font-face, utilising the [Fontspring @Font-Face Syntax](http://www.fontspring.com/blog/the-new-bulletproof-font-face-syntax). We source our fonts from legal web font providers such as [Font Squirrel](http://www.fontsquirrel.com/), [Google Web Fonts](http://www.google.com/webfonts), [Typekit](https://typekit.com/) and [MyFonts](http://www.myfonts.com/search/is_webfont:true/webfonts/?view=list).


## IE Stylesheets

Internet Explorer hacks should be avoided wherever possible. On the rare occasion that an IE bug can't be fixed with regular CSS, we move our IE-relevant hacks into their own stylesheet. This is included in the head of the document as follows:

    <!--[if lt IE 9]>
      <link rel="stylesheet" href="internet-explorer.css">
    <![endif]-->

Media Queries aren't supported in IE8 and older. When building responsive 'Mobile First' sites, any desktop styles that live within media queries will need to be duplicated into an IE stylesheet, without their containing media query.

Everything that is added to IE stylesheet should be well commented so other developers know exactly what is being affected.


## Sensible Selectors

#### ID attributes

Don't style IDs with CSS. IDs should be used for anchor link targets and JS hooks only. They have a *much* higher specificity and cannot be used more than once on a page. Using classes allows for easier specificity calculating and give the option that a component *could* be reused - however unlikely.

#### Directly Styling Elements

Be cautious about directly styling elements, e.g. `div` or `header`. Will every instance of that element *always* need those styles?

#### Over Qualifying Selectors

Writing concise, reusable CSS is very important increasing readability and maintainability, and for reducing file size. Be careful to not over qualify your selectors by chaining too many elements / classes for one rule.

**Bad:**

    header ul.main-navigation li a {
      color: #555
    }

In the 'bad' example, there is no reason to specify that the `.main-navigation` class needs to live in the `<header>` element. What if we need to move it?

We are also saying that the `.main-navigation` class can only ever be applied to a `<ul>`. What if we need to switch to an `<ol>`?

We know that every `<a>` within our `.main-navigation` (which is a list) will be located inside an `<li>` – it would be invalid if it weren't. This means we don't need to specify `li a` in our selector, we can simply use `a`.

Think about ways you can reduce the number of elements in your selectors to increase performance and decrease file size.

**Good:**

    .main-navigation a {
      color: #555
    }


## Code Commenting

Within well organised files, code comments are invaluable to help developers navigate through projects and complete their work.

CSS files should have a title at the top, describing the file's purpose.

Each section of the file should be grouped according to content and relevance, and titles should be used to clearly identify what a group of styles is for. Within these, sub-headers can be used to identify certain related content styles.

[This section needs examples of CSS comments]


## Accessibility

Test navigation without mouse
Don't use display: none; for image replacement
Think carefully any time display: none; is used

[This section need explanations and further detail]