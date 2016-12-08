---
layout: post
title: "How to Install Python 3.2.3 on Mac OS X"
tags: [python, programming, mac os x, software, development]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-06-03 18:47:00 -8
---

By default, your Mac comes installed with Python 2.7, no installation necessary! However, if you want some of the new features of Python such as "print" being a function now instead of a standalone command, then you are going to want to install Python 3.2.3. Follow the steps below to get started:

Step 1) Go <a href="http://www.python.org/download/releases/3.2.3/">here</a> to learn all about the new release of Python. Then, find the downloads section to download the latest release for Mac. (Or just click <a href="http://www.python.org/ftp/python/3.2.3/python-3.2.3-macosx10.6.dmg">here.</a>)

Step 2) Double click on the installer and follow the instructions for installing Python 3.2.3 on your Mac.

Step 3) Now, when you open up terminal and type in "python", version 2.7 still appears. To open the version you just installed, type "python3" and this will open the latest version of Python 3.x.x.

Step 4) To streamline this process even further, you can add an alias for "python3" and call it "python" so that no matter what, Python 3.x.x will always open whether you type "python" or "python3." To do this, open up Terminal.

Step 5) At the command prompt, if you are comfortable with VIM, type:
    vim ~/.bash_profile
If not, type:
    open ~/.bash_profile
And this will open up the file in your default text editor. Add the following line to the file and save:
    alias python="python3"
    
Step 6) That's it! Now when you type "python" into Terminal, Python 3.x.x will open by default! 

Happy programming!
