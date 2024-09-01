---
title: Frauenanteil in deutschen politischen Talkshows
author: Christian Humm
date: 2013-02-05T10:14:54+00:00
url: /2013/02/05/frauenanteil-in-deutschen-politischen-talkshows/
categories:
  - Fernsehen
  - Medien
tags:
  - Anne Will
  - Beckmann
  - Günther Jauch
  - Hart aber fair
  - log in
  - maybrit illner
  - Menschen bei Maischberger
  - Talkshows
toc: false
cover: cover.jpg
featureimagecaption: "Photo: by [Vazha Despotashvili](https://www.pexels.com/@vazha-despotashvili-732747?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels) from [Pexels](https://www.pexels.com/photo/art-studio-georgia-studio-talk-show-2188604/?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels)"
summary: "Dank der #aufschrei-Debatte wird inzwischen auch in den deutschen Polittalks das Thema Sexismus verhandelt. Doch kann man davon aus gehen, dass in den mehr oder weniger gelungenen Sendungen von Jauch, Will, Illner und log in eines fehlen dürfte &#8211; eine kritische Selbstreflektion, etwa über den Frauenanteil unter den eigenen Gästen."
---

Dank der [#aufschrei-Debatte][1] wird inzwischen auch in den deutschen Polittalks das Thema Sexismus verhandelt. Doch kann man davon aus gehen, dass in den mehr oder weniger gelungenen Sendungen von [Jauch][2], [Will][3], [Illner][4] und [log in][5] eines fehlen dürfte &#8211; eine kritische Selbstreflektion, etwa über den Frauenanteil unter den eigenen Gästen.

Dieser ist in allen sechs großen deutschen Polittalks dürftig. Ein Umstand der auch in der Debatte um und in den Untersuchungen über politische Talkshows faktisch keine Rolle spielt.

Bei einer Auswertung aller Folgen, die zwischen September 2011 und September 2012 ausgestrahlt wurden, kommt man je nach Sendung auf einen Frauenanteil unter den Gästen von 20,7% (_maybrit illner_) bis 38,2% (_Menschen bei Maischberger_) und auch das &#8220;innovative&#8221; Format _log in_ schneidet mit 23,8% nicht besser ab:

{{< chart >}}
type: 'bar',
data: {
    datasets: [{
        label: 'weibliche Gäste (%)',
        data: [28.5, 33.67, 30.54, 25.91, 23.75, 20.68, 38.24],
    },
    {
        label: 'männliche Gäste (%)',
        data: [71.5, 66.33, 69.46, 74.09, 76.25, 79.32, 61.76],
    }],
    labels: ['Anne Will', 'Beckmann', 'Günther Jauch', 'hart aber fair', 'log in', 'maybritt illner', 'Menschen bei Maischberger'],
},
options: {
    locale: 'de-DE',
    plugins: {
        title: {
            display: true,
            text: 'Frauen- und Männeranteil unter den Gästen deutscher Polittalks'
        },
        subtitle: {
            display: true,
            text: 'Wahlen zum Studierendenparlament an der Universität Trier'
        },
    },
    scales: {
        y: {
            beginAtZero: true,
            title: {
                display: true,
                text: 'Anteil Gäste (%)'
            },
        },
    },
}
{{< /chart >}}

---
*Cover photo by [Vazha Despotashvili](https://www.pexels.com/@vazha-despotashvili-732747?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels) from [Pexels](https://www.pexels.com/photo/art-studio-georgia-studio-talk-show-2188604/?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels)*

 [1]: http://maedchenmannschaft.net/wie-aufschrei-en/ "Mädchenmannschaft: Wie #aufschreien?"
 [2]: http://daserste.ndr.de/guentherjauch/rueckblick/sexismus113.html "Günther Jauch"
 [3]: http://daserste.ndr.de/annewill/videos/annewill3671.html "Anne Will"
 [4]: http://www.zdf.de/maybrit-illner/Schote-Zote-Herrenwitz-26381644.html "maybrit illner"
 [5]: http://blog.zdf.de/zdflogin/2013/01/29/komplett-mitschnitt-sind-frauen-macho-opfer/ "zdf log in"
