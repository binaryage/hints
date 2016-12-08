---
layout: post
title: "How to Remove .DS_Store File from a Git Repo on Mac OS X"
tags: [git, github, svn, mac, .DS_Store, bitbucket, repos, os x, osx, unix]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-04-27 23:50:00 -8
---

Whether you are a new or experienced git user, at one point in your git career using a Mac, you stumbled upon the fabled .DS_Store file. This little file is a "Desktop Services Store" that contains attributes of a folder and is created every single time a folder is navigated to. Man, that's a lot of .DS_Store files. For the average Mac user, these files are never seen because they are hidden. However, any git user will know that annoying feeling when they notice that a pesky .DS_Store file has crept its way into their repo. Here is a tutorial on how to solve this problem, once and for all.

A sample .DS_Store file for those who may not know what they look like:
<img class="clear blog-image-full-border" src="/images/dsstore.png" title=".DS_Store">

Step 1) If you would like to see .DS_Store files, download and use [TotalFinder][TotalFinder] which has a very easy method for viewing hidden files. There are other methods involving Terminal, but TotalFinder makes it easy (it's a preference and even has a keyboard shortcut!).

Step 2) Navigate to your repo using Terminal (Applications > Utilities > Terminal). This first command will remove any and all .DS_Store files from your repo. Simply enter:
    
    find . -name .DS_Store -print0 | xargs -0 git rm --ignore-unmatch
    
Step 3) Now we will create a global exclusion list (you can skip this step if you already have one set up). To do this, enter the command:    

    git config --global core.excludesfile ~/.gitignore
    
Step 4) Now, we must add the pesky .DS_Store file to our newly created global exclusion list, named .gitignore (assuming you don't want any .DS_Store files in any repos that you may own). To do this, simply use this command:

    echo .DS_Store >> ~/.gitignore
    
This will add an entry to your .gitignore file that tells your git repo to ignore any file called .DS_Store. This is exactly what we want.

Commit these changes and push to your repo. To our surprise, all .DS_Store files have been removed! Congratulations! Now our repos are clean, free from clutter, and more professional.

Also, if you often navigate through Finder with hidden files on, I would recommend the tool called [Asepsis][Asepsis] a product of BinaryAge. Asepsis redirects the creation of .DS_Store files to a special folder that you seldom interact with. All the properties of folders are still retained, they are just placed in a different, well-hidden directory. 

If you have any questions about this process or would like me to explain something more in depth, please feel free to leave a comment below!

[TotalFinder]: http://totalfinder.binaryage.com
[Asepsis]: http://asepsis.binaryage.com
