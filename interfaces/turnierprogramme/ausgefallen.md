---
layout: page
title: Ausgefallenes Turnier
tagline: v1.6.2

---
{% include JB/setup %}

### HTTP-Verb ###
	POST

### URL ###
	/api/v1/ausgefallen/{turnierId}

#### Parameter ####

* **turnierId**: ID des Turniers

### Inhalt ###

* Vorkommnisse (optional) [vorkommnisse]

#### Beispiel ####

<pre class="line-numbers"><code class="language-javascript">{
	"vorkommnisse": "Bitte Text eingeben"
}</code></pre>

### Rückgabe ###
Response-Objekt und HTTP-Ergebnis-Code

* * *

[zurück](javascript:history.go(-1))