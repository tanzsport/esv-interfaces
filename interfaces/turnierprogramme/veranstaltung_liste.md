---
layout: page
title: Veranstaltung (Liste)
tagline: v1.6.0

---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/veranstaltungen

### Rückgabe ###
* Array über zukünftige Veranstaltungen, auf die der Benutzer Zugriff hat 
  * Veranstaltungs-ID [id]
  * Datum von [datumVon]
  * Datum bis [datumBis] 
  * Ort [ort]
  * Titel (optional) [titel]

#### Beispiel ####

<pre class="line-numbers"><code class="language-javascript">[
    {
        "id": 2001,
        "datumVon": "2014-04-18T00:00:00+0200",
        "datumBis": "2014-04-21T00:00:00+0200",
        "ort": "Berlin",
        "titel": "Blaues Band der Spree"
    },
    {
        "id": 2002,
        "datumVon": "2014-06-13T00:00:00+0200",
        "datumBis": "2014-06-14T00:00:00+0200",
        "ort": "Berlin",
        "titel": "Summer Dance Festival"
    }
]</code></pre>

* * *

[zurück](javascript:history.go(-1))