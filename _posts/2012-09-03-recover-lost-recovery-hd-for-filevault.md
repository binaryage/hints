---
layout: post
title: "Recover lost Recovery HD for FileVault - the easy way"
tags: [recovery hd, filevault, diskutil, lion, mountain lion, bootcamp]
author_name: Antonin Hildebrand
author_url: http://hildebrand.cz
google_plus: 101180624276428786239
---

Today I wanted to install FileVault2 on my secondary MacBook. Unfortunately FileVault reported:<br>
**FileVault can’t be turned on for the disk ...**

I did a quick googling and realized that the problem is missing "Recovery HD" partition on my disk. Since Lion, OS X installers create Recovery HD partition immediatelly after the main system partition. It is a small (650MB) bootable partition that can be used for various system troubleshooting scenarios (for example when you encript your disk with FileVault and forget the login password).

### How to recreate lost recovery partition easily?

I found several articles [about](http://musings.silvertooth.us/2012/03/restoring-a-lost-recovery-partition-in-lion/) [the](http://www.dmitry-dulepov.com/2011/09/how-to-create-mac-os-x-lion-recovery.html) [topic](https://plus.google.com/108724035107725322855/posts/Y33cF3cJR9o), but all methods seemed to be pretty complex and/or time consuming. There must be an easier way! What about fooling OS X installer into creating Recovery HD partition for us?

Here is an easy solution which took me less than 10 minutes. Let's say you want to restore Recovery HD partition for your system partition called "OSX" running Lion.

#### Prerequisities:

  1. installation disk for Lion (or "Install Mac OS X Lion" app, downloaded from the App Store)
  2. at least 8 GB of free space on your "OSX" partition (needed for a clean OS X installation)
  3. your "OSX" partition is formatted with resizeable filesystem (Journaled HFS+ is fine)

#### Steps:

  1. use `Disk Utility.app` to:
    1. shrink OSX partion by 8 GB (or more)
    2. insert new OSX 2 partition immediately after OSX (I used the small "+" button under Partition Layout)
    3. make sure both partitions have format: Journaled HFS+ (JHFS+)

  2. start installing Lion on newly created OSX 2 partition
      1. let computer reboot first time to finish copying
      2. during second reboot hold Option key and boot into old OSX (we don't need to finish OSX 2 installation)

  3. merge OSX 2 into OSX via command-line:

```
~ ➔ diskutil list
/dev/disk0
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *251.0 GB   disk0
   1:                        EFI                         209.7 MB   disk0s1
   2:                  Apple_HFS OSX                     175.0 GB   disk0s2
   3:                  Apple_HFS OSX 2                   75.0 GB    disk0s3
   4:                 Apple_Boot Recovery HD             650.0 MB   disk0s4
~ ➔ diskutil mergePartitions JHFS+ not disk0s2 disk0s3
Merging partitions into a new partition
     Start partition: disk0s2 OSX
     Finish partition: disk0s3 OSX 2
Started partitioning on disk0
Merging partitions
Waiting for the disks to reappear
Growing disk
Finished partitioning on disk0
/dev/disk0
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *251.0 GB   disk0
   1:                        EFI                         209.7 MB   disk0s1
   2:                  Apple_HFS OSX                     250.1 GB   disk0s2
   3:                 Apple_Boot Recovery HD             650.0 MB   disk0s4
```



In step 3 you have to use `diskutil list` to read identifiers of OSX and OSX 2 partitions. If you did all right, **you must see OSX, OSX 2 and Recovery HD in this exact order** somewhere in the list. By executing`diskutil mergePartitions` you merge OSX 2 into OSX (and lose content of the newly created partition OSX 2). You have to end up with OSX immediatelly followed by Recovery HD.

#### Notes

1. Forget using `Disk Utility.app` in step 3. You cannot delete OSX 2 via Disk Utility and resize OSX to eat the gap. Disk Utility is smart enough and deteling partition deletes also hidden Recovery HD partition which immediatelly follows.

2. The same method should work with Mountain Lion (not tested)

3. The same method should work in more complex scenarios. You get the idea.

#### Disclaimer

I'm not responsible for anything you do to your data. Always do proper backups!

Hope this helped.
