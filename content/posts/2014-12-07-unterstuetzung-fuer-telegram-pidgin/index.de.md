---
title: Unterstützung für Telegram in Pidgin
author: Christian Humm
date: 2014-12-07T14:18:26+00:00
url: /2014/12/07/unterstuetzung-fuer-telegram-pidgin/
categories:
  - IT
  - Linux
tags:
  - Archlinux
  - Instant Messaging
  - Telegram
  - ubuntu
cover: cover.png
vgwort: 13049f7fcaac404b98dc6a32aca58140
summary: "Möchte man Telegram unter Linux benutzen, so gibt es mehrere Möglichkeiten. Entweder man greift zur universellen Webversion, zum offiziellen Desktopclient oder zu alternativen Clients wie Sigram. Noch ein zusätzliches Programm zum chatten? Och no, mögen vielleicht einige denken. Auch ich möchte nicht für jeden Messagingdienst ein eigenes Programm starten müssen &#8211; wozu gibt es schließlich Multiprotokoll-Messenger. Erfreulicherweise gibt es für Telegram ein Plugin für Pidgin, dessen Installation und Einrichtung ich im Folgenden kurz beschreiben möchte."
---

Eine aktuell angesagt Alternative zu WhatsApp, Facebook Messenger & Co. ist [Telegram][1]. Den Messenger ist nicht nur auf vielen Platformen verfügbar und kostenlos, sondern legt zumindest nach außen hin auch großen Wert auf das Thema Sicherheit und Verschlüsselung.

Möchte man Telegram unter Linux benutzen, so gibt es mehrere Möglichkeiten. Entweder man greift zur universellen [Webversion][2], zum [offiziellen Desktopclient][3] oder zu alternativen Clients wie [Sigram][4]. Noch ein zusätzliches Programm zum chatten? Och no, mögen vielleicht einige denken. Auch ich möchte nicht für jeden Messagingdienst ein eigenes Programm starten müssen &#8211; wozu gibt es schließlich Multiprotokoll-Messenger. Erfreulicherweise gibt es für Telegram ein Plugin für Pidgin, dessen Installation und Einrichtung ich im Folgenden kurz beschreiben möchte.

## Telegram Purple

Das Plugin namens _Telegram-Purple_ ist noch relativ jung und unter aktiver Entwicklung, wie ein Blick auf das entsprechende [Repository bei Github][5] schnell zeigt. Deswegen werden auch bisher nur grundlegende Funktionen &#8211; senden & empfangen von Nachrichten, Anzeige des Onlinestatus von Kontakten, Empfangen von Bildern &#8211; unterstützt. In Zukunft soll aber unter anderem die Unterstützung von verschlüsselten Chats, Bild- / Audio- / Videonachrichten, Dateiübertragungen hinzukommen.

## Installation

Unter Archlinux findet sich [die aktuelle Entwicklerversion im AUR][6] und kann mit dem AUR-Helper eurer Wahl installiert werden (in meinem Fall pacaur):

`pacaur -S telegram-purple-git`

Für Ubuntu betreibt [Andrew von WebUpd8][7] netterweise ein PPA in dem auch _Telegram Purple_ enthalten ist, dass sich mit folgenden Befehlen einrichten lässt:

```
sudo add-apt-repository ppa:nilarimogard/webupd8
sudo apt-get update
sudo apt-get install telegram-purple
```

Für andere Distributionen muss man etwas mehr Handarbeit betreiben. Im Repository der Entwickler gibt es aber ein wenig [Hilfestellung][8].

## Einrichtung

Nach der Installation fügt man in Pidigin ganz normal ein neues Konto hinzu, dabei dann als Protokoll &#8220;Telegram&#8221; auswählen. Ins Feld Benutzer einfach die Handynummer inklusive Landesvorwahl eintragen und auf &#8220;Hinzufügen&#8221; klicken:

{{< figure src="images/Konto-hinzufügen_001.png" alt="Telegram Purple - Konto hinzufügen" title="'Konto hinzufügen'-Dialog" >}}

Telegram sendet danach zur Verifikation einen Code per SMS an die angegebene Handynummer. Diesen einfach in den aufpoppenden Dialog eintragen und damit ist die Einrichtung schon abgeschlossen:

{{< figure src="images/Telegram-Code_002.png" alt="Telegram Code" title="Popup-Dialog zur Verifikation des Accounts" >}}

In der Buddy-Liste von Pidgin werden die eigenen Telegram-Kontakte nach erfolgreicher Einrichtung in einer eigenen Kategorie aufgeführt.

{{< figure src="images/Buddy-Liste_003.png" alt="Telegram Purple Buddy-Liste" title="Buddy-Liste mit Telegram-Kontakten" >}}

 [1]: https://telegram.org/
 [2]: https://web.telegram.org/
 [3]: https://desktop.telegram.org/
 [4]: http://labs.sialan.org/projects/sigram
 [5]: https://github.com/majn/telegram-purple
 [6]: https://aur.archlinux.org/packages/telegram-purple-git/
 [7]: http://www.webupd8.org/2014/11/add-telegram-support-to-pidgin-with.html
 [8]: https://github.com/majn/telegram-purple/blob/master/README.md

{{< vgwort "13049f7fcaac404b98dc6a32aca58140" >}}