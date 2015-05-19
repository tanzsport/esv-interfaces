---
layout: page
title: Startliste (Wettbewerbsart)
tagline: v1.6.2

---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/startliste/wettbewerbsart/{wettbewerbsart}

#### Parameter ####

* **wettbewerbsart**: Wettbewerbsart

### Rückgabe ###
Wie [Startliste für Veranstaltung](startliste_veranstaltung.html). Die Felder [titel], [vorname], [nachname], [geschlecht] sind NULL, das Feld [startmeldungen] ist ein leeres Array. Die globalen Felder [status] und [nachmeldungen] sind NULL bzw. leer.

[Komplett-Beispiel](../../examples/startliste_wettbewerbsart.json)

* * *

[zurück](javascript:history.go(-1))