---
layout: post-hints
title: "How To Clear Out Launchpad and Add the Apps How You Want"
tags: [launchpad, ios, mac, mac os x]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-06-27 00:11:00 -8
---

Launchpad is a feature added to Mac OS X that emulates the home screens on iOS. The basic idea behind it is that you have one central location to find all of your apps. However, as most users have noticed, this feature, loved on iOS, is not as useful on OS X. The simple reason is that not every user wants every app on their computer showing up in Launchpad. Luckily for us, there is a simple trick that will allow us to organize and store what WE want in Launchpad. This is more desirable; follow the steps below in order to accomplish just this:

Step 1) Open up Terminal by going to Applications > Utilities > Terminal.

Step 2) Type in the following command: 
    sqlite3 ~/Library/Application\ Support/Dock/*.db "DELETE from apps; DELETE from groups WHERE title<>''; DELETE from items WHERE rowid>2;"; Killall Dock

This command essentially erases the entire database for Launchpad. Yay, now Launchpad is...empty? That's not useful. Read on!

Step 3) To add apps back to Launchpad, all you need to do is drag apps onto the Launchpad dock icon. Yep, it's that simple!

Step 4) If for some reason you would like to go back to the old Launchpad with an icon for every single app on your Mac, then enter the command below which will rebuild the database:
    rm ~/Library/Application\ Support/Dock/*.db; killall Dock
    
If you have any questions about the code listed above, please leave a comment below! 
