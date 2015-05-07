---
layout: page
title: Aufstiegstabellen
tagline: v1.6.1

---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/aufstiegstabelle/{wettbewerbsart}/{jahr}

#### Parameter ####

* **wettbewerbsart**: Wettbewerbsart gem. [Schlüsselverzeichnis](../../schluesselverzeichnis.html#wettbewerbsarten)
* **jahr**: Wettkampfjahr

### Rückgabe ###

* Array  * Landesverbände (Array, Landesverbände, für die die Tabelle gültig ist, z.Zt. alle) [ltv]  * Mindest-Punkte (Mindest-Punkte, die zum Erreichen einer Platzierung erforderlich sind) [minPunkte]  * Tabellen (Array) [tabellen]	* Startgruppen (Array) [startgruppen]	* Turnierart [turnierart]	* Kriterien (Array, aufsteigend sortiert nach Klasse) [kriterien]	  * Klasse (Ist-Klasse des Paares) [klasse]
	  * Ziel-Klasse des Aufstiegs [zielklasse]. Bei Ist-Klasse, die keinen Aufstieg ermöglichen wird NULL zurückgeliefert (z.B. BSW)	  * Punkte (erforderliche Punkte für Aufstieg) [punkte]	  * Plätze (erforderliche Plätze für Aufstieg) [plaetze]	  * Platzierung Bis Platz [bisPlatz]	  * Doppelstart: true/false, kennzeichnet Aufstiege in Startklassen, die nur im Doppelstart genutzt werden können [doppelstart]
#### Beispiel ####

<pre class="line-numbers"><code class="language-javascript">[
	{
		"ltv": ["LTVB", "TBW", "LTVBerlin", "..."],
		"minPunkte": 2,
		"tabellen": [
			{
				"startgruppen": ["KinI", "KinII"],
				"turnierart": "Std",
				"kriterien": [
					{
						"klasse": "BSW",
						"zielklasse": null,
						"punkte": 25,
						"plaetze": 7,
						"bisPlatz": 3,
						"doppelstart": false
					},
					{
						"klasse": "D",
						"zielklasse": "C",
						"punkte": 25,
						"plaetze": 7,
						"bisPlatz": 3,
						"doppelstart": false
					},
					{
						"klasse": "C",
						"zielklasse": "B",
						"punkte": 30,
						"plaetze": 7,
						"bisPlatz": 3,
						"doppelstart": true
					}
				]
			}
		]
	}
]</code></pre>

[Komplett-Beispiel](../../examples/aufstiegstabelle.json)

* * *

[zurück](javascript:history.go(-1))