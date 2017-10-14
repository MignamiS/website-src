+++
title = "Fare in modo che il campo di ricerca non vada cercato"
date = "2017-10-08"
tags = ["landmark", "semantica", "ricerca"]
draft = "true"
+++

Chi come me fa fatica a saltare da una parte all'altra di un sito, cercando di decifrare la logica dell''organizzazione delle informazioni, spesso utilizza Google per arrivare alla pagina che gli interessa.
Basta digitare poche parole chiave e, solitamente, il primo risultato della ricerca è quello desiderato.

Da webmaster però mi accorgo che questo comportamento diffuso riduce il traffico nelle pagine e di conseguenza gli introiti.
Così si introducono motori di ricerca interni, ma come fare a renderli veramente accessibili e utili a mantenere l'utente nelle nostre pagine.

In questo articolo la risposta alla domanda, tutt'altro che scontata.

<!--more-->

## Il problema dei menu di navigazione: l'arbitrarietà

Capita troppo di frequente di entrare in siti web la cui organizzazione delle pagine è caotica.
Spesso poi il menu di navigazione non è nemmeno ben identificato, sia visivamente che semanticamente.

**Confondere l'utente e farlo perdere nel sito non è un buon modo per generare traffico**.

Naturalmente non esiste una ricetta o una convenzione che indichi in modo chiaro come strutturare un sito web, a parte forse alcune voci classiche come:

- Home
- Chi siamo
- Contatto

Se poi ci si mettono pure menu espandibili solo parzialmente accessibili, ecco che diversi utenti si ritroveranno a vagare senza meta.



Persino io sono solito cercare su Google le informazioni, pur sapendo esattamente in quale sito voglio andare.
Questo perché i menu di navigazione sono costruiti secondo una logica arbitraria e spesso poco chiara.
E invece di esser costretto a saltare da una pagina all'altra preferisco chiedere all "oracolo" di trovare le informazioni per me.

Ma se noi volessimo tenere gli utenti nel nostro sito, ecco che possiamo affidarci ai motori di ricerca interni.
Solitamente viene collocato in alto a destra, ma si tratta di una convenzione.

![Un campo di ricerca.](/img/search-field-example.jpg)

Per fornire questo tipo di servizio è però fondamentale conoscere alcune cose.



## La funzione di ricerca deve essere facile da raggiungere

Il campo di ricerca deve essere di facile accesso per le persone con difficoltà motorie.
Questo perché si trova spesso **dopo il menu di navigazione** e questi è costretto a saltare da un link all'altro mediante tabulatore, magari anche per decine di elementi.

La **prima soluzione** è di utilizzare uno *skip-link* dedicato alla ricerca.

~~~html
<a href="#ricerca-nel-sito">Vai alla ricerca</a>
...
<input type="text" id="ricerca-nel-sito" ... />
~~~

Posizionando il link fra i primissimi elementi della pagina, sarà possibile per un utente che naviga usando la tastiera, saltare direttamente al campo di ricerca.


Un'altra **soluzione** è posizionare il campo di ricerca fra i primi elementi della pagina e, sfruttando il CSS, farlo apparire nella sua posizione originale.
Questo può però causare confusione nell'utente se il focus non dovesse seguire un ordine logico.


## La funzione di ricerca deve essere facile da trovare

Per le persone che hanno difficoltà visive, come ciechi o ipovedenti, è necessario mettere una "bandierina invisibile" sul form per la ricerca nel sito.
Questo perché semanticamente per un computer un campo di testo è uguale a tutti gli altri.

Possiamo però attribuirgli un [ruolo di ricerca](https://www.w3.org/TR/wai-aria/roles#search)
in modo che uno screen reader sia consapevole che quel campo di testo è adibito a motore di ricerca interno.

~~~html
<div role="search">
	<input type="text" aria-label="Cerca nel sito"/>
	<button>
		<span class="fa fa-search" aria-label="Cerca"></span>
	</button>
</div>
~~~

Innanzitutto grazie all'attributo `role="search"` associato al *div* sto affermando che tutto quello che è contenuto è implicato nella ricerca interna al sito.
Questo genera un *landmark*, un segnaposto che le tecnologie assistive riconoscono e notificano all'utente.
Ecco ad esempio la struttura di una pagina web mostrata da uno screen reader.

![Elenco dei landmark di una pagina web mostrato da NVDA](/img/search-landmark-list.png)

Selezionando la voce *search* il cursore viene portato automaticamente nel *div* adibito alla ricerca nel sito.

Alcune osservazioni:

- Il bottone è all'interno del widget di ricerca perché anc'esso contribuisce. Se fosse lasciato fuori sarebbe un errore semantico.
- Il ruolo "search" sovrascrive il ruolo dell'elemento che lo riceve. Per questo non va attribuito ad elementi come *form* o *link* perché altrimenti perderebbero il loro significato originario e non sarebbero più riconosciuti come tale. Il ruolo *search* va attribuito solo a contenitori anonimi come *div*.

Ecco invece alcune considerazioni sulle etichette:

Siccome l'icona della lente d'ingrandimento è convenzionalmente associata alla ricerca, spesso il campo di testo non ha etichette associate.
Questo può creare problemi alle persone con difficoltà visive, per cui è opportuno attribuire un'etichetta invisibile che espliciti l'intento del campo.

Puoi notare inoltre che anche il bottone ha un'etichetta associata e che essa non contiene una descrizione dell'immagine in sé, ma della funzione che rappresenta.

Nell'immagine del campo di ricerca è presente un *placeholder*, la scritta *search* sfumata.
Tieni presente che **da solo non basta** a etichettare un campo e spesso viene ignorato dagli screen reader.

Ecco quindi come verrà letto il nostro widget di ricerca:

{{< screen_reader "Landmark ricerca, campo di testo vuoto cerca nel sito, bottone cerca" >}}




## Non mettere i bastoni fra le ruote agli utenti!

In un eccesso di zelo uno sviluppatore web potrebbe utilizzare Javascript per spostare automaticamente il focus nel campo di ricerca appena la pagina  viene caricata.
Questo è **molto scomodo** per utenti con difficoltà visive e motorie.

Nel caso dei primi lo screen reader non annuncerà niente della pagina, notificando solo che il cursore è stato posizionato nel campo di ricerca. E se l'utente intendeva navigare la pagina sarà costretto a sganciarlo e ricollocarlo all'inizio, cosa piuttosto fastidiosa te lo garantisco.

Discorso analogo nel caso degli utenti con difficoltà motorie, che saranno costretti a riportare il cursore in carreggiata prima di poter navigare il sito.

Una regola spannometrica è di evitare di posizionare automaticamente il focus in una pagina, a meno che questa non sia dedicata completamente all'elemento in questione.
Ad esempio, nel caso di una pagina di login, posizionare il cursore sul primo campo del form è una **agevolazione gradita**, in quanto la pagina è adibita unicamente a questo scopo.




## Agevolare la ricerca

Infine un consiglio utile su come agevolare la ricerca a tutti gli utenti.
Di solito quando l'utente preme invio, dopo aver compilato il campo di ricerca, viene portato ad una pagina con i risultati.

Il consiglio è di selezionare automaticamente il primo risultato, in modo che l'utente non debba navigare fino ad esso per trovarlo.
Naturalmente occorre valutare caso per caso, non in tutte le situazioni questo porta benefici.



## Conclusione

Ti ho mostrato come creare un widget di ricerca accessibile e quali trappole evitare.
Migliorare l'accessibilità di questi strumenti permette agli utenti con difficoltà motorie e visive di muoversi più agilmente nel tuo sito, evitando che si appoggino a risorse esterne come i motori di ricerca.

Se posso darti un ultimo consiglio, è di **monitorare le ricerche** degli utenti.
In questo modo capirai cosa la gente cerca più frequentemente e potrai mettere queste informazioni in evidenza per agevolare ulteriorlmente la navigazione.
