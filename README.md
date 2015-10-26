# perspective-transform

! This is a hacked apart version to be used in Adobe Illustrator's scripting engine !
Adobe Illustrator's ECMA compatability is far from the best, so the vanilla script didn't work.
I pulled out some of the nicer elements making the PerspT object global, etc etc.

It works for the small project I am working on, somewhat inspired by https://somethingaboutmaps.wordpress.com/2015/09/28/a-matter-of-perspective/

Full credit to original author https://github.com/jlouthan/perspective-transform

A small JavaScript library for creating and applying perspective transforms. A perspective transform can easily be used to map one 2D quadrilateral to another, given the corner coordinates for the source and destination quadrilaterals. [Here](http://xenia.media.mit.edu/~cwren/interpolator/) is a useful resource for learning more about perspective transforms and the math behind them. [And here](http://uncorkedstudios.com/blog/perspective-transforms-in-javascript) is a blog post I wrote about the motivation for creating this library and details of some of its applications.

## Features
- Create functions to map points from one arbitrary quadrilateral to another and vice versa with the inverse
- Access the homographic matrix and its inverse (useful for transforming elements with CSS3)
- No external dependencies

## Basic Usage

### Illustrator

```js
//@include('perspective-transform');

var srcCorners = [158, 64, 494, 69, 495, 404, 158, 404];
var dstCorners = [100, 500, 152, 564, 148, 604, 100, 560];
var perspT = PerspT(srcCorners, dstCorners);
var srcPt = [250, 120];
var dstPt = perspT.transform(srcPt[0], srcPt[1]);
// [117.27521125839255, 530.9202410878403]
```
