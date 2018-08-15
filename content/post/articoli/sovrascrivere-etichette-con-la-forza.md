---
title: "Sovrascrivere Le Etichette Con La Forza"
date: 2017-09-29T10:54:55+02:00
draft: false
tags: ["aria-label", "link"]
categories: ["articoli"]
---

Ci sono volte in cui un'informazione è intuitiva per le persone che ci vedono, come ad esempio un'icona.
Ma per chi ci vede poco, o non ci vede del tutto, come possiamo trasmettere la stessa informazione senza stravolgere la pagina?

In questo articolo vediamo come rendere accessibile agli screen reader informazioni complesse, deducibili solo da esseri umani.

<!--more-->

Prendiamo il caso del link "Torna alla home page": è ormai diffusa l'icona della "casetta".
Basta quindi creare un link che la mostri, perché ogni utente sappia che cliccandoci sarà riportato alla pagina principale.

~~~html
<a href="home.php">
  <span class="glyphicon glyphicon-home"></span>
</a>
~~~

Qual è il problema? Lo *span*, a differenza delle immagini, non ha un testo associato.
Ecco come è percepito questo link da una macchina.

{{< figure src="/images/Icona-senza-etichetta.png" caption="Il link per tornare alla home page ha una icona ma non etichetta." >}}

Come facciamo a dare un'etichetta leggibile a questo link, per permettere a chi non ci vede (e ad uno spider di Google), di capire a cosa serve?
Usiamo un attributo speciale che permette di inserire informazioni invisibili ad occhio nudo, ma perfettamente accessibili ad una macchina.

~~~html
<span aria-label="Home page" class="glyphicon glyphicon-home"></span>
~~~

{{< figure src="/images/Icona-con-etichetta.png" caption="Cliccando sulla casetta si torna alla home page. La finestra a fianco mostra l'elenco dei link della pagina." >}}

{{% notice warning "Attenzione" %}}
I link senza testo, come quello con l'icona Home, possono penalizzare la SEO perché considerati "non descrittivi".
{{% /notice %}}




## Come funziona *aria-label*?

L'attributo *aria-label* sovrascrive la rappresentazione testuale dell'elemento.
È utile in circostanze dove la normale descrizione non è sufficiente oppure può confondere.

Per esempio si usa per:

* Dare un'etichetta ad un link che non contiene testo, come vediamo in questo 
[articolo sui link parlanti]({{< ref "link-parlanti.md" >}})
.
* Attribuire il nome ad un campo di testo che, per ragioni estetiche, non lo ha. Ad esempio, nel caso di un campo di ricerca dove il suo  scopo è palesato dall'icona della ricerca.
* Rendere esplicito il contenuto di una regione della pagina, come vediamo in questo 
[articolo sui landmark di navigazione]({{< ref "nav-nome.md" >}})
.

{{% notice warning Attenzione %}}
Si scrive **ARIA** e non **ARIAL**.
Dopo 8 ore di lavoro capita che scappi una "L" da "label" e vada a finire in "aria", ma scrivendo "arial-label" l'etichetta non funziona.
Sembra banale, ma è un errore che capita più spesso di quanto si pensi.
{{% /notice %}}
