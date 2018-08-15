---
title: "Titoli O Intestazioni?"
date: 2017-09-29T10:51:12+02:00
lastmod: 2018-08-15T10:51:12+02:00
draft: false
tags: ["title", "heading", "titolo"]
categories: ["articoli"]
---

Questo articolo chiarisce alcuni termini usati dagli addetti ai lavori: *titoli*, *heading*, *title* e *intestazioni*.

<!--more-->

## Titolo della pagina

Il titolo della pagina è mostrato nella scheda del browser ed è definito utilizzando il tag *title* nella *head* del documento:

~~~html
<head>
  ...
  <title>Home page | MioSito.com</title>
</head>
~~~

Il titolo di una pagina è più importante di quanto si creda: gli screen reader lo leggono infatti come prima cosa quando una pagina è caricata, permettendo all'utente con difficoltà **visive** di capire dove si trova.

Anche gli utenti con difficoltà **cognitive** ne traggono vantaggio, perché li aiuta ad orientarsi all'interno del sito.



## Attributo *title*

Da non confondere con il *titolo della pagina*, l'attributo *title* è associato ad un tag e può essere usato per aggiungere informazioni:

~~~html
<a href="..." title="Questo link si apre in una nuova finestra" ...
~~~

Ci si riferisce a questo attributo chiamandolo:

* Title attribute
* Attributo title
* Attributo titolo

{{% notice note "Nota bene" %}}
Da buoni informatici siamo legittimati a farcire di inglesismi la nostra parlata, quindi se si mescola italiano e inglese nessuno avrà nulla da obiettare.
{{% /notice %}}


## Heading

**Intestazioni** in italiano, sono talvolta conosciuti come "titoli di livello x", dove "x" è un numero da 1 a 6.

In generale, definirli "heading" permette di distinguerli dal titolo della pagina o dall'attributo *title*.
In questo sito, quando si parla di *heading di livello 2*, si intenderà proprio i titoli di questo genere.




## Table heading

L'intestazione di una tabella è la riga che definisce il nome delle colonne.

Riga di intestazione	| oppure 		| Table heading
---------------------	| ------ 		|--------------
Colonna 1							| Colonna 2	| Colonna 3

Vale anche per le tabelle orizzontali.
