---
layout: post-hints
title: "Change the File Type of Screenshots on OS X"
tags: [file, type, tiff, jpg, png, screenshots, os, x, osx, settings, preferences]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-04-27 00:00:00 -8
---

Yesterday, I posted a tutorial on how to change the location of screenshots taken on Mac OS X, posted <a href="/change-the-file-location-of-screenshots-on-mac-os-x/">here.</a> Today, I am going to go over how to change the file type of these screenshots. Why would you want to do this, you ask? There are several reason why this tutorial is useful. One, you may need a specific image format for a project you are working on. Second, you may also want to take higher quality, lossless screenshots (the TIFF format), or lower quality, compressed files (JPEG). Regardless, follow these steps below:

All you have to do is open up Terminal by going to Applications > Utilities > Terminal. At the prompt, type in the following command:

    defaults write com.apple.screencapture type jpg
    
and then run:

    killall SystemUIServer
    
This will change the format of your screenshots from the default "png" to "jpg"; the last parameter can be changed. Your options include jpg, png, tiff, or even pict. 

To change back to default, simply type:

    defaults write com.apple.screencapture type png

Hope this helps! Post any questions in the comments below and I will be sure to answer them.
