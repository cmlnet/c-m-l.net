---
title: Neuen Skype-Client auf Arch Linux installieren
author: Christian Humm
date: 2016-07-13T17:57:21+00:00
url: /2016/07/13/neuen-skype-client-auf-arch-linux-installieren/
categories:
  - IT
  - Linux
tags:
  - Archlinux
  - Howto
  - Linux
  - Skype
cover: cover.png
---

Heute hat Microsoft endlich einen [neuen Skype-Client für Linux veröffentlicht][1]. Die bisherige Version wurde sehr stiefmütterlich gepflegt und hinkte den Versionen für Mac und Windows sichtbar hinterher. Nun also ein neuer Client, basierend auf WebRTC und bisland noch ohne Videotelefonie ([weitere Details bei heise online][2]). Trotzdem lief das Programm in einem ersten Test bei mir stabil und vor allem optisch deutlich besser aus.

{{< notice note >}}
Dieser Beitrag wurde zuletzt am _13. Februar 2020_ aktualisiert. Dabei wurden der Paketname aktualisiert, so dass die Anleitung wieder funktionieren sollte.
{{< /notice >}}

Erfreulicherweise gibt es [im Arch User Repository (AUR) auch schon ein Paket][3] mit dem sich der Client schnell und unkompliziert auf Arch Linux installieren lässt. Dazu einfach folgende Befehle ausführen:

```bash
pacaur -S skypeforlinux-stable-bin
```

Oder falls _[pacaur][4]_ nicht installiert ist:

```bash
wget https://aur.archlinux.org/cgit/aur.git/snapshot/skypeforlinux-stable-bin.tar.gz
tar -xzf skypeforlinux-stable-bin.tar.gz
cd skypeforlinux-stable-bin
makepkg -s
sudo pacman -U skypeforlinux-stable-bin*-.xz
```


 [1]: https://community.skype.com/t5/Linux/Skype-for-Linux-Alpha-and-calling-on-Chrome-amp-Chromebooks/td-p/4434299
 [2]: http://www.heise.de/newsticker/meldung/Neustart-fuer-Skype-auf-Linux-3266335.html
 [3]: https://aur.archlinux.org/packages/skypeforlinux-stable-bin/
 [4]: https://aur.archlinux.org/packages/pacaur/
