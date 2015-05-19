---
layout: page
title: Ergebnisse
tagline: v1.6.2

---
{% include JB/setup %}

### HTTP-Verb ###
	POST

### URL ###
	/api/v1/ergebnis/{turnierId}

#### Parameter ####

* **turnierId**: Turnier-ID

### Header ###
	X-DTV-Pruefsumme: {pruefsumme}

Die Prüfsumme besteht aus den ersten 6 Stellen des SHA-1-Hashs des JSON-Datenstreams.

### Inhalt ###
Die Ergebnisse eines Turniers können mehrfach hochgeladen werden, z.B. im Live-Modus nach jeder Runde. Dabei können sich auch die Inhalte des übergreifenden Berichtes verändern. 

Erst nach Turnierende muss/darf die Prüfsumme enthalten sein. Dies ist für das ESV-System das Signal, das die Daten komplett sind (Turnier beendet). Danach können die Ergebnisse noch weitere 4 Stunden für Korrekturen erneut hochgeladen werden. Nach 4 Stunden lässt das ESV-System ein Hochladen nicht mehr zu.

Das Hochladen von Zwischenergebnissen (auch nur der reinen Startliste) ist möglich. Solange das Turnier noch läuft sind Daten wie: Endzeit, Ergebnis und Wertung (für noch nicht ausgeschiedene Starter) optional und Rundenablauf nur teilvollständig. Das Starter-Array muss trotzdem bei jedem Upload komplett (alle Starter inkl. abwesende) hochgeladen werden. Jeder Upload überschreibt immer den vorherigen komplett. 

Bei Startern eines anderen Staates, die keine Paar-ID bzw. Partner/in-ID haben, sind nur die Namen eingetragen, evtl. der Clubname, aber auch der Staat.

* Tänze (Array, max. 10 Tänze gem. [Schlüsselverzeichnis](../../schluesselverzeichnis.html#tnze)) [taenze]
* WR (Array, WR des Turniers) [wr]
  * Personen-ID (für DTV-WR Pflicht, für Ersatz-WR optional, für Ausländer NULL) [id]
  * Vorname [vorname]
  * Nachname [nachname]
  * Club [club]
	* Club-Name (optional für Ausländer) [name]
	* LTV-Name (für Ausländer NULL) [ltv]
  * Staat [staat]
* Turnierleiter (Array, min. 1 Element) [tl]
  * Analog WR-Einzelement (ID Pflicht, Ausnahmen auf Veranstaltungsebene konfiguriert)
* Beisitzer (Array, min. 1 Element) [bs]
  * Analog WR-Einzelement (ID Pflicht, Ausnahmen auf Veranstaltungsebene konfiguriert)
* Chairman (optional) (Array) [ch]
  * Analog WR-Einzelement
* Vorkommnisse (optional) [vorkommnisse]
* Beginnzeit (ISO8601) [beginn]
* Endzeit (ISO8601) [ende]
* Array Rundenablauf (NULL für Upload von nur-Startlisten) [ablauf]
  * Schlüsselwerte gem. [Schlüsselverzeichnis](../../schluesselverzeichnis.html#tnze): 1,R,2,3,4,5,6,7,8,9,F (Redance=R, bei 1.VR=1A, bei 2.VR=1B, bei Formations A-Finale=FA, bei B-Finale=FB) [runde]
  * Wertungstyp gem. [Schlüsselverzeichnis](../../schluesselverzeichnis.html#tnze): (Kreuze{0..1}=K, Mannschaftspunkte{1..1,5..2..2,5..3}=M, Finalplätze{1..x}=P, FormationswertungKreuze=FK, FormationswertungPlätze=FP, JMD-WertungenKreuze=JK, JMD-WertungenPlätze=JP, JudgingSystem2.x=JS) [typ]
* kombiniert mit Turnier-ID (optional) [kombiniertMit]
* Zuschauerzahl [zuschauer] 
* Array Starter [starter]
  * Starter-ID (Pflicht bei DTV-  und Grenzverkehrs-Paaren, bei WDSF-Paaren optional) [id]
  * Startnummer [startNr]
  * Personen (Array, enthält bei Teamwettbewerben alle Starter, die tatsächlich getanzt haben)
	* Personen-ID (Pflicht bei DTV-  und Grenzverkehrs-Paaren, bei WDSF-Paaren optional) [id]
	* Vorname [vorname]
	* Nachname [nachname]
	* WDSF-MIN (optional, sofern vorliegend; bei WDSF-Paaren Pflicht) [wdsfMin]
  * Staat [staat]
  * Status (teilgenommen = 1, fehlt entschuldigt = 2, fehlt unentschuldigt = 3) [status]
  * Meldungstyp (regulär = 1, Nachmeldung = 2, Nachmeldung, Sieger = 3, Nachmeldung, Aufsteiger = 4) [meldungsTyp]
  * Anzahl Sterne (gesetzte Paare) [sterne]
  * Ergebnis (NULL bei Status 2 oder 3 oder beim Upload von nur-Startliste) [ergebnis]
	* Platz-Gesamtergebnis Von [platzGesamtVon]
	* Platz-Gesamtergebnis Bis [platzGesamtBis]
	* Platz-Eigenes-Turnier Von  (z.B. nach Anhang 5, NULL wenn nicht benötigt) [platzTurnierVon]
	* Platz-Eigenes-Turnier Bis  (z.B. nach Anhang 5, NULL wenn nicht benötigt) [platzTurnierBis]
	* Punkte [punkte]
	* Platzierungen gesamt (zur Überprüfung in der DB, Adminalarm bei Abweichung) [platzierungenGesamt]
	* Punkte gesamt (zur Überprüfung in der DB, Adminalarm bei Abweichung) [punkteGesamt]
	* Aufstieg (0 = nein, 1 = ja, 2 = ja, durch Beschluss) [aufstieg]
	* Flag Laufzettel (Starter hat manuell bearbeitete Aufstiegdaten) [laufzettel]
	* Flag Verwarnung/Disqualifikation (0 = keine, 1 = Verwarnt Schrittbegrenzung, 2 = Disqualifiziert Schrittbegrenzung, 3 = gewöhnliche Disqualifikation) [vd]
      Das Verwarnungsflag darf nur >0 gesetzt werden, wenn die Verwarnung oder Disqualifikation innerhalb dieses Turnieres erfolgt ist. Dabei ist zu beachten, dass es für Paare möglich ist, innerhalb eines Turnieres in einer Runde erst verwarnt und in einer späteren Runde disqualifiziert zu werden (in diesem Fall wird vd=2 übertragen).
  * Wertung (Array mit N = Anzahl Runden Elementen; nicht getanzte Runden werden als NULL übertragen, Runden nach Ausscheiden werden gar nicht übertragen; werden Tänze in der jeweiligen Runde nicht getanzt, ist das jeweilige Wertungselement mit NULL anzugeben) [wertung] 
	* Vorrundenwertung (nur Kreuz+Mannschaftspunkt-Wertungen)
	  * Array WR
		* Array Tänze+1
		  * Tänze 1-x: Float für Wertung (Einzelkreuze, sonst NULL, nicht getanzte Tänze der Runde ebenfalls NULL)
		  * Tänze+1: Float Summe 
	  * Summe Wertungen über alle Tänze und alle WR
	* JudgingSystem2.x: Summe Float
	* Endrundenwertung (nur Final-Platz-Wertungen, bei Mannschaft wird Struktur der Vorrundenwertung verwendet)
	  * Array Tänze
		* Array WR+2
		  * WR1-x: Non-signed Byte für Wertung
		  * WR+1: Platzziffer
		  * WR+2: Platzziffer Summe
* Array Endrundentabelle (optional, nur bei Plätzewertungen P, FP, JP, Reihenfolge aus Rundenablauf, nur bei B/A-Finals relevant, vor Turnierende NULL) [endrundentabellen]
	* Array Tänze
	  * Array über Endrundenstarter (Zeilen im heute gedruckten Dokument)
		* Array über Plätze (Spalten im heute gedruckten Dokument)
		  * „Tabellenzelle“ (solange in Ausrechnung benötigt; NULL wenn Ausrechnung in früherer Spalte beendet)
			* Anzahl [anzahl]
			* Summe (optional, sonst NULL) [summe]
* Array Skatingtabelle (Reihenfolge aus Rundenablauf, nur bei B/A-Finals relevant, vor Turnierende leeres Array; sofern kein Skating in der Runde angewandt ist das jeweilige Element NULL) [skatingtabellen]
	* Skating Regel 10 [regel10]
	  * Array über Endrundenstarter
		* Array über Plätze
		  * „Tabellenzelle“ (wenn in Ausrechnung benötigt, sonst NULL)
			* Anzahl [anzahl]
			* Summe (optional, sonst NULL) [summe]
		* Platz (sofern in Regel 10 bestimmt, sonst NULL)
	* Skating Regel 11 (optional) [regel11]
	  * Array über Endrundenstarter
		* Array über Plätze
		  * „Tabellenzelle“ (wenn in Ausrechnung benötigt, sonst NULL)
			* Anzahl [anzahl]
			* Summe (optional, sonst NULL) [summe]
		  * Platz (sofern in Regel 11 bestimmt, sonst NULL)


#### Beispiele ####

##### Beispiel 1 #####

*Jeweils nur wenigen Beispiel-Elementen in Arrays - vollständiges Beispiel siehe Download!*

<pre class="line-numbers"><code class="language-javascript">{
    "taenze": [
        "CC",
        "RU",
        "JV"
    ],
    "wr": [
        {
            "id": "DE100004008",
            "vorname": "Maria",
            "nachname": "Schulze",
            "club": {
                "name": "Verein P",
                "ltv": "LTVBerlin"
            },
            "staat": "GER"
        }
    ],
    "tl": [
        {
            "id": "DE100004059",
            "vorname": "Matthias",
            "nachname": "Sprecher",
            "club": {
                "name": "Verein U",
                "ltv": "LTVBerlin"
            },
            "staat": "GER"
        }
    ],
    "bs": [
        {
            "id": "DE100004067",
            "vorname": "Melanie",
            "nachname": "Werner",
            "club": {
                "name": "Verein V",
                "ltv": "LTVBremen"
            },
            "staat": "GER"
        }
    ],
    "ch": [
        {
            "id": "DE100004075",
            "vorname": "Gunther",
            "nachname": "Hechel",
            "club": {
                "name": "Verein W",
                "ltv": "LTVBerlin"
            },
            "staat": "GER"
        }
    ],
    "vorkommnisse": "Bitte keine Romane schreiben\u2026",
    "beginn": "2014-06-14T10:15:00+0200",
    "ende": "2014-06-14T13:00:00+0200",
    "ablauf": [
        {
            "runde": 1,
            "typ": "K"
        }
    ],
    "kombiniertMit": null,
    "zuschauer": 300,
    "starter": [
        {
            "id": 4002,
            "startNr": 573,
            "personen": [
                {
                    "id": "DE100000053",
                    "vorname": "Alexander",
                    "nachname": "Schreiner",
                    "wdsfMin": null
                },
                {
                    "id": "DE100000061",
                    "vorname": "Anna",
                    "nachname": "Denz",
                    "wdsfMin": null
                }
            ],
            "staat": "GER",
            "status": 1,
            "meldungsTyp": 1,
            "sterne": 0,
            "ergebnis": {
                "platzGesamtVon": 4,
                "platzGesamtBis": 4,
                "platzTurnierVon": null,
                "platzTurnierBis": null,
                "punkte": 12,
                "platzierungenGesamt": 1,
                "punkteGesamt": 17,
                "aufstieg": 0,
                "laufzettel": false,
                "vd": 0
            },
            "wertung": [
                [
                    [
                        null,
                        null,
                        null,
                        3
                    ],
                    [
                        null,
                        null,
                        null,
                        3
                    ],
                    [
                        null,
                        null,
                        null,
                        2
                    ],
                    [
                        null,
                        null,
                        null,
                        3
                    ],
                    [
                        null,
                        null,
                        null,
                        3
                    ],
                    14
                ],
                [
                    [
                        null,
                        null,
                        null,
                        3
                    ],
                    [
                        null,
                        null,
                        null,
                        0
                    ],
                    [
                        null,
                        null,
                        null,
                        2
                    ],
                    [
                        null,
                        null,
                        null,
                        3
                    ],
                    [
                        null,
                        null,
                        null,
                        2
                    ],
                    10
                ],
                [
                    [
                        4,
                        4,
                        4,
                        3,
                        2,
                        5
                    ],
                    [
                        4,
                        4,
                        4,
                        4,
                        3,
                        4
                    ],
                    [
                        4,
                        4,
                        4,
                        3,
                        3,
                        4
                    ],
                    13
                ]
            ]
        },
        {
            "id": 4018,
            "startNr": 589,
            "personen": [
                {
                    "id": "DE100010032",
                    "vorname": "Lars",
                    "nachname": "Larsen",
                    "wdsfMin": 70003
                },
                {
                    "id": "DE100010045",
                    "vorname": "Amalia",
                    "nachname": "Formand",
                    "wdsfMin": ""
                }
            ],
            "staat": "DEN",
            "status": 3,
            "meldungsTyp": 1,
            "sterne": 0,
            "ergebnis": null,
            "wertung": null
        }
    ],
    "endrundentabellen": [
        [
            [
                [
                    {
                        "anzahl": 0,
                        "summe": null
                    },
                    {
                        "anzahl": 1,
                        "summe": null
                    },
                    {
                        "anzahl": 2,
                        "summe": null
                    },
                    {
                        "anzahl": 5,
                        "summe": null
                    },
                    null,
                    null
                ]
            ]
        ]
    ],
    "skatingtabellen": null
}</code></pre>

Downloads: [JSON](../../examples/ergebnis1.json) - [Startliste mit Ergebnis](../../examples/startliste1.pdf) - [Wertungstabelle gesamt](../../examples/gesamt1.pdf) - [Wertungstabelle Endrunde](../../examples/endrunde1.pdf)

##### Beispiel 2 #####

*Nur Skatingtabelle*

<pre class="line-numbers"><code class="language-javascript">{
	"skatingtabellen": [
		{
			"regel10": [
				// start-nr. 55
				[
					// ausrechnung
					[
						null, null, null
					],
					// platz
					null
				],
				// start-nr. 56
				[
					// ausrechnung
					[
						null, { "anzahl": 2, "summe": 4 }, null
					],
					// platz
					null
				],
				// start-nr. 57
				[
					// ausrechnung
					[
						null, { "anzahl": 2, "summe": 4 }, null
					],
					// platz
					null
				]
			],
			"regel11": [
				// start-nr. 55
				[
					// ausrechnung
					[
						null, null, null
					],
					// platz
					null
				],
				// start-nr. 56
				[
					// ausrechnung
					[
						null, { "anzahl": 8, "summe": null }, null
					],
					// platz
					3
				],
				// start-nr. 57
				[
					// ausrechnung
					[
						null, { "anzahl": 12, "summe": null }, null
					],
					// platz
					2
				]
			]
		}
	]
}</code></pre>

Downloads: [JSON](../../examples/ergebnis2.json) - [Wertungstabellen Endrunde und Skating](../../examples/tabellen2.pdf)

### Rückgabe ###

Daten erfolgreich angenommen, bzw. Informationen über mögliche Fehler (z.B. geschlossen, etc). Siehe [API-Response](../../api_response.html).

* * *

[zurück](javascript:history.go(-1))