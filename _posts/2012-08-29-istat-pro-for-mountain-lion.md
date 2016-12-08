---
layout: post
title: "iStat Pro for Mountain Lion"
tags: [istat, istat pro, mountain lion, download]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-08-29 01:29:00 -8
---

<img class="clear blog-image-full-border" src="/images/istat1.png" title="iStat Pro">

iStat Pro, the popular widget to monitor your computer by iSlayer has been deprecated by the company. They stated in a tweet that they will not be continuing development and support for Mountain Lion. Lucky for us, there is a simple fix that you can execute yourself on Mountain Lion to make the great extension work again! All you have to do is add a space to two different lines in some code. Ready to dive in?

Step 1) Right off the bat, we can download the widget from <a href="http://islayer.com/apps/istatpro/download/">here.</a>

Step 2) Extract the widget and then double click on it to install. It will show up on your dashboard and you can view it as normal. However, take a close look at the process tab. You may need to enable it by clicking on the "i" and then going to the "Sections" tab and turning on "Processes." You will notice that the processes tab is broken. Want to fix it? Keep reading on!

<img class="clear blog-image-full-border" src="/images/istat2.png" title="iStat Pro">

Step 3) In order to fix this small bug, we're going to have to open up some code. Grab your favorite text editor (I personally use TextMate) and navigate to the <code>~/Library/Widgets</code> folder where you will find the iStat widget.

Step 4) Right click on the widget and press "Show Package Contents"

Step 5) Find the two files, Tall.js and Wide.js. In Tall.js, we will navigate to lines 548 and 550. Find the section that looks exactly like what is shown below:

{% highlight javascript %}
if(p.v("processes_sort_mode") == 'cpu')
	widget.system('ps -arcwwwxo "pid %cpu command" | egrep "PID|$1" | grep -v grep | ' + exclude + ' head -7 | tail -6 | awk \'{print "<pid>"$1"</pid><cpu>"$2"</cpu><name>"$3,$4,$5"</name></item>"}\'', function(data){ _self.updateProcessesOut(data);});
else
	widget.system('ps -amcwwwxo "pid rss command"  | egrep "PID|$1" | grep -v grep | ' + exclude + ' head -7 | tail -6 | awk \'{print "<pid>"$1"</pid><cpu>"$2"</cpu><name>"$3,$4,$5"</name></item>"}\'', function(data){ _self.updateProcessesOut(data);});
}
{% endhighlight %}

Notice the two parts that read: 
<code>
  egrep "PID|$1"
</code>

Simply add a space between the pipe and the dollar sign as follows:
<code>
  egrep "PID| $1"
</code>

That's it! Make those two changes and then save the file. For the Wide.js, the same two lines can be found at 609 and 611 (make the same changes).

Step 6) After you have successfully made the changes to the code, open up a Terminal window (Applications > Utilities > Terminal) and type in:
<code>
  killall Dock
</code>

Now you should have a functioning iStat Pro installation that works on Mountain Lion! Great!

<img class="clear blog-image-full-border" src="/images/istat3.png" title="iStat Pro">

If you have any questions about the process or you are stuck on a particular step, leave a comment below and I will get back to you as soon as I can!
