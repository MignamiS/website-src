---
title: "Dare un nome ai menu di navigazione"
date: 2018-01-15T11:50:21+02:00
lastmod: 2018-08-15T11:50:21+02:00
draft: false
tags: ["nav", "navigazione", "aria-label"]
categories: ["articoli"]
---

Capita che ci siano più menu per navigare un sito.
Magari uno di primo livello, con le sezioni principali del sito, e uno secondario con la navigazione delle sotto-sezioni.

Ecco come possiamo dare loro un nome, rendendo esplicito il loro scopo.

<!--more-->

Abbiamo già parlato dei menu di navigazione e di come etichettare elementi per renderli più accessibili agli screen reader.

* [Articolo sui menu di navigazione]({{< ref "faro-per-naviganti.md" >}})
* [Articolo sulle etichette per screen reader]({{< ref "sovrascrivere-etichette-con-la-forza.md" >}})

Possiamo unire le due cose per ottenere dei menu di navigazione più chiari.
Per esempio, se abbiamo un sommario:

~~~html
<nav aria-label="Menu principale">...</nav>
...
<nav aria-label="Indice dei contenuti">
  Capitolo 1
  Capitolo 2
  ...
</nav>
~~~

Un computer può quindi ricostruirsi la struttura della pagina, il cui scheletro è composto da regioni che indicano chiaramente il loro scopo.

{{< figure src="/images/landmark-navigazione.png" alt="Elenco di regioni di una pagina, dove è indicato chiaramente il menu principale e l'indice dei contenuti" caption="Elenco delle regioni di una pagina, con i menu di navigazione resi espliciti dal nome" >}}

{{% notice warning "Attenzione" %}}
Se nella pagina sono presenti due o più menu di navigazione **senza** un'etichetta, è considerato un errore dai principali validatori di accessibilità.
{{% /notice %}}




## Devo farlo anche quando ho un solo menu di navigazione?

Se il menu è solo uno per pagina, aggiungere l'etichetta è a tua discrezione.
Migliora l'esperienza utente.
