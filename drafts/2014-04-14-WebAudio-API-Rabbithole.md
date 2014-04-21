---
layout: post
title: Looking Down the Web Audio API Rabbithole
---

Looking Down the Web Audio API Rabbithole
-----------------------------------------

The past year I've been playing on and off with the Web Audio API.  Last spring as I was finishing my computer science degree from Rutgers I used the Web Audio API quite a bit to create a GarageBand inspired online sequencer that I was making for a senior project.  This post won't go into that, instead it will talk about my more recent exploration using AudioNodes to change a signal as it passes through a routing graph.  

Oh, and here's a big fat DISCLAIMER: I don't know much at all about Digital Signal Processing, or working with audio in general.  I've been playing drums for about 10 years and guitar for less than that, but that hasn't taught me much about working with audio signals.  In playing with the Web Audio API I've had to concurrently learn about the actual API calls as well as the signal processing behind it.  With that disclaimer out of the way, let's move on to a quick overview of the Web Audio API.

What is the Web Audio API?
--------------------------

The Web Audio API-- whose official specification is [here](https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html)-- is a new HTML5 API that allows you to process and synthesize audio in Javascript.  I know, you're probably thinking "But Scott, Javascript is an interpreted language.  That audio manipulation must be so slow!".  Ah, but that is the beauty of the Web Audio API; the API calls are in Javascript, but the underlying manipulation is implemented natively in optimized Assembly, C, or C++ code.  There is also support for doing audio manipulation directly in Javascript, but the primary draw is the underlying native implementation.

On to the Code!
---------------

Ok, 