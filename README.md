# Internet Explorer + CSS = ☹

This repository is just to test several CSS issues (true or myths) against Internet Explorer.

It contains some pages that have a text which should render with a green color. On all pages, that text is initially set to a red color and made green by rules further down the stylesheets.

Spoiler alert: Works in all sane browsers but IE breaks.

## Issues tested

So far, this allows to "test" the following issues. (It's not like we have automated tests. Fire up IE and click yourself.)

### Selector limit

IE will understand only the first 4095 CSS selectors and ignore any from the 4096th on.

Tested with IE 8 and 9; both broken.

### Number of CSS files

Only the first 31 CSS files are loaded by Internet Explorer.

Any files included after these are ignored.

Tested with IE 8 and 9; both broken.

### CSS file size

There are some rumors on the interwebs about IE breaking at a file size around roughly 288 kilobytes.

We generate a CSS file of about 500 kb (when built statically).

Tested with IE 8 and 9, none broke. People were probably just hitting the selector limit.

## Getting it running

It's a [middleman](http://middlemanapp.com/) application, just because it was easy to set up. Could probably be something smaller, but who cares?

The following is just a quick guide. If you need more information, please check the middleman documentation.

For development:

* `middleman server`
* connect to <http://localhost:4567/>

Building static HTML:

* `middleman build`