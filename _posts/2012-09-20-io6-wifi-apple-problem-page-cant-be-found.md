---
layout: hints-post
title: "iOS 6 upgrade problem: wifi redirects to apple.com"
tags: [iOS 6, apple, wifi, upgrade, problem, update, connectivity]
author_name: Antonin Hildebrand
author_url: http://hildebrand.cz
google_plus: 101180624276428786239
---

I have just update to iOS 6 and experienced a problem with wifi connectivity. Everytime I wanted to connect to my home wifi it ended up opening "Log In" screen with broken page at apple.com saying "hmm, the page you're looking for can't be found.".

I googled for solutions and found several threads:

  * [https://discussions.apple.com/thread/4311667](https://discussions.apple.com/thread/4311667)
  * [https://discussions.apple.com/message/19629512](https://discussions.apple.com/message/19629512)
  * [https://discussions.apple.com/message/19625125](https://discussions.apple.com/message/19625125)
  * ...

There are some suggestions which worked to some users but no widely confirmed solution.

My router is a TimeMachine box (Airport Extreme). Here are the steps which worked for me:

  1. Used `AirPort Utily` on my Mac to restart the router
  2. in iOS 6: Settings -> General -> Reset -> Reset Network Settings  
  3. in iOS 6: Settings -> General -> Reset -> Reset All Settings
  
Then wifi started to operate properly. 

Also I noticed I lost an option for personal hotspot in my Settings menu, but that may be only effect of losing my settings. It can be probably re-enabled somewhere deeper in the Networking Settings.