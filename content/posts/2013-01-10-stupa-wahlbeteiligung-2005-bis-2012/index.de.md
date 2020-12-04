---
title: Studierendenparlament Universität Trier – Wahlbeteiligung 2005 bis 2012
author: Christian Humm
date: 2013-01-10T20:30:08+00:00
url: /2013/01/10/stupa-wahlbeteiligung-2005-bis-2012/
categories:
  - Politik
tags:
  - stupa
  - trier
  - uni trier
toc: false
cover: "images/stupa_trier_header.jpg"
---
Aus Anlass der kürzlichen Wahlen zum [Studierendenparlament (StuPa) an der Universität Trier][1] habe ich mir mal den Spaß gemacht und ein kleines Diagramm zur Entwicklung der Wahlbeteiligung gemacht. Leider sind [online nur Daten bis 2005][2] vorhanden, es wäre natürlich wesentlich interessanter auch weiter zurückliegende Wahlen berücksichtigen zu können.

<!--more-->

{{< highcharts-custom chart="stupa2012" >}}
    chart: {
        type: 'line'
    },
    title: {
        text: 'Wahlbeteiligung 2005 bis 2012'
    },
    subtitle: {
        text: 'Wahlen zum Studierendenparlament an der Universität Trier'
    },
    xAxis: {
        gridLineWidth: 1,
        categories: ['2005', '2006', '2008', '2009', '2010', '2011', '2012']
    },
    yAxis: [{
        title: {
            text: 'Wahlbeteiligung (%)'
        }
        // min: 0
    }, { //--- Secondary yAxis
    title: {
        text: 'Abgegebene Stimmen',
    },
    opposite: true,
    min: 0
    }],
    plotOptions: {
      line: {
          dataLabels: {
              enabled: true
          },
          enableMouseTracking: false
      }
    },
    series: [{
        yAxis: 0,
        name: 'Wahlbeteiligung (%)',
        data: [14.94, 11.84, 11.8, 14.5, 9.65, 10.13, 10.94]
    }, {
        yAxis: 1,
        name: 'Abgegebene Stimmen (Tsd.)',
        data: [1969, 1591, 1655, 2034, 1397, 1506, 1633]
    }]
{{< /highcharts-custom >}}

 [1]: http://stupa.uni-trier.de/ "Homepage des Studierendenparlaments an der Uni Trier"
 [2]: http://www.uni-trier.de/index.php?id=20154
