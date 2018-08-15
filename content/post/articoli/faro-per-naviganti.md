---
title: "Un faro per i naviganti"
date: 2018-01-15T11:56:02+02:00
lastmod: 2018-08-15T11:56:02+02:00
draft: false
tags: ["nav", "landmark", "navigazione"]
categories: ["articoli"]
---

Navigare un sito web può essere una gran rottura di scatole per diverse tipologie di utenti.

Eppure basta davvero poco per agevolarle, vediamo come fare.

<!--more-->

In pratica dobbiamo segnalare che una parte della pagina è adibita alla navigazione: di solito questa regione contiene una lista di link.

~~~html
<nav>
  Home
  Shop
  Contatto
</nav>
~~~

Visto? Non è così difficile, eppure delimitando la regione di navigazione del sito agevoliamo diversi utenti.

* Persone **deboli di vista** che fanno uso di uno screen reader: con una combinazione di tasti possono infatti saltare alla sezione di navigazione di una pagina web, evitando loro di doverla cercare o di indovinare quale sia.
* Persone con **difficoltà motorie** che navigano utilizzando solo la tastiera, in modo che possano arrivarci con una combinazione di tasti.
* Persone che interagiscono con il web unicamente **con la propria voce**, per la stessa ragione.
* Motori di ricerca che possono prelevare più facilmente i link da dare in pasto ai propri crawler.

Il 
[tag nav](https://www.w3schools.com/tags/tag_nav.asp)
è uno standard HTML5, perciò perfettamente supportato dai validatori di codice e dalla maggior parte dei browser.



## Cosa può essere indicato come *nav*?

Ecco alcuni elementi che possono essere considerati dei menu di navigazione, per agevolare l'utente:

* Menu secondari fuori da quello principale.
* Sommari (*tables of content*).
* Widget di paginazione, come quelli in fondo alla pagina principale di questo sito.

{{% notice note "Nota bene" %}}
I menu di secondo livello non devono essere racchiusi a loro volta in un tag *nav*.
{{% /notice %}}
