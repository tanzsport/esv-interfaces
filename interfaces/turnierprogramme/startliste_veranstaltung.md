---
layout: page
title: Startliste (Veranstaltung)
tagline: v1.6.0

---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/startliste/veranstaltung/{veranstaltungsId}

#### Parameter ####

* **veranstaltungsId**: ID der Veranstaltung gem. [Veranstaltungsliste](veranstaltung_liste.html)

### Rückgabe ###
* Gültigkeits-Flag für Meldestand (0 = Turniermeldungen noch nicht gestartet, 1 = Meldestand noch nicht final, 2 = Meldestand final) [status]; NULL in Gesamt-Starterliste
* Array Nachmeldungen möglich: Liste der Turnier-IDs mit Nachmeldeerlaubnis [nachmeldungen]; NULL in Gesamt-Starterliste
* Array Starter [starter]
  * Starter-ID [id]
  * Team (optional, nur bei Formations-, Small-Group- und Mannschaftswettbewerben) [team]
    * Team-Name (sofern vorhanden, z.B. bei Gruppen+Formationen) [name]
    * Team-Kapitän (sofern vorhanden, z.B. bei Gruppen+Formationen) [kapitaen]
    * Team-Trainer (sofern vorhanden, z.B. bei Gruppen+Formationen) [trainer]
  * Personen (Array, enthält bei Teamwettbewerben alle Tänzer inkl. Ersatztänzer) [personen]
    * Personen-ID (DTV-Nummer) [id]
    * Titel (nur bei Einzelaufruf Veranstaltung, [sonst NULL](startliste_wettbewerbsart.html)) [titel] 	* Vorname (nur bei Einzelaufruf Veranstaltung, [sonst NULL](startliste_wettbewerbsart.html)) [vorname]	* Nachname (nur bei Einzelaufruf Veranstaltung, [sonst NULL](startliste_wettbewerbsart.html)) [nachname]	* Geschlecht (nur bei Einzelaufruf Veranstaltung, [sonst NULL](startliste_wettbewerbsart.html)) [geschlecht]	* WDSF-MIN (optional, sofern vorhanden) [wdsfMin]	* Nationalität (3-Buchst.-Code) [nationalitaet]
  * Club (bei deutschen Paaren Pflicht, sonst optional) [verein]	* Club-ID [id]	* Club-Name [name]	* LTV (bei deutschen Paaren Pflicht, sonst optional) [ltv]	  * LTV-ID [id]	  * LTV-Name [name]  * Staat (Staat, für den der Starter an den Start geht) [staat]  * Meldungen (Array, nicht vorhanden bei Aufruf der Gesamt-Starterliste für eine Wettbewerbsart) [meldungen]	* Turnier-ID (nur die IDs der Turniere der aufgerufenen Veranstaltung) [turnierId]	* Flag Meldung (Meldung = true, Abmeldung = false) [meldung]	* Datum der Meldebestätigung (durch Verein) [bestaetigt]	* Startnummer (optional – wird erst später für Ligaturniere relevant sein wie JMD und Formation) [startNr]	* Flag Startsperre (true/false) [startsperre]
  * Array Startbuch turnierartweise (optional, nur Einzelwettbewerbe St/Lat und JMD, nur Turnierarten für die ein elektronisches Startbuch vorliegt, in der Übergangszeit ggf. komplett leer) [startbuch]	* Turnierart [turnierart]	* Startgruppe [startgruppe]	* Ist-Startliga (optional, nur Formationswettbewerbe St/Lat und JMD) [startliga]	* Ist-Startklasse (z.B. BSW, D, C,B,A,S,PD) (optional, nur bei Einzelwettbewerben St/Lat und JMD) [startklasse]	* Ziel-Startklasse (C,B,…, NULL für BSW/S/PD/ausländische-Paare/alle Doppelstartpaare, die nicht weiter aufsteigen können, d.h. „kein Aufstieg möglich bei diesem Turnier für dieses Paar“; optional, nur bei Einzelwettbewerben St/Lat, ggf. später Einzelwettbewerbe JMD) [naechsteStartklasse]	* Punkte (optional, nur bei Einzelwettbewerben St/Lat, ggf. später Einzelwettbewerbe JMD) [punkte]	  * Ist [ist]	  * Ziel [ziel]	* Platzierungen (optional, nur bei Einzelwettbewerben St/Lat, ggf. später Einzelwettbewerbe JMD) [platzierungen]	  * Ist [ist]	  * Ziel [ziel]	* Regeln (optional, nur bei Einzelwettbewerben St/Lat, ggf. später Einzelwettbewerbe JMD) [regeln]	  * Mindestpunkte [minPunkte]	  * Platzierung bis Platz (einschließlich) [platzierungBis]	* Flags [flags]	  * Laufzetteldruck da Aufstiegschance am Wochenende (optional, nur bei Einzelwettbewerben St/Lat, ggf. später Einzelwettbewerbe JMD) [laufzettel]	  * Verwarnt wg. Figurenbegrenzung (nur Einzelwettbewerbe St/Lat) [verwarnungSchrittbegrenzung]

#### Beispiel ####

<pre class="line-numbers"><code class="language-javascript">{
	"status": 1,
	"nachmeldungen": [],
    "starter": [
        {
            "id": 4000,
            "team": null,
            "personen": [
                {
                    "id": "DE100000015",
                    "titel": null,
                    "vorname": "Max",
                    "nachname": "Mustermann",
                    "geschlecht": "m"
                    "wdsfMin": null,
                    "nationalitaet": "GER"
                },
                {
                    "id": "DE100000029",
                    "titel": null,
                    "vorname": "Maria",
                    "nachname": "Musterwoman",
                    "geschlecht": "w"
                    "wdsfMin": null,
                    "nationalitaet": "USA"
                }
            ],
            "club": {
                "id": 7000,
                "name": "Grau-Silber-Schwarz Musterstadt",
                "ltv": {
                    "id": 11,
                    "name": "TNW"
                }
            },
            "staat": "GER",
            "meldungen": [
                {
                    "turnierId": 1234,
                    "meldung": true,
                    "bestaetigt": "2014-11-18T16:08:34+0100",
                    "startNr": null,
                    "startsperre": false
                }
            ],
            "startbuch": [
                {
                    "turnierart": "Lat",
                    "startgruppe": "KinII",
                    "startliga": null,
                    "startklasse": "D",
                    "naechsteStartklasse": "C",
                    "punkte": {
                        "ist": 2,
                        "ziel": 30
                    },
                    "platzierungen": {
                        "ist": 1,
                        "ziel": 7
                    },
                    "regeln": {
                        "minPunkte": 2,
                        "platzierungBis": 3
                    },
                    "flags": {
                        "laufzettel": false,
                        "verwarnungSchrittbegrenzung": false
                    }
                },
                {
                    "turnierart": "Std",
                    "startgruppe": "KinII",
                    "startliga": null,
                    "startklasse": "D",
                    "naechsteStartklasse": "C",
                    "punkte": {
                        "ist": 1,
                        "ziel": 25
                    },
                    "platzierungen": {
                        "ist": 1,
                        "ziel": 7
                    },
                    "regeln": {
                        "minPunkte": 2,
                        "platzierungBis": 3
                    },
                    "flags": {
                        "laufzettel": false,
                        "verwarnungSchrittbegrenzung": false
                    }
                }
            ]
        }
   ]
}</code></pre>

[Komplett-Beispiel](../../examples/startlisten.json)

* * *

[zurück](javascript:history.go(-1))