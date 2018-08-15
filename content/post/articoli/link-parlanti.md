---
title: "I link parlanti sono buoni consiglieri"
date: 2018-03-22T11:57:15+02:00
draft: false
tags: ["link"]
categories: ["articoli"]
---

I link sono il cuore del web, la forma più primordiale che distingue il testo digitale da quello cartaceo.
Dopo tutti questi anni dovrebbe essere ormai chiaro come costruire l'etichetta di un link, eppure...

E dire che un link ambiguo è indigesto ai motori di ricerca almeno tanto quanto lo è per le persone con handicap.

<!--more-->

I link devono essere **parlanti**, ne va dell'accessibilità e dell'usabilità del nostro prodotto web.

Un link *parlante* è un collegamento la cui etichetta **indica in modo chiaro a cosa serve**.
Questo perché chi ha difficoltà visive potrebbe non cogliere elementi del contesto che spiegano lo scopo del link.

Prendiamo ad esempio un testo e aggiungiamo un link:

"Leggi 
[questo]({{< ref "link-parlanti.md" >}})
articolo sui link parlanti".

Ecco come lo percepisce un utente cieco che naviga la pagina con uno screen reader.

> Questo, link

Il link "questo" non da nessuna informazione, è **ambiguo**.
L'utente deve quindi capire da sé a cosa serve, magari è proprio ciò che gli serve ma non lo può sapere a meno che non ispezioni le vicinanze alla ricerca di indizi che gli facciano capire che è proprio quello che sta cercando.

In questo caso è facile perché, leggendo il testo prima di esso, l'utente può dedurre che si tratta di un collegamento ad un articolo.

Ma non sempre è facile capire a cosa serva un link, specialmente se l'utente non può fare affidamento sulla vista.



## Come posso rendere un link "parlante" se è integrato in un testo?

Vero, se un link non fa parte di un testo di senso compiuto è più facile.
Nel caso di prima, il testo stesso ci viene in aiuto per rendere il link esplicito:

"Leggi questo 
[articolo sui link parlanti]({{< ref "link-parlanti.md" >}})
"



## Ok, e se proprio non posso renderlo "parlante"?

Capita, magari per motivi estetici, o per mille altre ragioni.
Non sempre si può rendere esplicito un link.

Per esempio, nella home di questo sito gli articoli sono mostrati in versione "ristretta", mentre cliccando su "continua" si legge il testo per intero.
Sarebbe poco logico aggiungere il titolo ad ognuno di questi link...almeno, visivamente.

Ma puoi leggere quest'altro post in cui spiego 
[come sovrascrivere l'etichetta di un link]({{< ref "sovrascrivere-etichette-con-la-forza.md" >}})
