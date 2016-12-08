---
layout: post
title: "Change the Font Size in List View of Stacks in your Dock"
tags: [font, size, list, view, stacks, dock, hack, tweak]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-03-22 01:45:00 -8
---

On Mac OS X, you can easily drag folders into your dock for easy access. There are 4 default views, Fan, List, Grid, and Automatic. However, there is also a hidden 5th view that Apple has not revealed to the public, but has been found as a plist hack for Finder.

Here is the code to enter into Terminal:
<code>defaults write com.apple.dock use-new-list-stack -bool YES && killall Dock</code>

This enables a "new list view" for folders in the dock. The cool thing about this feature is that it is customizable. You can manipulate the icons as well as use Quick Look from inside the list view by pressing the spacebar key while holding your mouse over the icon.

Here are some screenshots of the hidden view:
<img class="clear blog-image-border" src="/images/dock_size_1.png" title="Dock List View">

After pressing CMD + to make the text bigger:
<img class="clear blog-image-border" src="/images/dock_size_2.png" title="Dock List View">

And after pressing CMD + several times in order to max out the font size:
<img class="clear blog-image-border" src="/images/dock_size_3.png" title="Dock List View">

To undo this feature and restore the normal list view, simply enter this command into Terminal.
<code>defaults write com.apple.dock use-new-list-stack -bool NO && killall Dock</code>

If you have any questions, please post them in the comments below!
