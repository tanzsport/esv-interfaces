---
layout: page
title: Digitale WR-Zettel
tagline: v1.6.1

---
{% include JB/setup %}

### HTTP-Verb ###
	POST

### URL ###
	/api/v1/wrzetteldigi/{turnierId}/{runde}

#### Parameter ####

* **turnierId**: Turnier-ID
* **runde**: Runde gem. Rundenablauf im Ergebnis-Upload

### Inhalt ###

Bei Formations/JMD-Wertungen läuft das Wertungsarray immer über 5/4 virtuelle Tänze (Tanz 1-4/3: Wertungsgebiete Punkte 0-10, Tanz 5/4: Kreuz oder Platz).* Array über alle WR (in der Reihenfolge wie im Ergebnisupload; das Element ist NULL, wenn die Wertungen nicht vollständig digital erfasst wurden, z.B. wenn teilweise oder vollständig auf Papier gewertet wurde)  * Kreuzvorgabe von (bei Finale NULL) [kreuzvorgabeVon]  * Kreuzvorgabe bis (bei Finale NULL) [kreuzvorgabeBis]  * Array über Starter [starter]	* Startnummer [startNr]
	* Array über Tänze (bzw. Wertungsgebiete bei Formation oder JMD) [wertungen]	  * Wertung (Float oder „L“ für Lift, NULL, falls dieser Tanz in der Runde nicht getanzt wurde) 	  * Float Summe Wertung (NULL bei Platzwertung) [summe]  * Unterschrift (Base64-kodiertes PNG-Bild 1bit, max. 400*200 Pixel) [unterschrift]

* * *

[zurück](javascript:history.go(-1))