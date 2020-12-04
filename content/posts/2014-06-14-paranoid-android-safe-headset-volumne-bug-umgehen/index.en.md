---
title: 'Paranoid Android: How to fix the Safe Headset Volume bug'
author: Christian Humm
date: 2014-06-16T08:29:07+00:00
url: /2014/06/16/paranoid-android-fix-safe-headset-volumne-bug/
categories:
  - Android
  - IT
tags:
  - Android
  - how to
  - Paranoid Android
toc: false
cover: cover.jpg
---
At the moment I am running the Custom Rom [Paranoid Android][1] on my smart phone (a Nexus 4). Normally this is a fairly stable rom, with some nice features like Hover or Peek and a well designed UI. However, in the latest version, 4.4 RC 1, there is an annoying bug: As soon as you listen to music via a headset and try to raise the volume over the so-called &#8220;Safe Headset Volume&#8221; Android reboots.

<!--more-->

If you raise the volume the first time of the limit while having a headset attached, Android displays a warning. Pressing &#8220;okay&#8221; allows you then to rise  the volume over the limit. In Stock Android you have to do this again after each reboot of the device &#8211; which can be quiet annoying. Paranoid Android offers you the choice to disable the warning permanently and this is exactly where the &#8220;soft reboot&#8221; happens.

{{< figure src="images/safe_headset_volumne_warning.png" title="Screenshot: Safe Headset Volume Warning in Android" >}}

The [bug][2] will be fixed in the next release probably and it should not affect to many users as the most will have disabled the volume warning already in an earlier warning. All who do not want to wait for the next release and are experiencing the bug can easily fix it:

  1. First you have to install a terminal emulator on your smart phone. I recommend the open source app [Terminal Emulator][3]. (Alternativly you can apply the fix via the Android Debug Bridge (ADB), however I will not describe the steps here.)
  2. After the installation you start the terminal emulator, type in the following and press enter: `su`
  In the appearing dialog you give the app superuser rights so you can use the following command.
  3. Type in the next command and press enter: `settings put system safe_headset_volume 1`
  The command disables the safe headset volume warning permanently. Replace the 1 with a 2 and will see the warning again.

  {{< figure src="images/Screenshot_2014-06-13-23-40-01.png" title="Terminal Emulator with the commands needed to disable the safe headset volume warning" >}}

 [1]: https://plus.google.com/+ParanoidAndroidCorner/
 [2]: https://paranoidandroid.atlassian.net/browse/AOSPA-527 "Bug im Tracker von Paranoid Android"
 [3]: https://f-droid.org/repository/browse/?fdfilter=terminal&fdid=jackpal.androidterm "Terminal Emulator in the F-Droid catalog"
