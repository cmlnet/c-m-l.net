---
title: 'R: YouTube Kommentare mit vosonSML auslesen'
author: Christian Humm
date: 2020-02-13T17:00:00+00:00
url: /2020/02/13/r-youtube-kommentare-mit-vosonsml-auslesen/
categories:
  - HowTo
  - IT
  - Wissenschaft
tags:
  - R
  - YouTube
cover: cover.png
vgwort: 89d72ce261e94496b9064c2ac8df2ed3
---
YouTube ist eine enorm populäre Seite und entsprechend interessant auch für die Forschung. Egal ob es dabei um Wissenschaftskommunikation, die Erforschung von Verschwörungstheorien oder Jugendkultur geht, nicht nur die Videos selbst sind relevant, sondern auch die Kommentarspalte unter selbigen.

In den Kommentaren reagieren die Nutzer\*innen auf die Videos, interagieren und diskutieren mit deren Macher\*innen und anderen User*innen. Doch um YouTube Kommentare zu analysieren, muss man sie erst einmal sichern.

Hierfür eignet sich [R][1] und das Paket [vosonSML][2] bestens. Wie man damit YouTube Kommentare sichert, zeige ich euch im Folgenden.

<!--more-->

## YouTube API Key besorgen

Als erstes braucht ihr einen YouTube API Key. Diesen bekommt ihr mit folgenden Schritten:

  1. [Google API Bibliothek aufrufen][3]
  2. Neues Projekt erstellen
    (Dazu oben links, neben dem Logo auf „Projekt auswählen“ klicken und dann auf „Neues Projekt“)
  3. YouTube Data API v3 aus der API-Liste auswählen und auf der folgenden Seite aktivieren
  4. In der Linken Navigationsleiste auf „Anmeldedaten“ klicken
  5. Auf der nächsten Seite dann über „+ Anmeldedaten erstellen“ einen neuen API-Schlüssel erstellen

## R-Pakete installieren und laden

Dann können wir die nötigen Pakete für R installieren und laden – eine lauffähige R-Umgebung ist dabei natürlich Voraussetzung:

```r
install.packages("magrittr") # Damit nachher %>% benutzt werden kann
library(magrittr)

install.packages("vosonSML")
library(vosonSML)
```

## YouTube Kommentare auslesen ...

Danach können die Kommentare ausgelesen werden:

```r
# ... muss durch den oben erstellten YouTube API Key ersetzt werden
myYoutubeAPIKey <- "..."

# Extraktion der Video-IDs aus YouTube URLs
myYoutubeVideoIds <- GetYoutubeVideoIDs(c("https://www.youtube.com/watch?v=X8RUxm5xmxA","https://www.youtube.com/watch?v=ENI84bjZCBo"))

# Authentifizierung und Download der 100 ersten Kommentare plus Antworten auf diese
# Die Zahl der Kommentare kann über den Paramenter maxComments angepasst werden
youtubeData <- Authenticate("youtube", apiKey = myYoutubeAPIKey) %>%
  Collect(videoIDs = myYoutubeVideoIds, maxComments = 100)
```

## ... und sichern

Zum Schluss können wir die Kommentare dann noch zur späteren Verwendung in einer CSV-Datei sichern:

```r
write.csv(youtubeData, "comments.csv")
```

 [1]: https://www.r-project.org/
 [2]: http://vosonlab.net/SocialMediaLab
 [3]: https://console.developers.google.com/apis/library
