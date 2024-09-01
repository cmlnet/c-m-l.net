---
title: Arc Theme – ein schönes GTK3, GTK2 und GNOME Shell Design
author: Christian Humm
date: 2015-06-07T09:40:05+00:00
url: /2015/06/07/arc-theme-ein-schoenes-gtk3-gtk2-und-gnome-shell-design/
categories:
  - Linux
tags:
  - Archlinux
  - Design
  - GNOME Shell
  - GTK2
  - GTK3
  - Theme
cover: cover.png
summary: "Auf meinem Desktop benutzte ich zum arbeiten Linux, genauer gesagt Arch Linux und als Desktop-Environment kommt dort, nach Ausflügen zu XFCE und Cinnamon, schon länger die GNOME Shell zum Einsatz. Das Standardtheme der GNOME Shell &#8211; Adwaita &#8211; gefällt  mir dabei allerdings nicht wirklich, also bin ich immer auf der Suche nach alernativen Themes für die Shell."
---

Auf meinem Desktop benutzte ich zum arbeiten Linux, genauer gesagt <a href="https://www.archlinux.org">Arch Linux</a> und als Desktop-Environment kommt dort, nach Ausflügen zu XFCE und Cinnamon, schon länger die <a href="https://wiki.gnome.org/Projects/GnomeShell">GNOME Shell</a> zum Einsatz. Das Standardtheme der GNOME Shell &#8211; Adwaita &#8211; gefällt  mir dabei allerdings nicht wirklich, also bin ich immer auf der Suche nach alernativen Themes für die Shell.

Dank <a href="http://www.omgubuntu.co.uk/2015/06/arc-gtk-theme">OMG! Ubuntu!</a> bin ich vor kurzem auf einen neuen, sehr hübschen Vertreter seiner Art gestoßen: das <a href="https://github.com/horst3180/Arc-theme">Arc Theme</a>. Ein Theme das auf eine flache, teil-transparentes Aussehen setzt. Das Theme unterstützt GTK 3, GTK 2 und die Gnome-Shell (Version 3.14 & 3.16), sowie auf GTK basierende Desktop-Environments wie Unity, Budgie, Pantheon, etc.

{{< figure src="images/arc_weather.png" title="GNOME Shell Extension Weather" >}}

{{< figure src="images/arc_shell.png" title="GNOME Shell Aktivitätenübersicht" >}}

{{< figure src="images/arc_desktop.png" title="GNOME Shell mit Nautilus" >}}

{{< figure src="images/arc_clock.png" title="GNOME Shell Uhrzeit/Kalender-Widget" >}}

## Installation

Für Ubuntu, Debian, Fedora und openSUSE stellt der Entwickler freundlicherweise [fertige Pakete zur Verfügung][1]. Für Arch Linux gibt es [einen Eintrag im AUR][2], so dass die Installation ebenfalls schnell von der Hand geht:

```
pacaur -Ss gtk-theme-arc-git
```

Zu dem Theme passen gut die [Ozon Icons][3], für die es ebenfalls einen [Eintrag im AUR][4] gibt.

 [1]: http://software.opensuse.org/download.html?project=home%3AHorst3180&package=arc-theme
 [2]: https://aur.archlinux.org/packages/gtk-theme-arc-git/
 [3]: https://github.com/ozonos/ozon-icon-theme
 [4]: https://aur.archlinux.org/packages/ozon-icon-theme-git/
