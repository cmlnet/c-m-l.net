---
title: 'LaTeX 101: Manuelle Zeilenumbrüche in Tabellenzellen'
author: Christian Humm
date: 2019-12-17T19:39:49+00:00
url: /2019/12/17/latex-101-manuelle-zeilenumbrueche-in-tabellenzellen/
categories:
  - HowTo
  - IT
tags:
  - how to
  - Howto
  - latex
  - makecell
  - parbox
toc: true
cover: cover.png
vgwort: 05b86b09fbd64206865c5ab76678b460
---

Manchmal braucht man manuelle Textumbrüche in Tabellenzellen. Was in Word oder LibreOffice selbstverständlich und einfach funktioniert, ist in LaTeX gar nicht so einfach. Die herkömmliche Methode mittels `\\` oder `\linebreak` einen Zeilenumbruch zu setzen, kann in Tabellenumgebungen nämlich nicht benutzt werden. Aber wie für alles gibt es auch hierfür natürlich eine Lösung in LaTeX – in Wirklichkeit gibt es natürlich wahrscheinlich zig Lösungen, aber das sind die zwei von mir benutzten.

<!--more-->

## 1. Das `parbox` Kommando

Die erste Möglichkeit ist das Kommando `\parbox`. Mit dem Parameter für Breite (in {}) und – optional – vertikale Ausrichtung (in []) umschließt das Kommando, wiederum mit geschweiften Klammern, den Inhalt der Tabellenzellen. Dort können nun mit `\\` oder `\linebreak` Umbrüche gesetzt werden. Das funktioniert wie im normalen Fließtext:

```latex
\parbox[]{2cm}{...}
```

Wie das nachher aussieht, zeigt folgendes Beispiel mit einer Zelle deren vertikale Ausrichtung mit dem Parameter _c_ zentriert wurde:

```latex
\begin{tabular}{|c|c|}
	\hline
	Blind Text & \parbox{2cm}{Blind \\ Text} \\
	\hline
\end{tabular}
```

{{< picture src="images/latex_tabelle_parbox.png" title="Ergebnis des Beispielcodes" >}}

Neben `c` gibt es noch die in der Tabelle aufgeführten Parameter für die vertikale Ausrichtung:

|Parameter für vertikale Ausrichtung|
|--- |--- |
|t|oben|
|c|zentriert|
|b|unten|

Der Vorteil dieses Vorgehens ist, dass kein zusätzliches Paket geladen werden muss. Der in meinen Augen große Nachteil liegt allerdings darin, dass zwingend eine feste Breite der Zelle – beziehungsweise genauer gesagt, der in die Zelle hineingelegten Box – angegeben werden muss.

## 2. LaTeX-Paket `makecell`

Mit dem Paket [makecell][1] kann man (unter anderem) auch manuelle Zeilenumbrüche in Tabellenzellen setzen und das ohne eine feste Breite angeben zu müssen. Geladen wird das Paket über folgende Befehl in der Präambel:

```latex
\usepackage{makecell}
```

### Zeilenumbrüche einfügen

Dies erlaubt uns nun ebenfalls einzelne Zellen anzupassen. Die Syntax ist dabei relativ einfach. Der Inhalt der Zelle in der manuelle Zeilenumbrüche gesetzt werden sollen, wird mit `\makecell{...}` umschlossen. Im Text der Zelle können dann wieder händisch Zeilenumbrüche gesetzt werden, wie folgendes Beispiel zeigt:

```latex
\begin{tabular}{|c|c|}
   \hline
   a & \makecell{n = 17 \\ Alter: 18-25 \\ 17 Männer} \\
   \hline
   c & d \\
   \hline
\end{tabular}
```

{{< picture src="images/latex_tabelle_umbruch_1.png" title="Ergebnis des Beispielcodes" >}}

### Weitere Optionen: Ausrichtung von Text in Zellen

In diesem Zusammenhang hat `makecell` noch eine weitere praktische Option: Man kann nicht nur die vertikale, sondern auch die horizontale Ausrichtung von Text in Zellen festlegen. Dazu muss man `\makecell` in eckigen Klammern die Parameter für die vertikale `(v)` und / oder horizontale `(h)` Ausrichtung mitgeben: `\makecell[vh]{...}`

|Parameter für horizontale Ausrichtung||
|--- |--- |
|l|linksbündig|
|c|zentriert|
|r|rechtsbündig|

Folgendes Beispiel zeigt, wie der Code für eine Tabelle aussieht, in der der Text in einer Zelle rechtsbündig ausgerichtet werden soll:

```latex
\begin{tabular}{|c|c|}
   \hline
   Blind Text & \makecell[r]{n = 17 \\ Alter: 18-25 \\ 17 Männer} \\
   \hline
   Blind Text & Blind Text \\
   \hline
\end{tabular}
```

{{< picture src="images/latex_tabelle_makecell_ausrichtung.png" title="Ergebnis des Beispielcodes" >}}

 [1]: https://www.ctan.org/pkg/makecell

{{< vgwort "05b86b09fbd64206865c5ab76678b460" >}}