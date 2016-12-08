---
layout: post
title: "How To Flush DNS Cache on Mac OS X 10.7 and 10.8"
tags: [flush, dns, 10.7, 10.8, mac os x, mac, os x]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-08-18 10:20:00 -8
---

If you are having problems connecting to the internet on your Mac, you may need to flush your DNS cache. On Mac OS X 10.7 and 10.8, you can simply open Terminal by using Spotlight (CMD+Space) or by going to Applications > Utilities > Terminal. Copy and paste the command below to flush your DNS Cache:

{% highlight bash %}
sudo killall -HUP mDNSResponder 
{% endhighlight %}

Type in your Administrative password and the command should fix your internet problems! Hopefully your internet connection problems are gone now and you can enjoy the internet! If you have any questions, please feel free to leave a comment below!
