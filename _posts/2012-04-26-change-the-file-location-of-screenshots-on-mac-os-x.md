---
layout: hints-post
title: "Change the File Location of Screenshots on Mac OS X"
tags: [images, screenshots, mac os x, macosx, file, finder, defaults, terminal]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-04-26 09:23:00 -8
---

On Mac OS X, you can easily take screenshots of your desktop by pressing shortcut keys on your keyboard. (More on that <a href="{{site.url}}/how-to-measure-screen-elements-in-pixels/">here.</a>) However, all of your screenshots will go to your desktop by default. To change this, open up Terminal by going to Applications > Utilities > Terminal, or by simply using Spotlight to search for Terminal, and copy and paste the following commands:

    defaults write com.apple.screencapture location /path/to/screenshots
    
A common place to switch the screenshot location to might look something like this:

    defaults write com.apple.screencapture location ~/Pictures/Screenshots
    
This will place the screenshots into a folder called Screenshots in your Pictures folder in your Home folder. Be sure to create the folder structure before you actually try and take a screenshot.

To apply these changes, again in Terminal, type:

    killall SystemUIServer
    
And, to change it back to the default desktop location, simply type in:

    defaults write com.apple.screencapture location ~/Desktop/

UPDATE: New post on how to change the file type of your screenshots <a href="{{site.url}}/change-file-type-of-screenshots-on-os-x/">here!</a>

That's it! Hope this hint has helpful, post any questions or concerns in the comments below.