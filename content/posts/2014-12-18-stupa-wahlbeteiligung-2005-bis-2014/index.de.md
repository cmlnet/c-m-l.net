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
summary: "Wie jedes Jahr, gibt es auch diesmal zu den Wahlen zum Studierendenparlament der Universität Trier 2014 eine kleine Übersicht zur Entwicklung der Wahlbeteiligung."
---
Wie jedes Jahr, gibt es auch diesmal zu den [Wahlen zum Studierendenparlament der Universität Trier 2014][1] eine kleine Übersicht zur Entwicklung der Wahlbeteiligung:

{{< chart >}}
type: 'bar',
data: {
    datasets: [{
        label: 'Wahlbeteiligung (%)',
        type: 'bar',
        data: [14.94, 11.84, 11.8, 14.5, 9.65, 10.13, 10.94, 12.8, 10.34],
        yAxisID: 'A',
    },
    {
        label: 'Abgegebene Stimmen (Tsd.)',
        type: 'line',
        data: [1969, 1591, 1655, 2034, 1397, 1506, 1633, 1907, 1494],
        yAxisID: 'B',
    }],
    labels: ['2005', '2006', '2008', '2009', '2010', '2011', '2012', '2013', '2014'],
},
options: {
    locale: 'de-DE',
    plugins: {
        title: {
            display: true,
            text: 'Wahlbeteiligung 2005 bis 2014'
        },
        subtitle: {
            display: true,
            text: 'Wahlen zum Studierendenparlament an der Universität Trier'
        },
    },
    scales: {
        A: {
            type: 'linear',
            position: 'left',
            title: {
                display: true,
                text: 'Wahlbeteiligung (%)'
            },
        },
        B: {
            type: 'linear',
            position: 'right',
            title: {
                display: true,
                text: 'Abgegebene Stimmen (Tsd.)'
            },
            // grid line settings
            grid: {
                drawOnChartArea: false, // only want the grid lines for one axis to show up
            },
        },
    },
}
{{< /chart >}}

 [1]: https://www.uni-trier.de/fileadmin/studium/StuPa/Wahlausschuss_2014/Dokumente/Feststellungsbeschluss_2014.pdf
