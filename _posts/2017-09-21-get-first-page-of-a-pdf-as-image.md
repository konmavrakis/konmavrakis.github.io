---
title: Get first page of a pdf as an image
layout: post
date: 2017-09-21 13:08
headerImage: false
tag:
- bash
- pdf
- image
- ghostscript
star: true
category: blog
author: konmavrakis
description: Use ghostscript to get convert first page of a pdf to an image
---
Recenlty I wanted to get every first page of a PDF to create a grid with all the images. 

In order to do so, I created a script in order to automatically convert the first page only of a PDF to an image.

You'll need to install [Ghostscript](https://www.ghostscript.com/), modify the following script and you'll be ready to go!

```bash
#!/bin/bash
for i in {32..54} #in my case the PDFs were named "32.pdf, 33.pdf"
do
   gs -dNOPAUSE -dBATCH -sDEVICE=jpeg -dFirstPage=1 -dLastPage=1 -sOutputFile="$i.jpeg" $i.pdf
done
```
You must set ``-dFirstPage`` and ``-dLastPage`` to the page you want to retrieve. In my case I wanted the first image so I set ``-dFirstPage`` and ``-dLastPage`` to ``1``.
If you want png output change ``-sDevice`` to ``png16m`` and change the file type of ``-sOutputFile`` to ``"name.png"``
