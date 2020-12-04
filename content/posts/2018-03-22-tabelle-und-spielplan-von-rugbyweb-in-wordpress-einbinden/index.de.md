---
title: Tabelle und Spielplan von Rugbyweb in WordPress einbinden
author: Christian Humm
date: 2018-03-22T10:39:48+00:00
url: /2018/03/22/tabelle-und-spielplan-von-rugbyweb-in-wordpress-einbinden/
categories:
  - IT
tags:
  - iFrame
  - rugby
  - rugbyweb.de
  - Wordpress
cover: cover.png
vgwort: c57c01349d3a49dc8fb3b83aebe02bfd
licence: cc-by
---
{{< figure src="/2018/03/22/tabelle-und-spielplan-von-rugbyweb-in-wordpress-einbinden/images/logo_rugbyweb.gif" alt="Logo von rugbyweb.de" class="float-left" >}}

Auf [rugbyweb.de][2] werden alle Ergebnisse und Spielpläne der verschiednen deutschen Rugby Union Ligen veröffentlicht. Leider hat die Seite den Charme der 90er Jahre und eine API zur Abfrage von Tabellensituationen, der Zusammensetzung von Ligen, Spielplänen oder Spielergebnissen gibt es nicht.

<!--more-->

Will man diese Informationen zum Beispiel auf der Homepage des eigenen Clubs einbinden, dann gibt es im Grunde nur zwei Möglichkeiten:

1. **Man überträgt die Informationen händisch.**\
  Unter WordPress kann man dafür beispielsweise das [Plugin SportPress][3] nutzen. Neben dem hohen Arbeitsaufwand für die regelmäßige Aktualisierung der Informationen, gibt es einen weiteren Haken: Auf Rugbyweb werden zwar die Spielergebnisse veröffentlicht, aber nicht die Zahl der gelegten Versuche pro Mannschaft. Da die Zahl der gelegten Versuche aber zum Beispiel in der Bundesliga über den [Offensivbonuspunkt][4] entscheidet, lässt sich etwa die Tabellensituation ohne zusätzliche Recherche nicht akkurat abbilden.

2. **Einbindung per iFrame**\
  Die zweite Möglichkeit ist die Anbindung per iFrame. Nachteil hierbei ist, dass sich die von Rugbyweb eingebundenen Informationen optisch nur bedingt anpassen lassen und man nur Tabellen und Spielergebnisse gemeinsam auf seiner Seite darstellen kann. Dafür spart man sich aber die ständigen Aktualisierungen nach jedem Spieltag. Wie genau die Einbindung per iFrame unter WordPress funktioniert, zeige ich im folgenden.

## Anleitung

Als Beispiel dient hierbei die [Seite der Rugbyabteilung des FSV Trier-Tarforst][5], da ich diese betreue.

1. Ihr benötigt ein Plugin, das es ermöglicht iFrames einzubinden. Ich nutze dafür [Advanced iFrame][6].
2. Sobald ihr das Plugin installiert und aktiviert habt, legt ihr eine Seite (keinen Beitrag!) an auf der die Tabelle und die Spielergebnisse angezeigt werden soll.
3. Dort nutzt ihr dann folgenden Shortcode zur Einbindung des iFrames:\
  `[advanced_iframe src="http://www.rugbyweb.de/showdb.inc.php?layout=rw2&league=RLnrwR" width="100%" height="1200"]`
  
    * Unter `src` muss die URL zur Seite [showdb.inc.php][7] von Rugbyweb angegeben werden mit den Parametern `layout` und `league`:
        * Der Parameter `layout` ermöglicht es aus fünf verschiedenen Designs zu wählen. Ihr habt die Wahl zwischen _rw_, _rw2_, _rj_, _scrum_ und _scrum2_.
        * `league` bestimmt welche Liga angezeigt werden soll. RLnrwR steht beispielsweise für die Regionalliga NRW Rheinland. Das Kürzel seht ihr wenn ihr über rugbyweb.de ganz normal die gewünschte Liga aufruft in der Adresszeile des Browsers.
        * `width` gibt die breite des iFrames an. Hier empfiehlt sich die Angabe `100%`.
        * `height` wiederum bestimmt die Höhe des iFrames. Hier muss man mit der Angabe experimentieren, was am besten aussieht.

4. Jetzt noch die Seite speichern und veröffentlichen, dann sieht es [beispielsweise so aus][8]:

{{<figure src="cover.png" title="Einbindung der Tabelle" link="https://www.c-m-l.net/blog/wp-content/uploads/2018/03/screenshot.png" >}}

 [1]: https://www.c-m-l.net/blog/wp-content/uploads/2018/03/logo_rugbyweb.gif
 [2]: http://www.rugbyweb.de
 [3]: https://de.wordpress.org/plugins/sportspress/
 [4]: https://de.wikipedia.org/wiki/Rugby-Union-Regeln#Punktwertung
 [5]: http://www.rugby-trier.de/
 [6]: https://de.wordpress.org/plugins/advanced-iframe/
 [7]: http://www.rugbyweb.de/showdb.inc.php
 [8]: http://www.rugby-trier.de/de/herren/tabelle/
 [9]: https://www.c-m-l.net/blog/wp-content/uploads/2018/03/screenshot.png
