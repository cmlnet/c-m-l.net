---
title: 'HowTo: WebDAV und Plesk 9'
author: Christian Humm
date: 2009-08-08T20:39:29+00:00
url: /2009/08/08/howto-webdav-und-plesk-9/
featuredImage: img/plesk_webdav_screenshot_01.png
categories:
  - Server
tags:
  - Apache2
  - Howto
  - Plesk
  - WebDAV
cover: "img/plesk_webdav_screenshot_01.png"
vgwort: 3ae1af2ce63244a0ae184a92c8ef0081
---
Zwar unterstützt [Plesk][1] 9 offiziell kein [WebDAV][2] und bringt entsprechend auch keine Oberfläche zur Aktivierung und Administration mit. Dennoch geht die Einrichtung von WebDAV auch auf Servern mit Plesk und [Apache2][3] schnell von der Hand.

<!--more-->

## 1. Aktivieren des Apache-Moduls

Bevor man WebDAV benutzen kann, müssen zuerst einmal die beiden Module mod\_dav und mod\_davfs für den Apache2 aktiviert werden. Dazu gehe ich im folgenden von Ubuntu 8.04 LTS als zugrundeliegender Distribution aus, bei anderen Distributionen kann sich das Vorgehen stark unterscheiden.

Normalerweise müssten die beiden benötigten Mods schon mit dem Apache2 mitgeliefert werden, d.h.&nbsp; es müssen keine neuen Pakete installiert werden.

{{< notice note >}}
**UPDATE 10. August 2009**

Noch einfacher geht das ganz mit dem kleinen Tool `a2enmod`, welches zumindest bei mir schon mit den Apache2 Paketen installiert wurde. Es genügt einfach folgende 2 Befehle auszuführen und man spart sich das Anlegen von symbolischen Verknüpfungen (auch die in Schritt 2):

```shell
a2enmod dav
a2enmod dav_fs
```
{{< /notice >}}

Alle für Apache momentan verfügbaren Mods werden im Verzeichnis `/etc/apache2/mods-available` aufgelistet. Dort sollten sich auch die beiden Dateien `dav.load` und `dav_fs.load` finden lassen. Um diese nun zu aktivieren gilt es eine symbolische Verknüpfung zu ihnen im Verzeichnis `/etc/apache2/mods-enabled` anzulegen:

```shell
ln -s /etc/apache2/mods-available/dav.load /etc/apache2/mods-enabled/dav.load
ln -s /etc/apache2/mods-available/dav_fs.load /etc/apache2/mods-enabled/dav_fs.load
```

Nachdem der Apache neu gestartet wurde, lädt er die beiden Module. Um das zu überprüfen kann man auf der Konsole _apache2ctl -M_ eingeben, dort werden dann alle geladenen Module ausgegeben.

## 2. Anlegen der LockDB

Jetzt muss noch die sogenannte LockDB angelegt werden. Hierzu muss zuerst ein Verzeichnis angelegt und mit den richtigen Zugriffsrechten ausgestattet werden:

```shell
mkdir /var/lock/dav
chmod 755 /var/lock/dav
chown www-data /var/lock/dav
```

_www-data_ ist dabei durch den Benutzer zu ersetzen unter dem Apache läuft und ist von Distribution zu Distribution unterschiedlich.

Nun muss der Ort der LockDB noch dem Apache mitgeteilt werden. Dazu öffnet man die Datei _/etc/apache2/mods-available/dav_fs.conf_ bzw. legt sie an falls sie noch nicht existiert und schreibt folgendes hinein:

```shell
DAVLockDB "/var/lock/dav/lockdb"
```

_lockdb_ bezeichnet dabei eine Datei die der Server selbst anlegt. Die Konfigurationsdatei muss jetzt wieder mit Hilfe eines Symlinks so verknüpft werden, dass sie beim Start des Servers berücksichtigt wird:

```shell
ln -s /etc/apache2/mods-available/dav_fs.conf /etc/apache2/mods-enabled/dav_fs.conf
```

## 3. Anlegen des WebDAV-Verzeichnisses

Nun sind alle Vorarbeiten abgeschlossen und es geht an die eigentliche Einrichtung des WebDAV-Verzeichnisses. Zuerst muss dabei wieder der Ordner selbst angelegt und mit den richtigen Zugriffsrechten ausgerichtet werden:

```shell
mkdir /var/www/vhosts/meinedomain.tld/httpdocs/webdav
chmod 755 /var/www/vhosts/meinedomain.tld/httpdocs/webdav
chown www-data /var/www/vhosts/meinedomain.tld/httpdocs/webdav
```

## 4. Konfiguration des Verzeichnisses

Die Konfiguration geschieht über die Datei _vhost_ssl.conf_ unter _/var/www/vhosts/meinedomain.tld/conf/_ . In diese Datei gehört dabei mindestens folgende Angabe:

```shell
<Directory /var/www/vhosts/meinedomain.tld/httpdocs/webdav>
DAV on
</Directory>
```

Weitere sinnvolle Konfigurationsoptionen die nach &#8220;DAV on&#8221; eingefügten werden können sind zum Beispiel:

  * **AllowOverride none**<br />
    Sorgt dafür, dass eine .htaccess im WebDAV-Verzeichnis nicht interpretiert wird.
  * **RewriteEngine Off**<br />
    Sorgt dafür, dass etwaige Rewrite Rules nicht zur Anwendung kommen. Dies ist insbesondere dann sinnvoll, wenn WebDAV nicht funktioniert und im ErrorLog des Apache die Fehlermeldung _&#8220;Cannot create collection; intermediate collection does not exist.&#8221;_ auftaucht.
  * **ForceType text/plain**<br />
    Sorgt dafür, dass Skripte im WebDAV-Ordner nicht interpretiert werden.
  * **Options Indexes**<br />
    Erlaubt das Auflisten des Verzeichnisinhalts.

## 5. Schutz des Verzeichnisses in Plesk 9

Jetzt funktioniert zwar WebDAV, aber jeder kann in das Verzeichnis schreiben, was natürlich möglichst vermieden werden sollte. Deshalb gilt es einen Verzeichnisschutz einzurichten, sodass nur nach Eingabe des richtigen Usernamens und Passworts ein Zugriff möglich ist. Am einfachsten lässt sich dies über Plesk selbst erledigen.

Hierzu ruft man in Plesk die Übersichtsseite für die jeweilige Domain auf und klickt dort auf _Password Protected Directories_ (1):

{{< figure src="img/plesk_webdav_screenshot_01.png" caption="Aufruf _Password Protected Directories_" attr="" attrlink="" >}}

Im zweiten Schritt muss dann _Add Protected Directory_ angeklickt werden (2):

{{< figure src="img/plesk_webdav_screenshot_02.png" caption="Aufruf _Add Protected Directory_" attr="" attrlink="" >}}

Auf der sich nun öffneten Seite muss das WebDAV-Verzeichnis eingeben werden und zwar relativ zum Order _httpdocs_ der Domain. In unserem Fall muss also _/webdav_ eingetragen werden (3). Dann heißt es nochmal auf _OK_ klicken (3):

{{< figure src="img/plesk_webdav_screenshot_03.png" caption="Angeben des zu schützenden Verzeichnisses" attr="" attrlink="" >}}

Nun wird man auf eine weitere Seite weitergeleitet. Hier gilt es nun einen neuen Benutzer für dieses Verzeichnis anzulegen. Wie zu vermuten sollte man dazu auf Add New User klicken (5):

{{< figure src="img/plesk_webdav_screenshot_04.png" caption="Aufruf _Add New User_" attr="" attrlink="" >}}

Jetzt muss nur noch ein Username (1) und zweimal ein Passwort eingetragen werden (2):

{{< figure src="img/plesk_webdav_screenshot_05.png" caption="Festlegen von Benutzername und Passwort" attr="" attrlink="" >}}

Jetzt ist das Verzeichniss vor unbefugten Zugriff geschützt und wir können mit dem letzten Schritt weitermachen.

## 6. Neustart des Apache

Nun müssen die zahlreichen Konfigurationsänderungen noch Plesk respektive dem Apache2 mitgeteilt werden. Dazu dient folgender Befehl:

```shell
/usr/local/psa/admin/sbin/websrvmng -v -a
```

Jetzt sollte das Verzeichnis unter `https://meinedomain.tld/webdav/` angesprochen werden können. Wer gerne testen möchte, ob alles klappt, dem sei [cadaver][4] empfohlen, ein kleiner WebDAV-Client für die Konsole.

Wenn es nicht klappt, dann ist oftmals ein Blick in das Fehlerprotokoll des Apache hilfreich. Dieses sollte sich bei Webservern mit Plesk üblicherweise unter `/var/www/vhosts/meinedomain.tld/statistics/logs` zu finden.

## Hinweise

Besonderer Dank gilt an dieser Stelle Otto Berger der in seinem Blog bergercity.de bereits [eine ähnliche Anleitung veröffentlicht][5] hat, die mir beim experimentieren mit Plesk und WebDAV eine große Hilfe war.

 [1]: http://www.parallels.com/de/products/plesk/ "Offizielle Produktseite zu Parallels Plesk Panal"
 [2]: http://de.wikipedia.org/wiki/WebDAV "Wikipedia Artikel zu WebDAV"
 [3]: http://de.wikipedia.org/wiki/Apache_HTTP_Server "Wikipedia Artikel zu dem HTTP-Server Apache"
 [4]: http://www.webdav.org/cadaver/
 [5]: http://www.bergercity.de/linux/plesk-webdav-nutzen/ "Plesk: WebDAV nutzen"
