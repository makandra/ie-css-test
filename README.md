# Internet Explorer + CSS = ☹

This repository is just to test several CSS issues (truths or myths) against Internet Explorer.

It contains some pages that have a text which should render with a green color. On all pages, that text is initially set to a red color and made green by rules further down the stylesheets.

Spoiler alert: Modern browser are not affected. IE up to version 9 is terrible.

## Issues tested

The following isses can be tested. (It's not like we have automated tests. Fire up IE and click yourself.)


### Selector limit

More than 4095 CSS selectors can be a problem:

   IE8  |   IE9  |  IE10  |  IE11
--------|--------|--------|--------
 ✘ fail | ✘ fail | ✔ pass | ✔ pass

IE8 and IE9 will understand only the first 4095 CSS selectors and ignore any from the 4096th on.

### Number of CSS files

More than 31 CSS files can be a problem:

   IE8  |   IE9  |  IE10  |  IE11
--------|--------|--------|--------
 ✘ fail | ✘ fail | ✔ pass | ✔ pass

Only the first 31 CSS files are loaded by IE8 and IE9. Any files included after these are ignored.

### CSS file size

There are some rumors on the interwebs about IE breaking at a file size around roughly 288 kilobytes.

We generate a CSS file of about 500 kb (when built statically) by using very long class names, but not many rules.

   IE8  |   IE9  |  IE10  |  IE11
--------|--------|--------|--------
 ✔ pass | ✔ pass | ✔ pass | ✔ pass

This actually works on all IEs. People were probably just hitting the selector limit around that size mark.

## Getting it running

It's a [middleman](http://middlemanapp.com/) application, just because it was easy to set up. Could probably be something smaller, but who cares?

The following is just a quick guide. If you need more information, please check the middleman documentation.

For development:

* `middleman server`
* connect to <http://localhost:4567/>

Building static HTML:

* `middleman build`
