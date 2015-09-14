---
layout: post
title: "Fix rpl_malloc when cross compilation fails"
description: ""
category: Fix
tags: [rpl_malloc, cross-compilation, fbdump]
---
{% include JB/setup %}
 
I needed fbdump on my embedded device today, but while cross compiling it, I fall into an obscure rpl_malloc error. 
It's was easy to find a fix, but I think I should shared it here too.

So basically you just have to enter this command BEFORE the configure script:

`$ export ac_cv_func_malloc_0_nonnull=yes`

Now the compilation should works fine.

[Source](https://groups.google.com/forum/#!topic/ikarus-users/_R0QHqwyYz8)