---
title: Synchronisierungsprobleme zwischen Zotero und Papership (temporär) beheben
author: Christian Humm
date: 2019-05-03T07:16:10+00:00
url: /2019/05/03/synchronisierungsprobleme-zwischen-zotero-und-papership-temporaer-beheben/
categories:
  - iOS
  - IT
  - Wissenschaft
tags:
  - Literaturverwaltung
  - Wissenschaft
  - Zotero
cover: cover.png
vgwort: 3840a8f9e9b7439a86428bbfa57869f4
licence: cc-by
---
[Zotero][1] ist ein ziemlich großartiges Literaturverwaltungsprogramm, dem es allerdings an tauglichen Apps für Tablets fehlt. Eine Ausnahme ist [Papership][2] für iOS. Mit dieser App ist es möglich nicht nur möglich die in Zotero angelegte Literatursammlung zu verwalten, sondern auch Texte zu annotieren.

Umso schmerzlicher also, dass Papership [nicht mehr aktiv gepflegt wird][3] und es mit der aktuellen Version von Zotero zu Problemen bei Synchronisierung von angehängten Dateien, ergo Texten, kommt. Glücklicherweise lässt sich das Problem relativ schnell lösen – zumindest vorübergehend.

<!--more-->

Gestestet habe ich das ganze nur mit der Dateisynchronisierung via WebDAV. Papership bietet darüberhinaus noch eine Synchronisierung via _box.com<_ oder über Zotero selbst an. Zumindest bei erster Möglichkeit taucht das Problem wohl auch auf.

## Das Problem

Wie äußert sich das Problem bei der Dateisynchronisierung? Änderungen die man in Papership an Texten vornimmt, also etwa Markierungen, werden nicht hochgeladen und tauchen damit auch nicht in den in Zotero angehängten Dateien auf. Eine Fehlermeldung geben dabei weder von Papership noch Zotero aus, weshalb es manchmal etwas dauert, bis das Problem auffällt.

Verifizieren lässt es sich aber über die Einstellungen von Papership unter dem Punkt _Zotero File Hosting_: Wenn man dort auf _Verify Server_ klickt erhält man folgende Fehlermeldung:

{{< figure src="images/papership_sync_fehlermeldung.png" caption="Fehlermeldung _Cannot Verify Server_ in Papership" >}}

## Die Ursache

Der Grund für den Fehler liegt in der fehlenden Datei lastsync.txt. Diese Datei haben ältere Versionen von Zotero (bis einschließlich Version 4) automatisch angelegt und Papership sucht sie noch immer. Findet die App sie nicht, dann lädt sie keine Dateien mehr hoch.

## Die Lösung


Die Lösung ist simpel: Es muss einfach nur die leere Datei _lastsync.txt_ im Dateiverzeichnis von Zotero, also dort wo die angehängten Texte gespeichert werden, angelegt werden. Danach funktioniert sowohl das hochladen von annotierten Texten als auch die Verifizierung des Servers wieder:

{{< figure src="images/papership_erfolgreiche_serververifikation.png" caption="Erfolgreiche Serververifikation in Papership" >}}

Die Lösung ist leider nicht dauerhaft, da Zotero die Datei von Zeit zu Zeit wieder löscht. Ein Muster wann dies der Fall ist, konnte ich allerdings nicht erkennen. Wenn es also wieder zu Problemen bei der Synchronisierung kommt, muss die Datei erneut angelegt werden.

 [1]: https://www.zotero.org/
 [2]: https://www.papershipapp.com/
 [3]: https://forums.zotero.org/discussion/comment/289064/
