---
layout: page
title: ESV-Schnittstellen
tagline: Dokumentation
---
{% include JB/setup %}

# Aktualisierungen #

**01.04.2016**

* Korrektur [Schlüsselverzeichnis](schluesselverzeichnis.html): Rising Stars Schlüssel ist RS, nicht RSRLT

**19.05.2015**

* Aktualisierung auf Version 1.6.2 inkl. [Dokumenten](dokumente.html)
  * [WR-Zettel PDF](interfaces/turnierprogramme/wrzettel_pdf.html): Details ergänzt
  * [Gesamtstartliste](interfaces/turnierprogramme/startliste_wettbewerbsart.html): globales Feld [nachmeldungen] und Feld [startmeldungen] je Starter sind leere Arrays
  * API-Responses bei schreibenden Zugriffen ergänzt

**07.05.2015**

* Aktualisierung auf Version 1.6.1 inkl. [Dokumenten](dokumente.html)
  * Zusatzinfo [Ergebnisupload](interfaces/turnierprogramme/ergebnis.html) Verwarnungs/Disqualifikations-Flag  * [Schlüsselverzeichnis](schluesselverzeichnis.html) WR-Lizenzen: WR-B getrennt in WR-B-Std und WR-B-Lat  * Angabe, welche Felder in der [Gesamtstartliste](interfaces/turnierprogramme/startliste_wettbewerbsart.html) einer Wettbewerbsart NULL sind  * [Ergebnisupload](interfaces/turnierprogramme/ergebnis.html) und [digitale WR-Zettel](interfaces/turnierprogramme/wrzettel_digi.html): Vorgabe zur Verfahrensweise, wenn Tänze in einer Runde nicht getanzt wurden  * [Digitaler WR-Zettel](interfaces/turnierprogramme/wrzettel_digi.html): Datentyp für Einzelkreuz ist gemischt (Float für Wertung oder „L“ für Lift); Vorgabe zur Verfahrensweise, wenn die Wertungsdaten nicht vollständig digital vorliegen; Feldname für Unterschrift ergänzt  * [Skatingtabelle](interfaces/turnierprogramme/ergebnis.html): Klarstellung zur Übermittlung, falls das Skatingsystem nicht angewandt wurde
* neu: [WR-Zettel PDF](interfaces/turnierprogramme/wrzettel_pdf.html) und [WR-Zettel digital](interfaces/turnierprogramme/wrzettel_digi.html)

**29.04.2015**

* [Startlisten Veranstaltung](interfaces/turnierprogramme/startliste_veranstaltung.html): Fehlerkorrektur im Gesamtbeispiel (keine Startbuchdaten für Grenzverkehrspaare)
* [Startliste Wettbewerbsart](interfaces/turnierprogramme/startliste_wettbewerbsart.html): Erläuterungen erweitert, Gesamtbeispiel ergänzt
* [Ergebnis](interfaces/turnierprogramme/ergebnis.html): Erläuterungen zum Flag Verwarnung/Disqualifikation ergänzt

**10.04.2015**

* [Aufstiegstabellen](interfaces/turnierprogramme/aufstiegstabellen.html): Korrektur Feldname *bisPlatz* im Gesamtbeispiel

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
    * [PDF](interfaces/turnierprogramme/wrzettel_pdf.html)
    * [Digital](interfaces/turnierprogramme/wrzettel_digi.html)
