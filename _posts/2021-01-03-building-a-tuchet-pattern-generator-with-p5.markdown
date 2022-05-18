---
title: Truchet patterns
date: 2021-01-03
description: Building a Tuchet pattern generator with p5.js.
tags:
  - p5.js
  - generative
  - code
image: images/truchet-hero.png
---

From this Twitter account [@truchet_nested](https://twitter.com/truchet_nested) leading to [this post](https://christophercarlson.com/portfolio/multi-scale-truchet-patterns/) by Christopher Carlson, I stumbled into what I think is one of the more beautiful generative code projects I've seen. There is a certain feel from these patterns that's not too organic but also not too structured, hitting a sweet spot in between. Alien hieroglyphs, or hand made electronic circuits.

## It's just tiles
<!-- <div> -->
  <!-- <img src="images/truchet-tile-01.png" alt="Truchet tile example" title="A Truchet tile constructed from bezier curves." />
  <img src="images/truchet-tile-02.png" alt="Truchet tile example" title="A Truchet tile constructed from bezier curves." />
  <img src="images/truchet-tile-03.png" alt="Truchet tile example" title="A Truchet tile constructed from bezier curves." />
  <img src="images/truchet-tile-04.png" alt="Truchet tile example" title="A Truchet tile constructed from bezier curves." />
  <img src="images/truchet-tile-05.png" alt="Truchet tile example" title="A Truchet tile constructed from bezier curves." /> -->
<!-- </div> -->
<!-- {{ .Scratch.Set "img01" "images/truchet-tile-01.png"}} -->
{{ partial "image-row.html" . }}
  <!-- ![A Truchet tile constructed from bezier curves.](images/truchet-tile-01.png) -->

The patterns are generated from a series of tiles described by Carlson as 'winged', the wings extend past the body of the tile to overlap their neighbours by 1/3 of their own dimension. The mixture of transparency, and foreground & background colours allow the patterns to be build up seamlessly, each neighbour terminating, or extending the strokes to form emerging patterns of contiguous colour.
## Implementing a pattern generator
As a starting point I hacked together a basic p5.js script to produce patterns at a single scale. Primarily this was to keep things simple and to build an understanding of how the tiles interact, and also the p5.js library.

Using p5.js I constructed the library of sixteen tiles. The tile base containing elements common to all tiles was built up using `rect` and `ellipse` primatives. Each tile variation was then created with `arc` or `line` objects. 

With this basic generator in place it gives me a great starting point to iterate into a multi-scale version of the code.

## Multi-scale
The next step is to implement the multi-scale side of things. Introducing more tiles at half size adds another, more interesting level of visual complexity to the output.
