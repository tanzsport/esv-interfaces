---
layout: page
title: Startliste (Wettbewerbsart)
tagline: v1.6.0

---
{% include JB/setup %}

### HTTP-Verb ###
	GET

### URL ###
	/api/v1/startliste/wettbewerbsart/{wettbewerbsart}

#### Parameter ####

* **wettbewerbsart**: Wettbewerbsart

### Rückgabe ###
Wie [Startliste für Veranstaltung](startliste_veranstaltung.html). Die Felder [titel], [vorname], [nachname], [geschlecht] sind NULL, das Feld [startmeldungen] ist ein leeres Array. Die globalen Felder [status] und [nachmeldungen] sind NULL.

[Komplett-Beispiel](../../examples/startliste_wettbewerbsart.json)

* * *

[zurück](javascript:history.go(-1))