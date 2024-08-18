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
summary: "Aus Anlass der kürzlichen Wahlen zum Studierendenparlament (StuPa) an der Universität Trier habe ich mir mal den Spaß gemacht und ein kleines Diagramm zur Entwicklung der Wahlbeteiligung gemacht. Leider sind online nur Daten bis 2005 vorhanden, es wäre natürlich wesentlich interessanter auch weiter zurückliegende Wahlen berücksichtigen zu können."
---
Aus Anlass der kürzlichen Wahlen zum [Studierendenparlament (StuPa) an der Universität Trier][1] habe ich mir mal den Spaß gemacht und ein kleines Diagramm zur Entwicklung der Wahlbeteiligung gemacht. Leider sind [online nur Daten bis 2005][2] vorhanden, es wäre natürlich wesentlich interessanter auch weiter zurückliegende Wahlen berücksichtigen zu können.

{{< chart >}}
type: 'bar',
data: {
    datasets: [{
        label: 'Wahlbeteiligung (%)',
        type: 'bar',
        data: [14.94, 11.84, 11.8, 14.5, 9.65, 10.13, 10.94, 12.8],
        yAxisID: 'A',
    },
    {
        label: 'Abgegebene Stimmen (Tsd.)',
        type: 'line',
        data: [1969, 1591, 1655, 2034, 1397, 1506, 1633, 1907],
        yAxisID: 'B',
    }],
    labels: ['2005', '2006', '2008', '2009', '2010', '2011', '2012', '2013'],
},
options: {
    locale: 'de-DE',
    plugins: {
        title: {
            display: true,
            text: 'Wahlbeteiligung 2005 bis 2012'
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

 [1]: http://stupa.uni-trier.de/ "Homepage des Studierendenparlaments an der Uni Trier"
 [2]: http://www.uni-trier.de/index.php?id=20154
