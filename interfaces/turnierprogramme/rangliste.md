---
layout: page
title: Ranglisten
tagline: v1.4.1
---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/ranglisten/{stichtag}/{ranglistenId1},{ranglistenId2},…

#### Parameter ####

* **ranglistenIdX**: ID der Rangliste gem. [Schlüsselverzeichnis](../../schluesselverzeichnis.html#ranglisten-ids)
* **stichtag**: Stichtag im Format *ttmmjjjj* (optional)

### Rückgabe ###

* Array aller angeforderten Ranglisten
  * RL-ID [id]  * Stand (Datum der letzten Änderung) [id]  * Array Starter [starter]:	* Starter-ID [id]	* Rang [rang]	  * Rangliste [rl]	  * Platzierung der vorhergehenden DM [dm]	* Array über alle Personen: (nicht bei Gruppen/Formationen, bei Paaren: Herr-ID, Dame-ID,…) [personen] 	  * Personen-ID [id]	  * Titel [titel]	  * Vorname [vorname]	  * Nachname [nachname]	* Club [club]	  * ID [id]	  * Name [name]	  * LTV [ltv]	    * ID [id]	    * Name [name]	* RL-Punkte [punkte]	* Anz. teilgenommene Turniere in der Saison (evtl. verwendbar für die DM-Warnung in Std/Lat) [anzahlTurniere]
#### Beispiel ####

<pre class="line-numbers"><code class="language-javascript">[
    {
        "id": "Hgr-Std",
        "stand": "2014-10-31T00:00:00+0200",
        "starter": [
            {
                "id": 9000,
                "rang": {
                    "rl": 1,
                    "dm": 6
                },
                "personen": [
                    {
                        "id": "DE100100007",
                        "titel": null,
                        "vorname": "Daniel",
                        "nachname": "Radu"
                    },
                    {
                        "id": "DE100100015",
                        "titel": null,
                        "vorname": "Anne",
                        "nachname": "Weber"
                    }
                ],
                "club": {
                    "id": 8001,
                    "name": "Braunschweiger TSC e.V.",
                    "ltv": {
                        "id": 1,
                        "name": "NTV"
                    }
                },
                "punkte": 307,
                "anzahlTurniere": 4
            }
        ]
    }
]</code></pre>

[Komplett-Beispiel](../../examples/ranglisten.json)

* * *

[zurück](javascript:history.go(-1))