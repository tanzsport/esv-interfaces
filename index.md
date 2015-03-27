---
layout: page
title: ESV-Schnittstellen
tagline: Dokumentation
---
{% include JB/setup %}

# Aktualisierungen #

**25.03.2015**

* Schnittstellendefinitionen auf Version 1.6.0 aktualisiert
  * [Startlisten Veranstaltung](interfaces/turnierprogramme/startliste_veranstaltung.html): Flag Nachmeldeerlaubnis nun Array; Klarstellung zu globalen Parametern in der [Gesamtstartliste nach Wettbewerbsart](interfaces/turnierprogramme/startliste_wettbewerbsart.html) je Wettbewerbsart
  * [Ranglisten](interfaces/turnierprogramme/rangliste.html): Beispielaufruf ohne Stichtag ergänzt
  * [Aufstiegstabellen](interfaces/turnierprogramme/aufstiegstabellen.html): Feld Zielklasse ergänzt
  * neue Schnittstelle: [ausgefallenes Turnier](interfaces/turnierprogramme/ausgefallen.html)
  * Leerzeichen und Punkte aus Konstanten im [Schlüsselverzeichnis](schluesselverzeichnis.html) entfernt (LTVs, Startgruppen, Startklassen, RL-IDs) korrigiert
  * [Ergebnis-Interface](interfaces/turnierprogramme/ergebnis.html) ergänzt um Sterne-Info bei Startern
* Seite über [Zertifizierungsdokumente](dokumente.html) ergänzt

**03.03.2015**

* Wettbewerbsarten und Tänze im [Schlüsselverzeichnis](schluesselverzeichnis.html) korrigiert
* Interface [Ergebnisse](interfaces/turnierprogramme/ergebnis.html) ergänzt
* [API-Responses](api_response.html) ergänzt

**27.02.2015** 

* Startgruppen-Angabe in [Startliste](interfaces/turnierprogramme/startliste_veranstaltung.html) korrigiert (kein Leerzeichen)
* [Umgebungen und Systeme](umgebungen_systeme.html) ergänzt
* [Schlüsselverzeichnis](schluesselverzeichnis.html) ergänzt
* Interface [Ranglisten](interfaces/turnierprogramme/rangliste.html) ergänzt
* Interfaces für Funktionäre ergänzt ([Einzelaufruf](interfaces/turnierprogramme/funktionaer_einzelaufruf.html), [Gesamt-Liste](interfaces/turnierprogramme/funktionaer_liste.html))
* Interface [Aufstiegstabellen](interfaces/turnierprogramme/aufstiegstabellen.html) ergänzt

# Allgemeines #

* [Umgebungen und Systeme](umgebungen_systeme.html)
* [Schlüsselverzeichnis](schluesselverzeichnis.html)
* [API-Responses](api_response.html)
* [Zertifizierungsdokumente](dokumente.html)

# Interfaces #
* Turnierprogramme
  * Veranstaltungen
    * [Liste](interfaces/turnierprogramme/veranstaltung_liste.html)
    * [Einzelaufruf](interfaces/turnierprogramme/veranstaltung_einzelaufruf.html)
  * Startlisten
    * [Veranstaltung](interfaces/turnierprogramme/startliste_veranstaltung.html)
    * [Gesamt nach Wettbewerbsart](interfaces/turnierprogramme/startliste_wettbewerbsart.html)
  * [Ranglisten](interfaces/turnierprogramme/rangliste.html)
  * Funktionäre/Lizenzträger
    * [Einzelaufruf](interfaces/turnierprogramme/funktionaer_einzelaufruf.html)
    * [Gesamt-Liste](interfaces/turnierprogramme/funktionaer_liste.html)
  * [Aufstiegstabellen](interfaces/turnierprogramme/aufstiegstabellen.html)
  * Ergebnisse
    * [Ergebnisse](interfaces/turnierprogramme/ergebnis.html)
    * [ausgefallenes Turnier](interfaces/turnierprogramme/ausgefallen.html)
  * Wertungsrichterzettel
    * Datei-Upload (PDF)
    * digitale WR-Zettel
