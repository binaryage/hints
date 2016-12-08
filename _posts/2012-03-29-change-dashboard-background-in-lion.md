---
layout: post-hints
title: "Change Dashboard Background in Lion"
tags: [dashboard, lion, background]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-03-29 00:22:00 -8
---

In Mac OS X Lion, Dashboard has become its own space as part of the new feature, Mission Control. However, the method to change the background is missing for Dashboard, so here is a tutorial on how to accomplish this task.

Step 1) Open Applescript Editor under Applications > Utilities.

Step 2) Copy and paste this code into the app:

    delay 5
    tell application "Finder"
      set desktop picture to POSIX file "/Users/YourUsernameHere/PathToFile.png"
    end tell

Step 3) The reason that there is a "delay 5" at the beginning of the file is so that you can quickly switch to the Dashboard space.

Step 4) After you have edited your Applescript in the editor, press the run button or press "CMD + R" to run the applescript. Quickly switch from your current space to the Dashboard space within the time limit you have set.

Step 5) If all goes well, there should be zero errors when executing the applescript and your background for the Dashboard space should now be changed!

If you have any questions, please feel free to contact me or leave your question in the comments box below. Cheers!
