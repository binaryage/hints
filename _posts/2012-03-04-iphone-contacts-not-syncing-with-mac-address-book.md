---
layout: post-hints
title: "iPhone Contacts not syncing with Mac Address Book"
tags: [iphone, contacts, mac, addressbook, icloud]
author_name: Mark Miyashita
author_url: http://markmiyashita.com
google_plus: 101180624276428786239
date: 2012-03-04 03:45:00 -8
---

If you are still using the Mac Address Book without iCloud to sync your contacts when you plug in your iPhone, you may have run into the problem that they do not always sync when you plug in your phone. Follow these steps below to fix this simple problem.

Step 1) Make sure that your iPhone is not syncing contacts with Gmail, Microsoft Exchange, or Yahoo!.

Step 2) Plug iPhone in to computer and turn off contact syncing. Unplug, and then sync again.

Step 3) Unplug your iPhone again and quit all instances of Address book, iTunes, iCal etc.. on your Mac.

Step 4) Go to ~/Library/Application Support/AddressBook and move all the contents of that folder with the exception of the Metadata folder to your desktop (in case you need to restore them).

Step 5) Open iSync from your Applications, go to Preferences, and click reset Sync History.

Step 6) Reopen Address Book.

Step 7) Connect iPhone to iTunes and set up your iPhone to sync contacts as you please.
