---
title: whistle.im unsicher – Mögliche Messenger-Alternativen
author: Christian Humm
date: 2013-08-19T19:38:41+00:00
url: /2013/08/19/whistle-im-unsicher-moegliche-messenger-alternativen/
categories:
  - IT
tags:
  - Android
  - iOS
  - Sicherheit
  - Verschlüsselung
toc: false
vgwort: 12c962fc2fde4c179bb1e76141330634
summary: "Während WhatsApp weiterhin als unsicherer Sofortnachrichtendienst gilt, versuchen sich momentan in der Bugwelle PRISM-Skandals diverse Anbieter mit angeblich sicheren Alternativen am Markt zu positionieren. Eine dieser Alternativen ist whistle.im, dass von zwei deutschen Studenten entwickelt wird. Laut eigener Aussage soll dieser Messenger Kinderleicht zu bedienen und dennoch abhörsicher sein. Allzu viel scheint an diesem Versprechen aber nicht dran zu sein, wie eine Analyse des CCC-Mitglieds _nexus_ zeigt."
---
Während WhatsApp weiterhin [als unsicherer Sofortnachrichtendienst gilt][1], versuchen sich momentan in der Bugwelle PRISM-Skandals diverse Anbieter mit angeblich sicheren Alternativen am Markt zu positionieren. Eine dieser Alternativen ist [whistle.im][2], dass von zwei deutschen Studenten entwickelt wird. Laut eigener Aussage soll dieser Messenger Kinderleicht zu bedienen und dennoch abhörsicher sein. Allzu viel scheint an diesem Versprechen aber nicht dran zu sein, wie eine [Analyse des CCC-Mitglieds _nexus_][3] zeigt.

_nexus_ bescheinigt whistle.im &#8220;alles in allem ein vollkommen undurchdachtes Konzept&#8221; zu haben und nur eines tatsächlich zu leisten, nämlich seinem Vorbild WhatsApp in Sachen Sicherheitsmängeln in nichts nach zu stehen. Konkret nennt der Hacker acht problematische Punkte, die tatsächlich große Zweifel am Konzept der Software wecken:

>   1. Der Dienstanbieter betreibt einen Keyserver, auf dem die RSA-Keys aller Kommunikationsteilnehmer abgelegt sind. Dies bedeutet, dass der Anbieter die Schlüssel an die Nutzer austeilt. Dort kann natürlich ein gefälschter Key ausgeliefert werden und somit die Kommunikation mitgelesen werden.
>   2. Die privaten Schlüssel der Kommunikationsteilnehmer liegen (wenn auch verschlüsselt) auf dem Server des Dienstanbieters. Erhält dieser Kenntnis vom Passwort, so kann nachträglich jede Kommunikation entschlüsselt werden.
>   3. Es handelt sich um einen zentralen Dienst. Daher ist der Dienstanbieter auch in er Lage herauszufinden, wer, wann mit wem für wie lange kommuniziert.
>   4. Die Cryptographischen-Verfahren mögen als Javascript vorliegen. Nicht aber die Applikation. Das Wort OpenSource stiftet mehr Verwirrung als Klarheit. Was die Applikation an sich tut, bleibt verborgen.
>   5. Grundlegende Konzepte aktueller Verschlüsselungsverfahren wurden nicht verstanden.
>   6. Die Serverkommunikation hält Man-in-the-Middle-Angriffen nicht Stand.
>   7. Alle Keys werden vor Kommunikationsbeginn immer mit dem Keyserver ausgetauscht. Damit kann ein Angreifer, der eine Man-in-the-Middle-Attacke durchführt jederzeit in eine Kommunikation eingreifen und diese auch mitlesen. Eingeschränkt wird diese Möglichkeit nur durch die kryptische Anzeige des Fingerprints des RSA-Keys im Display.
>   8. Ein Angreifer kann problemlos eine Session &#8220;hijacken&#8221; und damit selbst Kommunikationspartner werden.

## Alternativen

Nun stellt sich natürlich die Frage, welchen Messenger man stattdessen zum sicheren Nachrichtenaustausch verwenden sollte. Auf den ersten Blick scheint es einige Alternativen zu geben. Allerdings haben fast alle einen mehr oder weniger großen Haken:

  * [Threema][4] kostet Geld und ist nicht OpenSource, die Sicherheit kann also nicht vollständig überprüft werden. Ähnliches gilt zum Beispiel auch für Viper.
  * <s>Heml.is hört sich zwar interessant an, befindet sich aber noch in der Entwicklung.</s>
  * [Kontalk][5] ist OpenSource, kostenlos und zudem noch dezentral &#8211; hat aber den &#8211; eventuell entscheidenden &#8211; Nachteil, dass es a) kaum verbreitet ist und b) aktuell nur unter Android läuft. Zumindest letzteres soll sich aber noch ändern.
  * Jabber/XMPP in Kombination mit OTR (Off-the-record Verschlüsselung) ist ebenfalls OpenSource, kostenlos und dezentral, ist aber weiter verbreitet als Kontalk und es gibt zudem Clients die auch auf dem normalen Desktop-PC laufen (bspw. [Pidgin][6] oder [Miranda][7]). Für Android gibt es mit [Xabber][8] und <s>Gibberbot</s>  gleich zwei Apps die OTR beherrschen, für iOS mit [ChatSecure][9] nur eine.

Zu empfehlen sind aktuell nur Kontalk und Jabber/XMPP. Ersteres hat bisher keine große Verbreitung und ist auf Android beschränkt, letzteres ist in seiner Benutzung nicht ganz so komfortabel und intuitiv.

 [1]: http://irights.info/whatsapp-wie-riskant-ist-der-messagingdienst "iRight.info - Whatsapp: Wie riskant ist der Messagingdienst?"
 [2]: https://whistle.im/
 [3]: http://hannover.ccc.de/~nexus/whistle.html "whistle.im: FaaS - Fuckup as a Service"
 [4]: http://threema.ch/
 [5]: http://www.kontalk.org/
 [6]: http://pidgin.im/
 [7]: http://miranda-im.org
 [8]: http://www.xabber.com/
 [9]: https://itunes.apple.com/us/app/chatsecure-encrypted-secure/id464200063?mt=8

{{< vgwort "12c962fc2fde4c179bb1e76141330634" >}}