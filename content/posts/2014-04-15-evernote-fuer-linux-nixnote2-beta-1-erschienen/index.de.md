---
title: 'Evernote für Linux: NixNote2 Beta 1 erschienen'
author: Christian Humm
date: 2014-04-15T19:58:44+00:00
url: /2014/04/15/evernote-fuer-linux-nixnote2-beta-1-erschienen/
categories:
  - IT
  - Linux
tags:
  - Archlinux
  - Evernote
  - Linux
  - Nevernote
  - NixNote
  - ubuntu
cover: cover.png
vgwort: a650d0fa094e4f3b8ac012f377eb8999
summary: "Ich benutze den Notizdienst Evernote eigentlich sehr gerne, lassen sich mit ihm doch Dokumente, Geistesblitze, (handschriftliche) Mitschriften etc. sehr einfach verwalten und organisieren. Zudem gibt es gute Apps für iOS und Android, sowohl Desktopclients für Windows und MacOS vom Hersteller. Nur Linux bleibt mal wieder leider außen vor."
---

{{< alert >}}
Dieser Beitrag wurde zuletzt am 24. Februar 2020 aktualisiert: Seit Oktober 2017 ist keine neue Version von NixNote mehr erschienen. Es ist deshalb sinnvoller die Alternative [Tusk](https://klaussinani.tech/tusk/) einzusetzen.
{{< /alert >}}

Ich benutze den Notizdienst Evernote eigentlich sehr gerne, lassen sich mit ihm doch Dokumente, Geistesblitze, (handschriftliche) Mitschriften etc. sehr einfach verwalten und organisieren. Zudem gibt es gute Apps für iOS und Android, sowohl Desktopclients für Windows und MacOS vom Hersteller. Nur Linux bleibt mal wieder leider außen vor.

Natürlich läuft der Webclient auch im Browser unter Linux, aber manchmal hätte man halt gerne doch ein natives Desktopprogramm. Glücklicherweise gibt es für diesen Fall zwei inoffizielle Alternativen[^1]:

[^1]: Daneben gibt es natürlich als dritte Option noch die Möglichkeit den Windowsclient [mittels Wine][2] auch unter Linux zu betreiben.

Zum einen [Everpad][3], mit dessen Bedienkonzept ich allerdings nie ganz warm geworden bin, und zum anderen [NixNote][4] (früher NeverNote), welches sich enger am offiziellen Desktopclient orientiert. Nachdem es um NixNote lange Zeit still geworden war, ist nun Anfang April endlich die erste Betaversion von NixNote2 [erschienen][5].

Die neue Version wurde von Grund auf neu geschrieben und nutzt Java jetzt nur noch für die Ver- und Entschlüsselungsfunktion. Dadurch fühlt sich das Programm im Vergleich zur alten Version 1.5, auch bei größeren Notizsammlungen deutlich schneller und flüssiger an. Zwar handelt es sich noch um eine Beta, mit Fehlern und Abstürzen muss also gerechnet werden, aber ich konnte im Alltagseinsatz, bisher keine Probleme feststellen.

Auch dass einige Features (selektive Synchronisation, Synchronisation von farbigen Notizen) bisher fehlen, bzw. nicht wieder eingebaut werden (verschlüsselte Datenbank), konnte ich gut verschmerzen. Sicherlich gibt es noch eine Dinge die sich optimieren ließen. Die Optik ist beispielsweise weiterhin etwas altbacken und das neue Trayicon ist auch nicht gerade das hübscheste, benutzen lässt sich das Programm allerdings trotzdem im Alltag.

{{< figure src="images/NixNote-Default-Account_001.png" title="Hauptfenster von NixNote 2 Beta 1" >}}

## Fehlerhafte Textdarstellung im Editor

Das einzige ernstzunehmende Problem, dass mir untergekommen ist, war eine falsch eingestellte Schriftart für den Editor, durch welche die Notizen nicht wirklich lesbar waren. Eingestellt war eine Schriftart namens &#8220;04b&#8221;. Der Fehler lässt sich aber einfach dadurch beheben, dass man in den Einstellungen den &#8220;Default Editor Font&#8221; ändert.

{{< figure src="images/Selection_002.png" title="Fehlerhafte Textdarstellung" >}}

{{< figure src="images/Selection_003.png" title="Korrigierte Textdarstellung" >}}

## Download & Installation

Den Download von fertigen Paketen für die Installation von NixNote2 findet man bei [Sourceforge][5], dort gibt es .deb, .rpm und .tar.gz zur Auswahl. Unter Ubuntu 13.10 ließ sich die DEB-Datei ohne Probleme installieren. Archlinux Nutzer können das Programm einfach [über das AUR installieren][6]. Wer die Entwicklung verfolgen, Bugs anzeigen oder selbst zur Entwicklung beitragen möchte, findet bei [Github den Quellcode][7].

## Changelog seit der ersten Alpha

  * Deb, RPM, & tar.gz (with an install script) have been created.
  * Support for reminders.
  * Ability to capture images from a webcam.
  * You can open a note for editing in a new window.
  * If you enable uploads, linked notebooks will now be sent.
  * Support for encrypted text (RC2 only).
  * You can pin or unpin notes.
  * You can add HTML entities via a dialog box (thanks to Milos Kozina).
  * Basic support for note history (premium users only).
  * You can now open/close notebooks.
  * Note title colors can be changed (not synchronized).
  * You can import Evernote extract files (enex).
  * You can do backups, restores, imports & exports to NixNote extract files (nnex).
  * Spell check has been added.
  * Significant performance improvements when loading notes with a lot of resources and when generating thumbnails.
  * Sync is more efficient, faster, & should resume properly after interrupts.
  * Many other smaller changes.
  * Lots of bug fixes.
  * Lots of new bugs. Hopefully less than the number of bugs I corrected.
  * Upgraded from Thrift 0.9 to 0.9.1.

 [1]: https://klaussinani.tech/tusk/
 [2]: https://appdb.winehq.org/objectManager.php?sClass=application&iId=2566
 [3]: https://github.com/nvbn/everpad
 [4]: http://sourceforge.net/projects/nevernote/
 [5]: http://sourceforge.net/projects/nevernote/files/NixNote2%20-%20Beta%201/
 [6]: https://aur.archlinux.org/packages/nixnote2-git/
 [7]: https://github.com/baumgarr/nixnote2

{{< vgwort "a650d0fa094e4f3b8ac012f377eb8999" >}}