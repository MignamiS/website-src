+++
title = "Fare in modo che il campo di ricerca non vada cercato"
date = "2017-10-08"
tags = ["landmark", "semantica", "ricerca"]
+++

Chi come me fa fatica a saltare da una parte all'altra di un sito, cercando di decifrare la logica dell'organizzazione delle informazioni, spesso utilizza Google per arrivare alla pagina che gli interessa.
Basta digitare poche parole chiave e, solitamente, il primo risultato della ricerca è quello desiderato.

Da webmaster però mi accorgo che questo comportamento diffuso riduce il traffico nelle pagine e di conseguenza gli introiti.
Così si introducono motori di ricerca interni, ma come fare a renderli veramente accessibili e utili a mantenere l'utente nelle nostre pagine.

In questo articolo la risposta alla domanda, tutt'altro che scontata.



<!--more-->

{{< curiosita "la maggior parte dei miglioramenti dell'accessibilità riguardano meno di 2 righe di codice." >}}

## L'arbitrarietà dei menu di navigazione

Capita di navigare in siti web le cui pagine sono organizzate secondo logiche aliene, con un menu di navigazione non ben identificato, sia visivamente che semanticamente.
Ciò significa che sia l'utente "umano" che una macchina fanno fatica ad orientarsi nell'intricata sequenza di pagine.
Se poi ci si mettono pure menu espandibili solo parzialmente accessibili, ecco che diversi utenti si ritroveranno a vagare senza meta.

È importante notare che **confondere l'utente e farlo perdere nel sito non è un buon modo per generare traffico**.
Questo perché il più delle volte la visita di un sito è motivata dalla ricerca di informazioni e giocare alla "caccia al tesoro" è il modo migliore per perdere un visitatore invece che guadagnarlo.

Quando il numero delle pagine diventa considerevole, pensare di poterle referenziare tutte in un unico menu è poco praticabile.
Ma se noi volessimo tenere gli utenti nel nostro sito, ecco che possiamo affidarci ai motori di ricerca interni.
Questi strumenti consentono di fornire all'utente le pagine che gli servono, saltando la navigazione.

{{< fig src="img/search-field-example.jpg" alt="Un campo di ricerca." >}}

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

{{< fig src="img/search-landmark-list.png" alt="Elenco dei landmark di una pagina web mostrato da NVDA" >}}


Selezionando la voce *search* il cursore viene portato automaticamente nel *div* adibito alla ricerca nel sito.

Alcune osservazioni:

- Il bottone è all'interno del widget di ricerca perché anch'esso contribuisce. Se fosse lasciato fuori sarebbe un errore semantico.
- Il ruolo "search" sovrascrive il ruolo dell'elemento che lo riceve. Per questo non va attribuito ad elementi come *form* o *link* perché altrimenti perderebbero il loro significato originario e non sarebbero più riconosciuti come tale. Il ruolo *search* va attribuito solo a contenitori anonimi come *div*.

Ecco invece alcune considerazioni sulle etichette:

Siccome l'icona della lente d'ingrandimento è convenzionalmente associata alla ricerca, spesso il campo di testo non ha etichette associate.
Questo può creare problemi alle persone con difficoltà visive, per cui è opportuno attribuire un'etichetta invisibile che espliciti l'intento del campo.

Inoltre anche il bottone ha un'etichetta associata e che essa non contiene una descrizione dell'immagine in sé, ma della funzione che rappresenta.

Nell'immagine del campo di ricerca è presente un *place-holder*, la scritta *search* sfumata.
Tieni presente che **da solo non basta** a etichettare un campo e spesso viene ignorato dagli screen reader.

Ecco quindi come verrà letto il nostro widget di ricerca:

{{< screen_reader "Landmark ricerca, campo di testo vuoto cerca nel sito, bottone cerca" >}}




## Non mettere i bastoni fra le ruote agli utenti!

In un eccesso di zelo uno sviluppatore web potrebbe utilizzare JavaScript per spostare automaticamente il focus nel campo di ricerca appena la pagina  viene caricata.
Questo è **molto scomodo** per utenti con difficoltà visive e motorie.

Nel caso dei primi lo screen reader non annuncerà niente della pagina, notificando solo che il cursore è stato posizionato nel campo di ricerca. E se l'utente intendeva navigare la pagina sarà costretto a sganciarlo e ricollocarlo all'inizio, cosa piuttosto fastidiosa lo garantisco.

Discorso analogo nel caso degli utenti con difficoltà motorie, che saranno costretti a riportare il cursore in carreggiata prima di poter navigare il sito.

Una regola spannometrica è di evitare di posizionare automaticamente il focus in una pagina, a meno che questa non sia dedicata completamente all'elemento in questione.
Ad esempio, nel caso di una pagina di login, posizionare il cursore sul primo campo del form è una **agevolazione gradita**, in quanto la pagina è adibita unicamente a questo scopo.




## Agevolare la ricerca

Infine un consiglio utile su come agevolare la ricerca a tutti gli utenti.
Di solito quando si preme invio, dopo aver compilato il campo di ricerca, si viene portati ad una pagina con i risultati.

Il consiglio è di selezionare automaticamente il primo risultato, in modo che l'utente non debba navigare fino ad esso per trovarlo.
Naturalmente occorre valutare caso per caso, non in tutte le situazioni questo porta benefici.



## Conclusione

Ti ho mostrato come creare un widget di ricerca accessibile e quali trappole evitare.
Migliorare l'accessibilità di questi strumenti permette agli utenti con difficoltà motorie e visive di muoversi più agilmente nel tuo sito, evitando che si appoggino a risorse esterne come i motori di ricerca.

Se posso darti un ultimo consiglio, è di **monitorare le ricerche** degli utenti.
In questo modo capirai cosa la gente cerca più frequentemente e potrai mettere queste informazioni in evidenza per agevolare ulteriormente la navigazione.
