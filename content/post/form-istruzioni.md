+++
date = "2017-10-17"
tags = ["form", "etichette"]
title = "Come etichettare un form correttamente"
draft = true
+++

Un tizio seccato contatta il servizio di supporto perché non riesce a registrarsi: l'operatore segue passo-passo la compilazione del form per la registrazione.
Dopo aver digitato una password nell'apposito campo l'utente passa al successivo, "conferma password" nel quale inserisce un secco "sì".
Purtroppo non è una barzelletta, addetti al supporto clienti si imbattono tutti i giorni in situazioni come questa.
A volte perché l'utente è veramente inesperto, a volte perché l'interfaccia confonde le idee.

Ecco qualche spunto per rendere i nostri form un po' più vivibili.

<!--more-->

Il modulo, o form, è alla base del web interattivo, cioè dove l'utente può inviare dati e non solo riceverli.
Si tratta in fin dei conti della versione informatica del classico "formulario" da compilare che si può trovare ancora oggi in posta o in banca.
Ma se dietro uno sportello c'é un funzionario umano dotato di intelligenza umana (si spera), dietro ad un form c'é il più delle volte una macchina.
E le macchine non vedono più in là del loro naso, per cui chi costruisce un formulario informatico deve essere **il più chiaro possibile** perché l'utente non commetta errori.

Se poi si ha a che fare con persone con difficoltà visive o motorie, ci sono anche alcuni accorgimenti a cui prestare attenzione per rendere l'esperienza utente la più fluida possibile.



## Perché etichettare i campi dei form

"Ma io uso sempre le etichette quando costruisco un form!" dirà qualcuno risentito.
E lo credo bene: un form senza etichette è un po' come un cartello stradale con delle frecce, ma senza i nomi delle località alle quali puntano.

Chi fa uso di tecnologie assistive come screen reader spesso salta da un campo all'altro con il *tabulatore*.
Ma se il campo non ha un'etichetta associata viene annunciato solo "campo di testo" o "checkbox non selezionato".

Inoltre entrando in un form si attiva una modalità speciale chiamata "modalità di input" che ignora tutto quello che c'é scritto attorno ai campi che non siano etichette.
Ad esempio se prima di un campo c'é un paragrafo che spieghi che tutti i campi sono obbligatori, questa informazione andrebbe inesorabilmente persa.



## Come etichettare un campo

Quando si aggiunge un campo, sia esso un campo di testo, un checkbox o un menù a tendina, occorre sempre fare 2 operazioni:

1. Inserire un'etichetta per il campo;
2. **Collegare l'etichetta al campo**;

Il secondo punto è il più importante perché è quello che rende accessibile il campo appena inserito.
Collegando l'etichetta si stabilisce una relazione fra i due elementi che può essere rilevata programmaticamente anche da una macchina.
Per stabilire questa relazione non è infatti sufficiente mettere etichetta e campo vicini, sia nel DOM che visivamente, ma occorre creare una relazione in codice.

**Benefici di collegare correttamente etichetta e campo**:

- Le macchine sono in grado di comprendere la relazione fra il campo e la sua etichetta, siano esse spider di Google o tecnologie assistive.
- L'area di click è più grande.

Certo, l'area di attivazione viene estesa non solo al campo, ma anche all'etichetta.
Questo è particolarmente utile agli utenti mobile e con mobilità ridotta, soprattutto per quei componenti piccoli come radio-button o checkbox.

Ma vediamo come fare per collegare un'etichetta al suo campo.



### Relazione esplicita (consigliata)

~~~html
<label for="username">Nome utente:</label>
<input type="text" id="username"/>
~~~

Questo frammento di codice mostra un'etichetta associata **esplicitamente** al suo campo tramite la referenza al suo id grazie all'attributo **for**.

Questo sistema è consigliato in quanto porta 2 benefici:

- La relazione è diretta ed è quindi più accessibile da parte di una macchina (che sia uno spider o uno screen reader).
- Associare un *id* ad un campo consente di referenziarlo da un punto qualsiasi della pagina: si può ad esempio creare un sommario degli errori commessi dall'utente inserendo un elenco di link che rimandano ai campi da correggere.


### Relazione implicita

~~~html
<label>Nome utente:
	<input type="text"/>
</label>
~~~

Questa è una relazione di parentela, cioé dove il campo è figlio dell'etichetta.
Questo tipo di relazione è implicita e a volte non è riconosciuto dalle tecnologie assistive.



## Includere tutte le informazioni nelle etichette

Come detto prima, chi fa uso di uno screen reader potrebbe non leggere le informazioni che non sono inserite come etichette.
Ecco perché è sempre buona cosa **includere tutte le informazioni su come  riempire un campo direttamente nell'etichetta**.


### Vade retro Asterisco!

È convenzione marchiare i campi obbligatori con un asterisco, lo faccio pure io.
Ma questa prassi è **il male** se non si seguono delle precise linee guida.

Il modo migliore per indicare che un campo è obbligatorio è di **dirlo esplicitamente nell'etichetta**.

{{< fig src="img/label-mandatory.png" alt="Campo di testo nome utente (obbligatorio)" >}}

Ma spesso l'estetica non consente di avere etichette troppo lunghe, per cui l'asterisco rimane l'unica scelta possibile, come fare?
Oltre a naturalmente inserire una legenda dove viene spiegato che i campi contrassegnati con un asterisco sono obbligatori, ci sono 2 opzioni:

- Invece di utilizzare il simbolo `*` si può inserire un'icona simile, ad esempio **fa-asterisk** (Font Awsome) con testo alternativo "campo obbligatorio".
- Usare l'attributo *aria-describedby* referenziando la legenda.

Nel caso della seconda opzione si otterrebbe un risultato del genere:

{{< screen_reader "Nome utente, campo di testo vuoto, il campo è obbligatorio" >}}





tutto quello che non è un'etichetta non viene letto, per cui includilo

text input: left/above
checkboxes/readio: right

il simbolo del male: l'asterisco
l'asterisco non è obbligatorio
	- non è chiaro
	- la sintesi vocale puo non leggerlo

come etichettare correttamente un form
codice: esplicito e implicito 
il beneficio del for: anchor to link

usabilità
etichette visivamente associate e in codice
do not use placeholder

