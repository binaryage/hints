---
layout: post-hints
title: "2D Dock in Mac OS X"
tags: [mac, macosx, lion, dock, finder]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-02-27 09:07:00 -8
---

Most people are accustomed to the traditional Mac OS dock which does in fact have a 3D look to it. However, there is an unknown secret: the operating system actually comes with a hidden 2D dock which, in my opinion, is cleaner looking and more minimalist. This hack works for Mac OS X 10.5 through the current 10.7. <br></br>
<img alt="" src="http://www.macosxhints.com/images/105docksmall.png" title="2D dock" class="alignnone" width="380" height="32" /><br></br>

To change your dock to the 2D version at all times, simply follow these instructions:

Step 1) Open up Terminal (if you don't know what or where that is, press the spotlight icon in the top right hand corner of your screen and type in "Terminal" or press CMD-Spacebar to quickly access Spotlight.

Step 2) Type the following command (or copy and paste if you are feeling lazy)

<code>defaults write com.apple.dock no-glass -boolean YES</code>

Step 3) Press Enter to run the command.

Step 4) Type 

<code>killall Dock</code>

Step 5) Press Enter to run the command.

Now your dock should reload and it should be the 2D version. 

[<a href="http://hints.macworld.com/article.php?story=2007101815375480">Link</a>]
