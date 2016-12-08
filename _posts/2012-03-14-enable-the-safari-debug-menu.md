---
layout: post-hints
title: "Enable the Safari Debug Menu"
tags: [safari, debug, menu, app, terminal]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-03-14 23:31:00 -8
---

If you would like to enable hidden features in Safari on your Mac, follow the steps below to enable the debug menu. Extra features you can unlock include: spoofing your user agent, using the Web Inspector, and disabling things such as Javascript.

Step 1) Open Terminal under Applications > Utilities > Terminal, or by pressing CMD + Spacebar and typing in Terminal.

Step 2) Copy and paste this line of code into Terminal to enable the debug menu.

<code>defaults write com.apple.Safari IncludeDebugMenu 1</code>

That's it! You now have the debug menu enabled! If at any time you want to revert back to Safari without the debug mode on, simply use the same code and change the one at the very end to a zero.

Questions? Leave them in the comments below!
