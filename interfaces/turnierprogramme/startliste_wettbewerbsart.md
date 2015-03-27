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
Wie [Startliste für Veranstaltung](startliste_veranstaltung.html), jedoch ohne die Felder *Titel*, *Vorname*, *Nachname*, *Geschlecht* im Starter-Array. Die globalen Felder [status] und [nachmeldungen] sind NULL.

* * *

[zurück](javascript:history.go(-1))