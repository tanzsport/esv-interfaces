---
layout: page
title: PDF WR-Zettel
tagline: v1.6.2

---
{% include JB/setup %}

### HTTP-Verb ###
	POST

### URL ###
	/api/v1/wrzettelpdf/{turnierId}

#### Parameter ####

* **turnierId**: Turnier-ID

### Content-Type ###

	multipart/form-data


### Inhalt ###
Der Multipart-Request-Body enthält beliebig viele PDF-Dateien. Der Name der Parts kann frei gewählt werden:

	Content-Type: multipart/form-data; boundary=----Boundary
	
	----Boundary	Content-Disposition: form-data; name="a"; filename="WRZettel1.pdf" Content-Type: application/pdf	
	----Boundary	Content-Disposition: form-data; name="b"; filename="WRZettel2.pdf" Content-Type: application/pdf

### Rückgabe ###
Response-Objekt und HTTP-Ergebnis-Code

* * *

[zurück](javascript:history.go(-1))