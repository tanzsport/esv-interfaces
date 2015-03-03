---
layout: page
title: API-Responses

---
{% include JB/setup %}

### HTTP-Codes ###

-	200 OK-	403 Login inkorrekt-	400 Datenkonstrukt ungültig (Bad request)-	404 Ressource existiert nicht (Ergebnis, Funktionär, Starter etc.)-	601 Token abgelehnt-	602 Veranstaltung bereits hochgeladen und Datensatz geschlossen-	603 Ergebnisupload nach Frist, Turnier wird der nächsten Woche zugerechnet-	604 Ergebnisdatensatz unvollständig (Fehlerdetails im response body)-	605 Starter nicht startberechtigt in angefragter Turnierart-	606 Datenempfang unvollständig-	610 Zugriff zur Sandbox abgelehnt, Turnier-ID des Arbeitssystems verwendet
### Response-Body ###

JSON-Objekt

* Fehlercode (korrespondiert mit HTTP-Ergebnis-Code) [code]
* Fehlermeldung [fehler]
* Detail (optional) [detail]
<pre class="line-numbers"><code class="language-javascript">{
	"code": 601, 
	"fehler": "Token abgelehnt", 
	"detail": null}</code></pre>* * *

[zurück](javascript:history.go(-1))