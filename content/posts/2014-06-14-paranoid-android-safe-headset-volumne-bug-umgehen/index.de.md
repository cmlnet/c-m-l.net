---
title: 'Paranoid Android: Safe Headset Volume Bug umgehen'
author: Christian Humm
date: 2014-06-14T08:03:58+00:00
url: /2014/06/14/paranoid-android-safe-headset-volumne-bug-umgehen/
categories:
  - Android
tags:
  - Android
  - Bug
  - Paranoid Android
  - Safe Headset Volumne
toc: false
cover: cover.jpg
vgwort: f281f8ed8f5e41c6ac429facc8d151e1
summary: "Momentan läuft auf meinem Smartphone das Custom Rom Paranoid Android. Eigentlich ein recht stabiles Rom, mit einigen netten Features wie Hover oder Peek und einer durchdachten Benutzeroberfläche. In der aktuellen Version 4.4 RC 1 hat sich allerdings ein fieser Bug eingeschlichen: Sobald man per Kopfhörer Musik oder ähnliches hört und die Lautstärke über das sog. &#8220;Safe Headset Volume&#8221; &#8211; was etwa der Hälfte der möglichen Lautstärke entspricht &#8211; angehoben wird, startet Android neu."
---
Momentan läuft auf meinem Smartphone das Custom Rom [Paranoid Android][1]. Eigentlich ein recht stabiles Rom, mit einigen netten Features wie Hover oder Peek und einer durchdachten Benutzeroberfläche. In der aktuellen Version 4.4 RC 1 hat sich allerdings ein fieser Bug eingeschlichen: Sobald man per Kopfhörer Musik oder ähnliches hört und die Lautstärke über das sog. &#8220;Safe Headset Volume&#8221; &#8211; was etwa der Hälfte der möglichen Lautstärke entspricht &#8211; angehoben wird, startet Android neu.

Wenn man die Lautstärke zum ersten Mal über diese Lautsstärkegrenze anhebt und dabei einen Kopfhörer eingesteckt hat, blendet Android eine Warnung ein. Bestätigt man diese mit &#8220;OK&#8221;, dann kann man die Lautstärke weiter anheben. Der Vorgang muss unter normalen Androidversionen nach jedem Neustart wiederholt werden &#8211; was ziemlich nervig sein kann. Paranoid Android bietet deshalb nach der Warnung die Möglichkeit diese dauerhaft auszuschalten und genau an dieser Stelle kommt es zum &#8220;Soft Reboot&#8221;.

{{< figure src="images/safe_headset_volumne_warning.png" title="Screenshot: Safe Headset Volume Warning unter Android" >}}

Zwar ist davon auszugehen, dass der [Bug][2] in der nächsten Version behoben ist und prinzipiell nicht viele Nutzer betrifft, da die meisten die Warnung wahrscheinlich schon in einer früheren Version ausgestellt haben. Wer aber von dem Bug betroffen ist und nicht bis zum nächsten Build warten will, der kann ihn relativ einfach beheben:

  1. Zuerst muss man einen Terminalemulator auf dem Smartphone installieren. Ich empfehle die Open-Source App [Terminal Emulator][3]. (Alternativ lässt sich das Ganze auch über die Android Debug Bridge (ADB) bewerkstelligen, dass Vorgehen werde ich hier aber nicht beschreiben.)
  2. Ist dasgeschehen startet man den Terminal Emulator und gibt im Commandprompt folgendes ein: `su`
  Im aufpoppenden Dialog gibt man der App Rootzugriff, damit der folgende Befehl benutzt werden kann.
  3. Nun gibt man folgenden Befehl ein:`settings put system safe_headset_volume 1`
  Damit wird die Lautstärkewarnung permanent abgeschaltet. Ersetzt man die 1 durch eine 2, dann wird die Warnung wieder eingeschaltet.

  {{< figure src="images/Screenshot_2014-06-13-23-40-01.png" title="Terminal Emulator mit den Befehlen zum Ausschalten der Lautstärkewarnung" >}}

 [1]: https://plus.google.com/+ParanoidAndroidCorner/
 [2]: https://paranoidandroid.atlassian.net/browse/AOSPA-527 "Bug im Tracker von Paranoid Android"
 [3]: https://f-droid.org/repository/browse/?fdfilter=terminal&fdid=jackpal.androidterm "Terminal Emulator im F-Droid Katalog"

{{< vgwort "f281f8ed8f5e41c6ac429facc8d151e1" >}}