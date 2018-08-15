---
title: "La peggior maledizione? Le tabelle senza intestazione"
date: 2018-04-18T12:01:49+02:00
draft: false
tags: ["tabelle"]
categories: ["articoli"]
---

Rendere accessibile una tabella è semplice e bastano poche righe di codice.

Se si trascura questo dettaglio un insieme di dati può diventare un ammasso di numeri senza forma; illeggibile.

<!--more-->

Una tabella è composta, come minimo, da due parti: *l’intestazione* e i *dati*.

Prendiamo ad esempio questa 
[tabella sul Sistema solare](https://it.wikipedia.org/wiki/Sistema_solare)
che ho trovato su Wikipedia.

Pianeta		| Distanza media (milioni di Km)	| Perielio (milioni di Km)
--------	| -------------------------------	| ---------------------------
Mercurio	| 57,91 													| 46
Venere		| 108															| 107,5
Terra			| 149,6														| 147,1
Marte			| 227,94													| 206,6

Per chi la tabella la vede, trovare la distanza media della Terra è semplice.

Ma ecco invece come appare una tabella senza intestazione, non accessibile, quando viene letta da uno screen reader.

> Pianeta Distanza media (milioni di km) Perielio (milioni di km) Mercurio 57,91 46 Venere 108 107,5 Terra 149,6 147,1 Marte 227,94 206,6 ...

Immagina di dover estrapolare lo stesso dato da una sequenza come questa…

**Ma l'intestazione c'è! Si vede benissimo.**

Vero, a livello visivo l'intestazione è visibile, ma non si può dire lo stesso del codice.
Se coloriamo lo sfondo di una cella, una macchina non può indovinare che il suo contenuto deve considerarlo "intestazione".
Possiamo al limite farlo noi umani, ma richiede uno sforzo deduttivo che un computer, almeno per il momento, non può ancora fare.



## Determinare programmaticamente un'intestazione

Per rendere accessibile ad un computer (e quindi ad una persona con handicap) una tabella, si usa il tag `<th></th>`.

~~~html
<table>
  <tr>
    <th>Pianeta</th>
    <th>Distanza media</th>
    <th>Perielio</th>
  </tr>
  <tr>
    <td>Mercurio</td>
    <td>57,91</td>
    <td>46</td>
  </tr>
  ...
</table> 
~~~

Ora l'intestazione è determinabile programmaticamente.

Le persone cieche possono navigare le tabelle comodamente, se sono accessibili.
Lo screen reader annuncia il nome della colonna quando il cursore entra in essa, poi legge il contenuto.
In questo modo l'utente sa sempre dove si trova.

Ad esempio, nel caso della distanza della Terra:

> Distanza media (milioni di Km) 149,6

Questa soluzione si applica anche per le **tabelle orizzontali**.
[Maggiori informazioni sulle tabelle](https://www.w3.org/WAI/tutorials/tables/one-header/).

{{% notice tip %}}
Utilizzare il tag *th* agevola la creazione dello stile per la tabella.
Dal CSS si può direttamente agganciare l'elemento "th".
{{% /notice %}}
