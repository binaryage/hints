---
layout: post-hints
title: "How To Clear iMessage History on Mac OS X"
tags: [imessage, history, mac os x, macosx, lion, download, beta]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-04-17 01:48:00 -8
---

This is a follow-up to my post about <a href="/download-imessage-beta-for-mac-os-x-lion/">installing iMessage Beta.</a>

If for some reason iMessage is acting strangely, one of the things you can try to do to alleviate this problem is to clear out your chat history. Large logs can cause iMessage to slow to a crawl. Here are the steps to fix this problem:

Step 1) Quit iMessage on your Mac.

Step 2) Open Finder and press CMD+Shift+G or by navigating to Go > Go To Folder...

Step 3) In the dialog, type in <code>~/Library/Messages/</code>

Step 4) There should be at least three files as shown in the screenshot below. We are going to delete the files <code>chat.db</code> <code>chat.db-shm</code> and <code>chat.db-wal</code>

<img class="clear blog-image-full-border" src="/images/imessage_logs.png" title="iMessage">

Step 5) After you have successfully deleted those three files, you can now open iMessage again and it will be similar to a brand new installation! Now you do not have to worry about long conversations slowing iMessage down. 

There is also an alternative way to accomplish this by using Terminal under Applications > Utilities > Terminal. Type in the command:
<code>rm -r ~/Library/Messages/chat.*</code>
This will effectively do the same thing. 

If you have any questions about the process, please post in the comments below!
