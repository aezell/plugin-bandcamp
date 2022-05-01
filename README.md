# plugin-bandcamp

A customizable Bandcamp plugin for Micro.blog

## Description

[Bandcamp](https://bandcamp.com) is a music listening and buying site catering to artists of all kinds. It allows the artists to sell digital and physical goods to their fans with full control and better payouts than other online systems.

This plugin provides a [Hugo shortcode](https://gohugo.io/content-management/shortcodes/) for your Micro.blog that makes it easy to add embeddable Bandcamp players for URLs of music you'd like to share. There is some light customization available via parameters to the short code.

## Requirements

Because of how the parameters are parsed in this shortcode, you'll need to use the `Hugo 0.91` option to build your Micro.blog site. You can change this on the Design page. Just be warned that if you aren't already using `0.91` you may run into some compatibility issues with your theme or other customizations when you switch.

## Basic Usage

The simplest usage of the Bandcamp shortcode works like this:

```html
{{< bandcamp `https://jakexerxesfussell.bandcamp.com/album/good-and-green-again` >}}
```

The URL must be in backticks otherwise we get a Hugo parsing error. It could be auto-converted by MB to the markdown for a link. In the advanced usages below, we can keep the regular doublequote usage or use backticks as well. Either will work but for this shortest form, it must be backticks.

## Screenshot

![simple_shot](https://user-images.githubusercontent.com/2454/166129522-0903dc79-b263-4001-b702-aa35b54d11f8.png)

## Advanced Usage

If you use some named parameters, you can customize the layout of your Bandcamp widget, like this:

#### Fancy with small art and full tracklist for a dark theme
```html
{{< bandcamp url="https://jakexerxesfussell.bandcamp.com/album/good-and-green-again" layout="standard-small-art" tracklist="true" theme="dark" >}}
```

#### That same layout but with the light theme
```html
{{< bandcamp url="https://jakexerxesfussell.bandcamp.com/album/good-and-green-again" layout="standard-small-art" tracklist="true" theme="light" >}}
```

#### And now with no tracklist
```html
{{< bandcamp url="https://jakexerxesfussell.bandcamp.com/album/good-and-green-again" layout="standard-small-art" tracklist="false" >}}
```

#### There's one for folks that love bigger art
```html
{{< bandcamp url="https://jakexerxesfussell.bandcamp.com/album/good-and-green-again" layout="standard-big-art" >}}
```

#### Or no art
```html
{{< bandcamp url="https://jakexerxesfussell.bandcamp.com/album/good-and-green-again" layout="standard-no-art" tracklist="true" >}}
```

#### Or only art
```html
{{< bandcamp url="https://jakexerxesfussell.bandcamp.com/album/good-and-green-again" layout="artwork-only" >}}
```

#### You can even make it slim
```html
{{< bandcamp url="https://jakexerxesfussell.bandcamp.com/album/good-and-green-again" layout="slim-with-art" theme="dark" >}}
```

## Notes

The possible layout options are:
- artwork-only
- slim-with-art
- slim-no-art
- standard-big-art
- standard-small-art
- standard-no-art

The `tracklist` parameter is only supported with the `standard` layouts.

Themes are currently limited to `light` or `dark`. The Bandcamp embed takes RGB hex values in its path but it ignores anything that isn't one of two background colors. Similarly, a small set of link colors are supported by the embed but are not currently supported by this plugin.

Only album URLs are currently supported. If you'd like to embed a specific track from Bandcamp, you should use their embed tool to get the HTML
