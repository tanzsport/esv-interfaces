---
layout: page
title: Veranstaltung (Einzelaufruf)
tagline: v1.6.1

---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/turniere/{veranstaltungsId}

#### Parameter ####

* **veranstaltungsId**: ID der Veranstaltung gem. [Veranstaltungsliste](veranstaltung_liste.html)

### Rückgabe ###
* einzelner Veranstaltungsdatensatz 
  * Veranstaltungs-ID [id]
  * Datum von [datumVon]
  * Datum bis [datumBis]
  * Turnierstätte [turnierstaette]
  	* Name [name]
  	* Anschrift (Straße + Nr) [anschrift]
  	* PLZ [plz]
  	* Ort [ort]
  * Veranstalter [veranstalter]
  	* ID [id]
  	* Name [name]
  	* LTV (optional) [ltv]
  	  * ID [id]
  	  * Name [name]
  * Ausrichter [ausrichter]
  	* ID [id]
  	* Name [name]
  	* LTV (optional) [ltv]
  	  * ID [id]
  	  * Name [name]
  	* Kontakt Telefon [kontaktTelefon]
  	* Kontakt E-Mail [kontaktEmail]
  * Titel (optional) [titel]
  * Bemerkungen (Freitext) [bemerkungen]
  * Array Wertungsrichter (optional) [wertungsrichter]
  	* Inhalte wie bei [Einzelaufruf Funktionäre](funktionaer_einzelaufruf.html)
  * Array Funktionäre (TL, BS, CHM; optional) [funktionaere]
    * Inhalte wie bei [Einzelaufruf Funktionäre](funktionaer_einzelaufruf.html)
  * Array Flächen [flaechen]
  	* Flächen-Bezeichnung [id]
  	* Typ (Text: z.B. Parkett, Kunststoff, Stein) [typ]
  	* Länge (in Metern; Kommawert z.B. 10,5; Länge ≥ Breite) [laenge]
  	* Breite(in Metern; Kommawert) [breite]
  * Array Turniere [turniere]
  	* Turnier-ID [id]
  	* Datum von [datumVon]
  	* Datum bis [datumBis]
  	* Startzeit Plan (Zeit, die im Tanzspiegel veröffentlicht wurde) [startzeitPlan]
  	* Startzeit Plan Korrigiert (kann, sofern vom Ausrichter verändert auch im Terminkalender als veränderte Startzeit kenntlich dargestellt werden) [startzeitPlanKorrigiert]
  	* Titel (optional) [titel]
  	* Veranstalter [veranstalter]
  	  * ID [id]
  	  * Name [name]
  	  * LTV (optional) [ltv]
  	  	* ID [id]
  	  	* Name [name]
  	* Ausrichter [ausrichter]
  	  * ID [id]
  	  * Name [name]
  	  * LTV (optional) [ltv]
  	  	* ID [id]
  	  	* Name [name]
  	 * Flächen-ID [flaechenId]
  	 * Wettbewerbsart (z.B. Einzel, Formation, Solo, Duo,…) [wettbewerbsart]
  	 * Turnierform [turnierform]
  	 * Startgruppe [startgruppe]
  	 * Startklasse oder Startliga [startklasseLiga]
  	 * Turnierart [turnierart]
  	 * Zulassung (grenzt die zugelassenen Paare ein, z.B. DTV oder auf einen oder mehrere LTV;) [zulassung]
  	   * Array; mögliche Werte: WDSF, EU, DTV + LTVs
  	 * Wanderpokal: true/false [wanderpokal]
  	 * Turnierrang (numerisch) [turnierrang]
  	 * Flag Aufstiegsturnier (Vergabe von Aufstiegspunkten und –platzierungen ja/nein) [aufstiegsturnier]
  	 * Ranglisten-ID (optional, bei Ranglistenturnieren und ggf. bei DM) [ranglistenId]
  	 * WDSF-Turnier-ID (optional) [wdsfTurnierId]
  	 * Startgebühr in EUR (optional, Zahlwert oder Freitext) [startgebuehr]
  	 * Bemerkungen (Freitext optional) [bemerkungen]
  	 * Array Wertungsrichter (optional) [wertungsrichter]
  	   * Personen-IDs
  	 * Turnierleiter Personen-ID (optional) [turnierleiter]
  	 * Beisitzer Personen-ID (optional) [beisitzer]
  	 * Chairman Personen-ID (optional) [chairman]

#### Beispiel ####

<pre class="line-numbers"><code class="language-javascript">{
	"id": 2001,
	"datumVon": "2014-04-18T00:00:00+0200",
	"datumBis": "2014-04-21T00:00:00+0200",
	"turnierstaette": {
		"name": "Sport- und Freizeitzentrum Siemensstadt",
		"anschrift": "Buolstr. 14",
		"plz": "13629",
		"ort": "Berlin"
	},
	"veranstalter": {
		"id": 8000,
		"name": "Landestanzsportverband Berlin e.V.",
		"ltv": null
	},
	"ausrichter": {
		"id": 9000,
		"name": "Ausrichtergemeinschaft Blaues Band der Spree",
		"ltv": {
			"id": 3
			"name": "LTVBerlin",
		}
	},
	"titel": "Blaues Band der Spree",
	"bemerkungen": null,
	"wertungsrichter": [],
	"funktionaere": [],
	"flaechen": [
		{
			"id": "Fläche 1",
			"typ": "Parkett",
			"laenge": 18.0,
			"breite": 10.0,
		},
		{
			"id": "Fläche 2",
			"typ": "Parkett",
			"laenge": 18.0,
			"breite": 10.0,
		},
		{
			"id": "Fläche 1+2",
			"typ": "Parkett",
			"laenge": 18.0,
			"breite": 20.0,
		},
		{
			"id": "Fläche 4",
			"typ": "Parkett",
			"laenge": 12.0,
			"breite": 9.0,
		}
	],
	"turniere": [
		{
			"id": 10000,
			"datumVon": "2014-04-18T00:00:00+0200",
			"datumBis": "2014-04-18T00:00:00+0200",
			"startzeitPlan": "10:00",
			"startzeitPlanKorrigiert": null,
			"titel": null,
			"veranstalter": {
				"id": 8000,
				"name": "Landestanzsportverband Berlin e.V.",
				"ltv": {
					"id": 3,
					"name": "LTV Berlin"
				}
			},
			"ausrichter": {
				"id": 9000,
				"name": "Ausrichtergemeinschaft Blaues Band der Spree",
				"ltv": {
					"id": 3,
					"name": "LTV Berlin"
				}
			},
			"flaechenId": "Fläche 1",
			"wettbewerbsart": "Einzel",
			"turnierform": "OT",
			"startgruppe": "Hgr",
			"startklasseLiga": "D",
			"turnierart": "Lat",
			"zulassung": [
				"DTV"
			],
			"wanderpokal": false,
			"turnierrang": 1,
			"aufstiegsturnier": true,
			"ranglistenId": null,
			"wdsfTurnierId": null,
			"startgebuehr": "10€ pro Paar für das 1. Turnier, 6€ für jedes weitere Turnier; WDSF-Turniere 25€",
			"bemerkungen": null,
			"wertungsrichter": null,
			"turnierleiter": null,
			"beisitzer": null,
			"chairman": null
		}
	]
}</code></pre>

[Komplett-Beispiel](../../examples/turnierliste.json)

* * *

[zurück](javascript:history.go(-1))