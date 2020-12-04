---
title: 'HowTo: EncFS unter Mac OS X 10.9 (Mavericks)'
author: Christian Humm
date: 2014-06-21T12:56:22+00:00
url: /2014/06/21/encfs-unter-mac-os-x-10-9-mavericks/
categories:
  - Mac OS
  - Sicherheit
tags:
  - EncFS
  - Mac OS
  - Security
  - Verschlüsselung
vgwort: 4528bc224fa744c7b650475faa1f570c
---
Möchte man seine Daten sicher in bei [Dropbox][1], Google Drive, [OneDrive][2] oder sonst irgendeinem Clouddienst speichern, hat man prinzipiell mehrere Möglichkeiten. Man kann den Beteuerungen der Anbieter, dass sie ihre Dienste und Daten sicher speichern glauben schenken ([Copy][3] etwa wirbt damit, dass die Daten mit 256 AES verschlüsselt würden). Man kann selbst einen Cloudspeicher hosten, etwa mittels [ownCloud][4]. Allerdings sollte dabei beachtet werden, dass das ganze dann natürlich nicht kostenlos ist und auch nur sicher, wenn man entsprechende Ahnung von Serveradministration und -absicherung hat. Man kann aber einen der großen Dienste nutzen und die Daten dabei nochmal extra verschlüsseln.

<!--more-->

Prinzipiell gibt es dafür mehrere Möglichkeiten: Eine der bekannteren dürfte das anlegen eines TrueCrypt-Containers sein, den man dann mittels Dropbox oder ähnlichem in die Cloud verfrachtet. Seit der [Einstellung des TrueCrypt-Projekts][5] sollte man die Software aber sofern möglich nicht weiter einsetzen. Was tun also, um seine Dateien in der Cloud verschlüsselt zu speichern? Die Lösung heißt [EncFS][6].

EncFS ist ein Open-Source-Dateisystem, welches komplette Verzeichnisse mittels eines Passworts verschlüsseln und transparent ins Betriebssystem einbinden kann. Zum gegenwärtigen Zeitpunkt gilt das Programm als sicher. Es stammt aus der Unix-Welt und dort ist die Installation und Benutzung auch am einfachsten. Dennoch kann es auch unter Windows, Android und auch Mac OS X benutzt werden &#8211; wie man für letzteres vorgehen muss, wird im Folgenden beschrieben.

## 1. Installation von Homebrew

Als erstes gilt es [Homebrew][7] auf seinem System zu installieren. Das ist ein alternativer Paketmanager mit sich relativ einfach Programme (aus dem Unix-Bereich) nachinstallieren lassen. Zur Installation startet man ein Terminal und gibt folgenden Befehl ein:

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## 2. Installation von encfs

Danach wird mittels Homebrew encfs aufgespielt:

```bash
brew install encfs
```

## 3. Kernelmodule laden

Nun müssen noch die Kernelmodule von encfs an die richtigen Stellen kopiert werden, damit Mac OS den verschlüsselten Ordner einbinden kann:

```bash
sudo /bin/cp -RfX /usr/local/Cellar/osxfuse/2.6.4/Library/Filesystems/osxfusefs.fs /Library/Filesystems/
sudo chmod +s /Library/Filesystems/osxfusefs.fs/Support/load_osxfusefs
```

## 4. Verschlüsselten Ordner erstellen und einbinden

Die weitere Benutzung ist relativ einfach. EncFS bindet einen verschlüsselten Ordner (Wurzelverzeichnis) entschlüsselt in einen anderen Ordner (Mountpunkt) ein. Man selbst arbeitet nur mit dem entschlüsselten Mountpunkt, das verschlüsselte Wurzelverzeichnis lässt man in Ruhe, um diesen kümmert sich EncFS schon selbst.

Zuerst gilt es beide Ordner zu erstellen:

```
encfs ~/Dropbox/Private.enc/ ~/Private/
```

Der Befehl sorgt dafür, dass das verschlüsselte Wurzelverzeichnis _.encrypted_ im Dropboxordner und der Mountpunkt _Private_ im Benutzerverzeichnis erstellt wird. Das Passwort mit dem die Dateien verschlüsselt werden, muss man im Lauf dieses Schritts eingeben. Falls dabei eine Warnung mit dem Text “Kernel extension is not from an identified developer” auftaucht, so bestätigt man diese mit &#8220;OK&#8221;.

{{< figure src="images/kernel-extension-warning.png" >}}

Möchte man das EncFS-Verzeichnis später einbinden, so genügt es den gleichen Befehl einfach nochmals ins Terminal einzugeben und im Folgenden, dann das zuvor festgelegt Passwort einzugeben:

```
encfs ~/Dropbox/Private.enc/ ~/Private/
```

Die verschlüsselten Dateien in _Private.enc_ werden entschlüsselt im Ordner _Private_ dargestellt. Legt man nun beispielsweise im Ordner _Private_ eine neue Datei an, so wird diese von EncFS verschlüsselt und im Ordner _.encrypted_ gespeichert.

Um das Verzeichnis auszuwerfen, genügt folgender Befehl:

```
umount ~/Dropbox/Private.enc/
```

## 5. Alternativ: Grafische Benutzeroberfläche zum Einbinden benutzen

Nun mag vielleicht nicht jeder, ständig mit dem Terminal hantieren nur um den EncFS-Ordner einzubinden. Erfreulicherweise lässt sich das ganze auch mittels einer grafischen Benutzeroberfläche erledigen:

  1. Man lädt das Programm [Macfusion 2][9] sowie das zugehörige [EncFS-Plugin][10] und installiert beide.
  2. Nun startet man Macfusion und fügt per Klick auf das +-Symbol ein EncFS-Volumne hinzu
  {{< figure src="images/Screenshot-Macfusion-1.png" >}}
  3. Im folgenden Dialog kann man den verschlüsselten Ordner auswählen:
  {{< figure src="images/Screenshot-Macfusion-2.png" >}}
    Falls man noch keinen verschlüsselten Ordner angelegt hat, so fragt Macfusion direkt, ob es das auch noch erledigen sollen:
  {{< figure src="images/Screenshot-Macfusion-3.png" >}}
  {{< figure src="images/Screenshot-Macfusion-4.png" >}}
  4. Standardmäßig bindet Macfusion den Ordner unter einem zufälligen Namen ein. Da das eher unpraktisch ist, sollte man im Reiter &#8220;Macfusion&#8221; noch den gewünschten Mountpunkt angeben:
  {{< figure src="images/Screenshot-Macfusion-5.png" >}}
  5. Nun kann man den EncFS-Ordner im Hauptfenster von Macfusion durch einen Klick auf &#8220;Mount&#8221; einbinden. Damit Macfusion auf das gespeicherte Passwort zum Entschlüsseln zugreifen kann, muss man dem Programm beim ersten Einbinden noch erlauben immer auf den Schlüsselbund zugreifen zu dürfen.

 [1]: https://db.tt/u7LmdZP
 [2]: https://onedrive.live.com/?invref=07766b6fd437c2f7&invsrc=90
 [3]: https://copy.com?r=8aUfqv
 [4]: http://www.owncloud.org/
 [5]: http://www.heise.de/security/artikel/Truecrypt-ist-unsicher-und-jetzt-2211475.html
 [6]: https://en.wikipedia.org/wiki/EncFS
 [7]: http://brew.sh/
 [8]: http://www.c-m-l.net/blog/wp-content/uploads/2014/06/kernel-extension-warning.png
 [9]: http://macfusionapp.org/
 [10]: http://thenakedman.wordpress.com/encfs/
