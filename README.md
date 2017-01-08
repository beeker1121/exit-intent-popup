exit-intent-popup
=================

# Features

* Fully customizable via HTML and CSS.
* Can use third party forms to collect emails.
* Support for embeddable CSS fonts, including Google Fonts.
* Cookie support with optional expiry date.
* Set a timed delay before the script starts tracking exit intent.
* Display popup based on exit intent or timed delay.
* Scales to adjust to window size.

# Usage

Simply include the script and call its `init` function with any options you choose.  You must add in your own HTML otherwise the popup will be blank.

```html
<script type="text/javascript" src="bioep.min.js"></script>

<script type="text/javascript">
    bioEp.init({
        // Options
    });
</script>
```

You can also add HTML and CSS directly on the page.  The popup element you wish to use must have an id of `bio_ep`.

```html
<head>
    <script type="text/javascript" src="bioep.min.js"></script>

    <script type="text/javascript">
        bioEp.init({
            // Options
        });
    </script>
    
    <style type="text/css">
        #bio_ep_bg {} // background
        #bio_ep {} // popup
        #bio_ep_close {} // close button
	</style>
</head>
<body>
    <div id="bio_ep">
        <!-- your popup HTML goes here -->
    </div>
</body>
```

# Template

Using HTML and CSS

```javascript
bioEp.init({
	html: '<div id="bio_ep_content">' +
		'<img src="http://beeker.io/images/posts/2/tag.png" alt="Claim your discount!" />' +
		'<span>HOLD ON!</span>' +
		'<span>Click the button below to get a special discount</span>' +
		'<span>This offer will NOT show again!</span>' +
		'<a href="#YOURURLHERE" class="bio_btn">CLAIM YOUR DISCOUNT</a>' +
		'</div>',
	css: '#bio_ep {width: 400px; height: 300px; color: #333; background-color: #fafafa; text-align: center;}' +
		'#bio_ep_content {padding: 24px 0 0 0; font-family: "Titillium Web";}' +
		'#bio_ep_content span:nth-child(2) {display: block; color: #f21b1b; font-size: 32px; font-weight: 600;}' +
		'#bio_ep_content span:nth-child(3) {display: block; font-size: 16px;}' +
		'#bio_ep_content span:nth-child(4) {display: block; margin: -5px 0 0 0; font-size: 16px; font-weight: 600;}' +
		'.bio_btn {display: inline-block; margin: 18px 0 0 0; padding: 7px; color: #fff; font-size: 14px; font-weight: 600; background-color: #70bb39; border: 1px solid #47ad0b; cursor: pointer; -webkit-appearance: none; -moz-appearance: none; border-radius: 0; text-decoration: none;}',
	fonts: ['//fonts.googleapis.com/css?family=Titillium+Web:300,400,600'],
	cookieExp: 0
});
```

Using an image

```javascript
bioEp.init({
	width: 394,
	height: 298,
	html: '<a href="#YOURURLHERE" title="Claim your discount!"><img src="http://beeker.io/images/posts/2/template2.png" alt="Claim your discount!" /></a>',
	cookieExp: 0
});
```

# Options

All options must be added to the init function as an object.

Name | Type | Default | Description
-----|------|---------|------------
**width** | integer | 400 | The width of the popup. This can be overridden by adding your own CSS for the #bio_ep element.
**height** | integer | 220 | The height of the popup. This can be overridden by adding your own CSS for the #bio_ep element.
**html** | string | blank | The HTML code to be placed within the popup. HTML can be added through this function or on the page itself within a element.
**css** | string | blank | The CSS styles for the popup. CSS can be added through this function or on the page itself.
**fonts** | array | null | An array containing URLs that link to font stylesheets. Google Fonts was the main idea behind this feature.
**delay** | integer| 5 | The time, in seconds, until the popup activates and begins watching for exit intent. If showOnDelay is set to true, this will be the time until the popup shows.
**showOnDelay** | boolean | false | If true, the popup will show after the delay option time. If false, popup will show when a visitor moves their cursor above the document window, showing exit intent.
**cookieExp** | integer | 30 | The number of days to set the cookie for. A cookie is used to track if the popup has already been shown to a specific visitor. If the popup has been shown, it will not show again until the cookie expires. A value of 0 will always show the popup.
**showOncePerSession** | boolean | false | If true, the popup will only show once per browser session. If false and cookieExp is set to 0, the popup will show multiple times in a single browser session.
**onPopup** | function | null | A callback function to be called when the popup is displayed in the browser.

# License

MIT license, feel free to use however you wish!

Created by [beeker.io](http://beeker.io/exit-intent-popup-script-tutorial)