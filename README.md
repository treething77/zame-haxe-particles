# Particle system for OpenFl

Features:

 - Can load .plist files from Particle Designer or [Particle Designer 2](https://71squared.com/en/particledesigner).
 - Has drawTiles renderer along with GL renderer.

**NOTE: work in progress, more features coming.**

## Export notes

Embedded textures is not supported, so you must **uncheck** "embed" before export.
![](http://blog.zame-dev.org/wp-content/uploads/2015/02/particledesigner.png)

## Renderer notes

GL renderer is the best choise for html5 (with -Ddom) - it support many features and super fast. It use "hacked" version of OpenGLView to be able to add canvas with proper z-index. [html5-dom demo](http://blog.zame-dev.org/pub/particles/html5-dom/).

However GL renderer is available **only** for html with -Ddom.

For all other targets use drawTiles renderer:

  - html5 in canvas mode - still pretty fast, doesn't support color effects. Can render incorrectly due to bug in openfl, please apply [this patch](https://github.com/openfl/openfl/pull/434) if you encounter it. [html5-canvas demo](http://blog.zame-dev.org/pub/particles/html5-canvas/).
  - native - fast, support color effects, hovewer in some cases GL renderer looks better.
  - flash - slow, can be buggy (due to drawTiles implementation in openfl). [flash demo](http://blog.zame-dev.org/pub/particles/flash.swf).

## How to use

Open terminal, go to some folder (if you want to), than:

```
git clone git@github.com:restorer/zame-haxe-particles.git
haxelib dev zame-particles ./zame-haxe-particles
```

This library depends on zame-miscutils. If you don't have then:

```
git clone git@github.com:restorer/zame-haxe-miscutils.git
haxelib dev zame-miscutils ./zame-haxe-miscutils
```

## Roadmap for future

[ ] Support for .json output format
[ ] Support for .lap and .pex output formats
[ ] Create component for luxe engine
[ ] Support for embedded textures
[ ] Support for snow
[ ] Support lime directly, without openfl
[ ] Support for HaxeFlixel and / or HaxePunk?
