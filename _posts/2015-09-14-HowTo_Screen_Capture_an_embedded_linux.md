---
layout: post
title: "How to screen capture an embedded linux ?"
description: ""
category: Tuto
tags: [linux, embedded, fbdump, screen capture]
---
{% include JB/setup %}
 
Okay, last post I was explaining how I've compilled fbdump. The original reason why I wanted fbdump is to take screen capture of an IMX6 board.

I didn't know how to do it, it's pretty simple, but I find the method really interesting.

First, what is a framebuffer, better read the [wikipedia page](https://en.wikipedia.org/wiki/Framebuffer), it probably explain better than me. On linux, like pretty much everything else, the framebuffer is a file. And this file has in real time, the image displayed on the screen.

So basically we need to capture this file, and then, convert it back to an image. There is some tools that can do this, I've found two, fbshot and fbgrab. These are pretty easy to use, but they havn't worked on my board, maybe because of the color depth (32 in my case), the resulting image was totally black.

I've succeeded using fbdump. There are two steps, but it worked.
So first we capture the framebuffer :

`$ ./fbdump -fb /dev/fb2 > imageDump.data`

You can notice that I'm running on framebuffer 2, and not 0.

To convert my dump back to an image, I've used Gimp, wich is perfect for this task because you can preview the file while touching the settings, and find what's yours. Once you've find the settings, there will be the same for further image. Just export back the image to the format you want.

Et voila !

