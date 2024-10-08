---
title: "R: Durchschnittliche Views einen YouTube-Kanals erfassen"
author: Christian Humm
date: 2021-02-18
categories:
  - HowTo
  - IT
  - Wissenschaft
tags:
  - R
  - YouTube
licence: cc-by
toc: true
draft: yes

# Cover picture
cover: cover.png
---

{{< licence name="cc-by" >}}

Um den Erfolg eines Videos bei YouTube einzuschätzen, ist es interessant zu schauen, ob es mehr oder weniger Views generiert als die anderen Videos des Kanals. Die dafür notwendigen durchschnitten Views pro Video lassen sich mit *R* und dem Paket *tuber* einfach ermitteln.

<!--more-->

Vorraussetzung für die Anleitung sind Grundkenntnisse in *R* und eine funktionierte *R*-Installation.

## Pakete installieren

Benötigt werden die Pakte [*tuber*](https://github.com/soodoku/tuber), 

```R
install.package("tuber")
```

## Pakte laden

Danach müssen die Pakete noch in die laufende *R*-Session geladen werden:

```R
library(tuber)
```

## API-Schlüssel für YouTube

Damit *tuber* die nötigen Daten auslesen kann, muss ein API-Schlüssel für YouTube erzeugt werden. 

https://developers.google.com/youtube/v3/getting-started