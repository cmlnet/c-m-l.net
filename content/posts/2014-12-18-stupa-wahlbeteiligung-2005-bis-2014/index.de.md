---
title: StuPa Wahlbeteiligung 2005 bis 2014
author: Christian Humm
date: 2014-12-18T09:57:09+00:00
url: /2014/12/18/stupa-wahlbeteiligung-2005-bis-2014/
categories:
  - Politik
tags:
  - stupa
  - trier
  - uni trier
toc: false
cover: cover.jpg
---
Wie jedes Jahr, gibt es auch diesmal zu den [Wahlen zum Studierendenparlament der Universität Trier 2014][1] eine kleine Übersicht zur Entwicklung der Wahlbeteiligung:

<!--more-->

{{< highcharts-custom chart="stupa2014" >}}
    chart: {
        type: 'line'
    },
    title: {
        text: 'Wahlbeteiligung 2005 bis 2014'
    },
    subtitle: {
        text: 'Wahlen zum Studierendenparlament an der Universität Trier'
    },
    xAxis: {
        gridLineWidth: 1,
        categories: ['2005', '2006', '2008', '2009', '2010', '2011', '2012', '2013', '2014']
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
        data: [14.94, 11.84, 11.8, 14.5, 9.65, 10.13, 10.94, 12.8, 10.34]
    }, {
        yAxis: 1,
        name: 'Abgegebene Stimmen (Tsd.)',
        data: [1969, 1591, 1655, 2034, 1397, 1506, 1633, 1907, 1494]
    }]
{{< /highcharts-custom >}}

 [1]: https://www.uni-trier.de/fileadmin/studium/StuPa/Wahlausschuss_2014/Dokumente/Feststellungsbeschluss_2014.pdf
