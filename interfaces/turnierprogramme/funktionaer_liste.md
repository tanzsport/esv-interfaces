---
layout: page
title: Funktionäre/Lizenzträger (Liste)
tagline: v1.6.0

---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/funktionaere 

### Rückgabe ###

* Array von Lizenzträgerdatensätzen analog zum [Einzelaufruf](funktionaer_einzelaufruf.html)
  * Felder titel, vorname, nachname sind NULL

#### Beispiel ####

<pre class="line-numbers"><code class="language-javascript">[
    {
        "id": "DE100777775",
        "wdsfMin": 1002001,
        "lizenzNr": 12999,
        "titel": null,
        "vorname": null,
        "nachname": null,
        "club": {
            "id": 8001,
            "name": "OTK Schwarz-Wei\u00df 1922 im SCS Berlin e.V.",
            "ltv": {
                "id": 3,
                "name": "LTVBerlin"
            }
        },
        "staat": "GER",
        "lizenzen": [
            "TL",
            "WR-S-DM-Std",
            "WR-S-DM-Lat"
        ]
    }
]</code></pre>

[Komplett-Beispiel](../../examples/funktionaere.json)

* * *

[zurück](javascript:history.go(-1))