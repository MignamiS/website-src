+++
date = "2017-10-07"
tags = ["link"]
title = "Costruire link decenti"
+++

Una delle componenti base dell'accessibilità di un sito web è la navigazione in esso.
I **link** ci permettono di spostarci da una parte all'altra, ma quando sono ambigui possono creare vere e proprie barriere persino ad utenti navigati.

Un esempio? Prova a scaricare uno di quei software gratuiti ed evitare tutti i banner pubblicitari che ti dicono "scarica!" e "download".
Confondere l'utente per questi siti è la prassi così **CASUALMENTE** prima di trovare quello che cerca si fa un bel giretto e fa guadagnare soldi al gestore.

Ma tu non sei uno di questi gestori disonesti, vero? VERO??? Bene, ecco qualche suggerimento per creare dei link che siano accessibili.

<!--more-->

Una persona con problemi di vista, come un utente cieco ad esempio, ha diversi strumenti che gli agevolano la navigazione in una pagina.
[NVDA](https://www.nvaccess.org/)
permette di saltare da un link all'altro, oppure di averne un elenco sotto forma di lista.
Il problema è che se un link non ha un'etichetta chiara, comprensibile anche fuori dal contesto, la persona potrebbe non capire lo scopo.

Ad esempio ecco come appare una pagina web con dei link come questi:

- Clicca [qui](#) per leggere l'articolo
- [scarica](#) il programma in PDF

{{< fig src="img/screenshot-lista-link.png" alt="Schermata di NVDA con l'elenco dei link di una pagina." >}}

Il "qui" è ambiguo, l'utente è costretto a leggere quello che gli sta attorno per cercare di capire a cosa serva.
E magari ha anche qualche possibilità di farcela, ma uno spider di Google?
Per una buona *Search Engine Optimization* (SEO) è opportuno che il testo dei link sia chiaro.



## Un buon modo per scrivere l'etichetta di un link

Il modo migliore per costruire link accessibili è proprio scrivendo delle etichette chiare.
Immagina di prendere tutti i link e di metterli in una pagina separata: sono tutti sufficientemente comprensibili?

Ad esempio possiamo scrivere:

- Clicca qui per [scaricare il programma](#).
- Leggi questo [articolo riguardo l'accessibilità](#).

Questo porta diversi benefici:

1. Il link indica in modo esplicito dove porta e migliora accessibilità e SEO.
2. L'area cliccabile è più estesa rendendolo più facile da attivare anche per utenti mobile.
3. Fa risaltare il testo invogliando il lettore a cliccare.


**Nota**: quando possibile evita di inserire un URL come testo di un link, ad esempio http://www.google.com.
L'etichetta deve essere leggibile da un essere umano.


## Link brevi per natura

Come la mettiamo con i link della *pagination*? O con un elenco alfabetico dove ogni link possiede un'etichetta di una lettera sola?

{{< fig src="img/example-pagination.png" alt="Esempio di pagination" >}}

In realtà proprio nella loro incomprensibilità sono chiari, perché l'utente intuisce che si tratta di un elenco di elementi correlati.

Una buona prassi è espandere l'area cliccabile in modo che non vengano attivati link vicini per errore.
Questo è particolarmente gradito da utenti con difficoltà motorie, oltre che da tutti coloro che utilizzano uno smartphone.



### Immagini con link

Quando un link contiene un'immagine, l'etichetta sarà il testo alternativo dell'immagine stessa.
Questo vale anche per i bottoni.

~~~html
<a href="#">
	<img src="img/freccia.png" alt="Vai">
</a>
~~~

Così quando la sintesi vocale arriverà sul link annuncerà "Vai".

**Da evitare** sono le ASCII-art perché sono comprensibili solo agli utenti dotati di vista (e gli spider dei motori di ricerca non lo sono).
Nell'esempio della pagination visto prima i link per "precedente" e "successivo" sono stati rimpiazzati con i caratteri `<` e `>`.
Se vuoi inserire una freccia in un link, invece di usare i caratteri della tastiera puoi usare una delle icone di [Font Awesome](https://www.w3schools.com/icons/fontawesome_icons_directional.asp)
inserendo un testo alternativo che venga letto alle tecnologie assistive.

~~~html
<a href="#">
	<span class="fa fa-arrow-right" title="Vai"></span> 
</a>
~~~

In questo caso ho utilizzato l'attributo *title*, ma è anche possibile inserire il testo direttamente nello *span* e poi, tramite CSS, spostarlo fuori dallo schermo per renderlo invisibile agli utenti.


## Conclusioni

Avere dei link chiari in una pagina porta molteplici benefici.
In primo luogo sono accessibili, rendendo la navigazione piacevole e senza "colpi di scena".

In secondo luogo vengono sostenuti i motori di ricerca (SEO) nel loro lavoro di indicizzazione delle nostre pagine.

Infine un'etichetta più grande è facile da premere, cosa che avvantaggia gli utenti mobile e tutti coloro che hanno difficoltà motorie.

Qualche secondo in più di lavoro è sicuramente un buon investimento.
