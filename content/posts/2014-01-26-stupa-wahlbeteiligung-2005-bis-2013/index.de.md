---
title: StuPa Wahlbeteiligung 2005 bis 2013
author: Christian Humm
date: 2014-01-26T16:06:22+00:00
url: /2014/01/26/stupa-wahlbeteiligung-2005-bis-2013/
featuredImage: images/stupa_trier_header.jpg
categories:
  - Politik
tags:
  - stupa
  - trier
  - uni trier
toc: false
cover: cover.jpg
---
Wie zu den Wahlen zum Studierendenparlament der Universität Trier [im letzten Jahr][1] gibt es auch diesmal eine kleine Übersicht zur Entwicklung der Wahlbeteiligung.

<!--more-->

{{< highcharts-custom chart="stupa2013" >}}
    chart: {
        type: 'line'
    },
    title: {
        text: 'Wahlbeteiligung 2005 bis 2013'
    },
    subtitle: {
        text: 'Wahlen zum Studierendenparlament an der Universität Trier'
    },
    xAxis: {
        gridLineWidth: 1,
        categories: ['2005', '2006', '2008', '2009', '2010', '2011', '2012', '2013']
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
        data: [14.94, 11.84, 11.8, 14.5, 9.65, 10.13, 10.94, 12.8]
    }, {
        yAxis: 1,
        name: 'Abgegebene Stimmen (Tsd.)',
        data: [1969, 1591, 1655, 2034, 1397, 1506, 1633, 1907]
    }]
{{< /highcharts-custom >}}

 [1]: http://www.c-m-l.net/2013/01/stupa-wahlbeteiligung-2005-bis-2012/ "StuPa Wahlbeteiligung 2005 bis 2012"
