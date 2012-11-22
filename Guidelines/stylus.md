# Guidelines - Stylus (Work in Progress)

## Overview

When writing Stylus, use the same guidelines as when writing CSS. However, there are a few major differences to keep in mind.


## General Syntax

Whilst you can write Stylus as if it were standard CSS, we prefer to remove all unnecessary punctuation and repetition. When using multiple selectors, we write each on a new line, without trailing commas.

**Bad**

    .class1, .class2
      position: relative;
      color: blue;

    .class1:hover, .class2:hover
      color: red;

**Good**

    .class1
    .class2
      position relative
      color blue

      &:hover
        color red

There are some rare exceptions to the multiple selectors on new lines rule. These mainly occur in the base stylesheet. Use your judgement to decide if selectors benefit from being on one line:

**Good**

    h1, h2, h3, h4, h5, h6
      font-weight bold


## Quotes

While we always use double quotes for standard CSS, we use single quotes in Stylus. These are quicker and easier to write, and automatically compiled to double quotes when the CSS is generated.


## Nesting

One of the most important things to understand when writing CSS through a pre-processor, is how your final compiled CSS will look. What saves loads of time in development, can produce bloated slow code that will forever degrade the performance of your end product. This is related to the "Over Qualifying Selectors" section of the CSS Guidelines.

**Bad**

    body
      .main-header
        ul.main-navigation
        width 100%
        li
          float left
          a
            color #555
            &:hover
              color #000

Compiles to:

    body .main-header ul.main-navigation {
      width: 100%;
    }
    body .main-header ul.main-navigation li {
      float: left;
    }
    body .main-header ul.main-navigation li a {
      color: #555;
    }
    body .main-header ul.main-navigation li a:hover {
      color: #000;
    }

**Good**

    .main-navigation
      width 100%
      li
        float left
      a
        color #555
        &:hover
        color #000

Compiles to:

    .main-navigation ul {
      width: 100%;
    }
    .main-navigation li {
      float: left;
    }
    .main-navigation a {
      color: #555;
    }
    .main-navigation a:hover {
      color: #000;
    }

These achieve the same effect, but the first example takes 36% more code to do the same thing. That is a lot of extra code for such a small example - imagine that same effect across an entire project!

Be aware of indentation levels and be sure that the things you are nesting definitely need to be nested.

Notice in the second example that the li styles aren’t nested inside the ul styles, and the a styles aren’t nested inside the li styles. We can do this with confidence, as we know that all links within .main-navigation should be within li elements, which themselves will live inside a list element. Our CSS doesn’t need to know this.

Also notice that we didn’t need to tell our CSS that the .main-navigation appears within the .main-header or the body. It will be styled the same regardless.
            
