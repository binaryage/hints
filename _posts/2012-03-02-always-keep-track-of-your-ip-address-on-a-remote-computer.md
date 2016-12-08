---
layout: post-hints
title: "Always Keep Track of your IP Address on a Remote Computer using Dropbox"
tags: [ipaddress, remote, mac, terminal, dropbox]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-03-02 16:17:00 -8
---

If you want to remotely access your computer using SSH, FTP, SMB, AFP, etc, you will most likely need your IP address unless you have Dynamic DNS set up. To combat this issue of an always changing IP address, follow the tips below to use Dropbox to always have access to your home computer's IP address. Note: this guide is for Mac/Unix only as it involves using a Cron job.

Step 1) Download Dropbox if you haven't already installed it. (Use this link <a href="http://db.tt/5QiebOV2">here</a> and you will receive 250MB of extra space!)

Step 2) After installing and setting up Dropbox, take note of the directory that your Dropbox folder is located in. (Usually, the Dropbox folder is in your home directory)

Step 3) Now we are going to create a cron job. If you have never used a cron job before, <a href="http://en.wikipedia.org/wiki/Cron">here</a> is a Wikipedia entry on what it is used for.

Step 4) Open your favorite text editor and create a new file called "cron.txt" From the examples on the Wikipedia article, we will need to fill in the five fields the distinguish the timing of the cron job and the last field which contains the specified command that runs at that time. 

Step 5) The first column of the cron job is the minutes column taking in a value from 00-59 and represents the actual minute that you want the job to run at. For example, 00 means the job will run on the hour, every hour; 04 means that it runs every hour in the fourth minute such as 1:04, 2:04, etc. You can enter multiple values separated by a comma or a range of numbers by using a hyphen. Besides inputting in a specific number, you can also enter * to signifiy a wild card which in this case would run every minute.

Step 6) Fill in the last four columns that are used to set up the frequency of the job. After the minutes column, the rest of the columns are: hour (00-23), day of the month (01-31), month of the year (01-12), day of the week (0-7) zero and sever both signify Sunday. For my file, I used <code>0,30 * * * *</code> which means my command will run on the hour and on the half hour, every hour of every day for the whole year.

Step 7) The last column of the cron job is the command. This can be whatever command you want, but for the purposes of this article, I will provide the code that I used to find my IP address.

<code>curl -s http://checkip.dyndns.org | sed 's/[a-zA-Z/<> :]//g' > ~/Dropbox/ip.txt</code>

In my example above, I am saving a file called "ip.txt" in the root of my Dropbox folder that is located in my home directory.

Step 8) Finally, note the directory of where you saved this file. Open Terminal, located in Applications > Utilities > Terminal, or you can use Spotlight to find it. Using the command "cd" (change directory) navigate to the directory that you saved the "cron.txt" file to. 

Step 9) Still in Terminal, run the command:
<code>crontab cron.txt</code>

Step 10) To check to make sure that this worked, run the command <code>crontab -l</code> and your file should show its contents. 

Step 11) Now, you must wait for the specified time to come, but when it does, there will be a file called "ip.txt" in your Dropbox folder that will automatically sync with the Internet that you can view from anywhere!

Step 12) Now you can always know your home IP address. Happy SSH'ing!

Here is my file that you can use as a sample. <a href="/downloads/cron.txt">Download</a> (Save link as)

Post in the comments below if you have any questions about this technique.
