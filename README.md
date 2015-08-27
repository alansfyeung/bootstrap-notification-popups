# Bootstrap Popup Notifications
A clean, Win8-inspired corner popup for notifications in Bootstrap

## Installation
Requires jQuery 
Requires the [Bootstrap3](http://getbootstrap.com/ "Bootstrap 3") framework
Requires [CSS3 transitions compliant](http://caniuse.com/#feat=css-transitions) browser

> Sorry, currently I only have the LESS source, you'll need to either compile it yourself to CSS, or include it into the Bootstrap3 LESS source then compile it. 

1. Drop `/js/notification-popups.js` into your project's JS folder
2. Drop `/src/less/alerts.less` into your LESS folder before compilation, overwriting the original alerts.less
3. Optionally, drop `/src/less/alert-colors.less` into your LESS folder, and if so, update your bootstrap.less to import this file


## Using it 
### Variant 1
In true Bootstrap fashion, you may use a `data-trigger=popup` attribute on any button or link element.
    <button class="btn btn-primary" data-trigger="popup">Hit me to see a popup</button>

You'll also need to add other data-* attributes in order to make it worth your while
    <button class="btn btn-primary" data-trigger="popup" data-type="success" data-title="Headline: " data-text="You have 1 new inbox" data-time="5">Hit me</button>

### Variant 2
Call the popup programmatically, as a jQuery extension.
    $.alert({ ... options ... });

    
## Options
These options can be specified in the { ... options... } object, or can be prefixed with data-* and inserted as an attribute.
    type                  A string, either 'info', 'success', 'warning' or 'danger'
    title                   A short title for the popup, displayed in bold
    text                   The text body for the popup, displayed after the title
    time                   Number of seconds before the popup disappears
    classNames      Any other classnames that you would like to whack onto the popup container
    
## Caveats
+   Sorry, at the moment the transition-in is a fade, and the transition-out is a slide; I hope to make this configurable in the future.
+   LESS source is tightly coupled with BS3 mixins and variables, BS4 looks like it'll be a SASS-only framework, so...
+   $.alert() may be a popular name in the jQuery namespace; use `$.alert.noConflict()` to revert this name
