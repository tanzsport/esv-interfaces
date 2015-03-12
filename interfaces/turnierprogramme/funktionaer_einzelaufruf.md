---
layout: page
title: Funktionäre/Lizenzträger (Einzelaufruf)
tagline: v1.5.0

---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/funktionaer/{personenId}

#### Parameter ####

* **personenId**: Personen-ID des Funktionärs bzw. Lizenträgers

### Rückgabe ###

* Personen-ID [id]* WDSF-MIN (optional, sofern verfügbar) [wdsfMin]* alte Lizenznummer (optional) [lizenzNr]* Titel [titel]* Vorname [vorname]* Nachname [nachame]* Club [club]  * ID [id]  * Name [name]  * LTV [ltv]	* ID [id]	* Name [name]* Staat [staat]* Array Lizenzen [lizenzen]	* Lizenz-IDs (Auflistung aller gültigen Funktionärs-Lizenzen)
#### Beispiel ####

<pre class="line-numbers"><code class="language-javascript">{
    "id": "DE100777775",
    "wdsfMin": 1002001,
    "lizenzNr": 12999,
    "titel": null,
    "vorname": "Max",
    "nachname": "Mustermann",
    "club": {
        "id": 8001,
        "name": "OTK Schwarz-Wei\u00df 1922 im SCS Berlin e.V.",
        "ltv": {
            "id": 3,
            "name": "LTV Berlin"
         }
    },
    "staat": "GER",
    "lizenzen": [
        "TL",
        "WR-S-DM-Std",
        "WR-S-DM-Lat"
    ]
}</code></pre>

* * *

[zurück](javascript:history.go(-1))