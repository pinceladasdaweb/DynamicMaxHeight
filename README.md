# Dynamic max height plugin
> ...or how to animate to an unknow height with CSS and pure JavaScript

## What is it?

This is a pure JavaScript plugin to dynamically check a layer height and compare it to a custom height value.
If layer height is higher than that custom value (data-maxheight), a "show more" button and a bottom gradient will appear.

It works with CSS3 transition to get a smooth animation.

## Demo

View [demo here](http://www.pinceladasdaweb.com.br/blog/uploads/dynamicheight/)

## Getting Started

```bash
# Get the latest snapshot
$ git clone git@github.com:pinceladasdaweb/DynamicMaxHeight.git
```

## How to use?

### Javascript initialization

Dynamic max height is a [Vanilla JS](http://vanilla-js.com/) plugin with no dependencies. Include the [`dynamicmaxheight.min.js`](build/dynamicmaxheight.min.js) before your ```</body>``` tag and initialise it:

```html
<script src="path/to/dynamicmaxheight.min.js"></script>
<script>
    DynamicMaxHeight({
        selector: '.dynamic-max-height'
    });
</script>
```

You can also load the plugin via AMD (require.js):

```html
<script>
require(["path/to/dynamicmaxheight.min.js"], function(DynamicMaxHeight) {
    DynamicMaxHeight({
        selector: '.dynamic-max-height'
    });
});
</script>
```

### HTML

The plugin depends on the following HTML structure:

```html
<div class="dynamic-max-height" data-maxheight="70">
    <div class="dynamic-wrap">
        <p> My life fades. The vision dims. All that remains are memories. I remember a time of chaos... ruined dreams... this wasted land. But most of all, I remember The Road Warrior. The man we called "Max." To understand who he was, you have to go back to another time... when the world was powered by the black fuel... and the desert sprouted great cities of pipe and steel. Gone now... swept away. For reasons long forgotten, two mighty warrior tribes went to war, and touched off a blaze which engulfed them all. Without fuel they were nothing. They'd built a house of straw. The thundering machines sputtered and stopped. Their leaders talked and talked and talked. But nothing could stem the avalanche. Their world crumbled. The cities exploded. A whirlwind of looting, a firestorm of fear. Men began to feed on men. On the roads it was a white line nightmare. Only those mobile enough to scavenge, brutal enough to pillage would survive. The gangs took over the highways, ready to wage war for a tank of juice. And in this maelstrom of decay, ordinary men were battered and smashed... men like Max... the warrior Max. In the roar of an engine, he lost everything... and became a shell of a man... a burnt-out, desolate man, a man haunted by the demons of his past, a man who wandered out into the wasteland. And it was here, in this blighted place, that he learned to live again.</p>
    </div>
</div>
```

### CSS

Minimal CSS Rules for the plugin:

```css
.dynamic-wrap {
    transition: max-height 0.25s ease-in-out;
    width: 100%;
    overflow: hidden;
    position: relative;
}

.height-active .dynamic-wrap:before{
    content: '';
    position: absolute;
    left: 0px;
    right: 0;
    bottom: 0;
    height: 30px;
    background: -moz-linear-gradient(top, rgba(240, 249, 255, 0) 0%, rgba(255, 255, 255, 1) 100%);
    background: -webkit-gradient(linear, left top, left bottom, color-stop(0%, rgba(240, 249, 255, 0)), color-stop(100%, rgba(255, 255, 255, 1)));
    background: -webkit-linear-gradient(top, rgba(240, 249, 255, 0) 0%, rgba(255, 255, 255, 1) 100%);
    background: -o-linear-gradient(top, rgba(240, 249, 255, 0) 0%, rgba(255, 255, 255, 1) 100%);
    background: -ms-linear-gradient(top, rgba(240,249,255,0) 0%, rgba(255, 255, 255, 1) 100%);
    background: linear-gradient(to bottom, rgba(240, 249, 255, 0) 0%, rgba(255, 255, 255, 1) 100%);
    z-index: 1;
}
```

## Options

The script expect the following attributes in the html tag:

| Value                              | Description                                                              |
| ---------------------------------- |:------------------------------------------------------------------------:|
| **data-maxheight**                 | Change "data-maxheight" in each item to set a different max height value |

##Browser Support

![IE](https://raw.githubusercontent.com/alrra/browser-logos/master/internet-explorer/internet-explorer_48x48.png) | ![Chrome](https://raw.githubusercontent.com/alrra/browser-logos/master/chrome/chrome_48x48.png) | ![Firefox](https://raw.githubusercontent.com/alrra/browser-logos/master/firefox/firefox_48x48.png) | ![Opera](https://raw.githubusercontent.com/alrra/browser-logos/master/opera/opera_48x48.png) | ![Safari](https://raw.githubusercontent.com/alrra/browser-logos/master/safari/safari_48x48.png)
--- | --- | --- | --- | --- |
IE 10+ ✔ | Latest ✔ | Latest ✔ | Latest ✔ | Latest ✔ |

## Thanks

Many thanks to [Joan Claret](https://github.com/JoanClaret/jquery-dynamic-max-height), who originally created the plugin for jQuery.

## Contributing

Check [CONTRIBUTING.md](CONTRIBUTING.md) for more information.

## History

Check [Releases](https://github.com/pinceladasdaweb/DynamicMaxHeight/releases) for detailed changelog.

## License
[MIT](LICENSE)