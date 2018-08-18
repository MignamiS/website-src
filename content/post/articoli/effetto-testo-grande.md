---
title: "Effetto Testo più Grande"
date: 2018-08-15T16:13:40+02:00
lastmod: 2018-08-18T16:13:40+02:00
draft: false
tags: ["heading", "semantica"]
categories: ["articoli"]
---

Ecco una buona ragione per evitare di utilizzare i tag heading per ottenere un effetto di "testo più grande".

Ammettiamolo, ogni tanto abbiamo riciclato un H4 o un H5 per dare al volo uno stile ad un elemento di contorno, oppure per far risaltare un frammento di testo.
Ma perché è una cattiva idea?

<!--more-->

Ebbene è una **pessima** idea.

A livello semantico un *heading* determina un titolo per qualcosa, come ad esempio un capitolo o un settore della pagina.
La gerarchia degli heading è adoperata per indicizzare o navigare la pagina, sfruttandola spesso come "table-of-contents".

Le persone con disabilità si appoggiano a questo *indice dei contenuti* per capire o navigare la pagina web.
Ma anche i motori di ricerca possono trarre beneficio da questo espediente.

Ecco come apparirebbe ad un motore di ricerca una pagina in cui è stato attribuito un H4 per rendere il testo più accattivante:

* Home page | comune di Springfield
	* Informazioni
	* Popolazione
	* Ultime news
	* Venite alla sagra del merluzzo che si terrà giovedì 26 giugno dalle ore 19:30 presso la sala parrocchiale. Cena, tombola e ballo liscio a partire dalle 20:00.
	* Contatti

{{< figure src="/images/elenco-titoli-spriengfield.png" alt="Elenco dei titoli, il titolo fuori luogo è evidenziato" caption="Elenco dei titoli della pagina visti da uno screen reader" >}}

In questo caso, una possibile correzione può essere:

* Home page | comune di Springfield
	* Informazioni
	* Popolazione
	* Ultime news
		* Sagra del merluzzo
	* Contatti





## I tag H1-H6 sono solo per i titoli

Ops è vero, ogni tanto sbaglio anche io...

{{% notice note "Ricorda" %}}
I tag H1-H6 sono solo per i titoli
{{% /notice %}}

Dare il tag di titolo ad un testo per enfatizzarlo è **semanticamente scorretto**, se questo non è effettivamente un titolo.
Esistono altri tag per questo, come `<strong></strong>` e `<em></em>`.

Immaginati sempre che gli heading vadano a formare un *indice dei contenuti* e che debbano essere coerenti con il contenuto della pagina.
Se un elemento stona con lo scopo della pagina, come nell'esempio di prima, è meglio utilizzare un altro tag.
