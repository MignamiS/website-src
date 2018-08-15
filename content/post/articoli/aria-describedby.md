---
title: "Appiccicare una descrizione ad un elemento"
date: 2018-08-15T16:15:42+02:00
draft: false
tags: ["aria-describedby"]
categories: ["articoli"]
---

Un attributo che ci può levare d'impaccio in alcune situazioni spinose.

Per esempio quando si tratta di aggiungere una descrizione ad un elemento, per renderlo accessibile, ma in circostanze dove lo spazio o il contesto non lo consentono.

<!--more-->

Situazione pratica: abbiamo un campo password con alcuni vincoli imposti, come quali simboli sono ammessi e la lunghezza minima.
Per motivi di design questi vincoli sono nascosti all'utente e appaiono in un fumetto solo quando il cursore entra nel campo.

Non si può:

* Usare un testo visibile solo agli screen reader messo prima del campo per spiegare come deve essere composta la password, perché l'utente salta da un campo all'altro e non può leggerlo.
* Inserire la spiegazione nell'etichetta del campo, perché la renderebbe verbosa e poco estetica.
* Utilizzare il *placeholder*, perché oltre a non essere esteticamente compatibile, può non essere annunciato correttamente dalla sintesi vocale.

Fra tutte le soluzioni che si potrebbero adottare, quella che propongo è l'attributo **aria-describedby**.

L'attributo *aria-describedby* permette di aggiungere una descrizione all'elemento corrente, in modo che sia annunciata subito dopo l'etichetta dell'elemento stesso.
*Aria-describedby* contiene la referenza (id) di un elemento, il cui testo è usato per costruire la descrizione.

~~~html
<label for="password">Password</label>
<input type="password" id="password" aria-describedby="fumetto-password"/>
<p class="fumetto" id="fumetto-password">Lunghezza minima 8 caratteri, simboli consentiti - e _</p>
~~~

Quando il cursore entra nel campo, viene per esempio annunciato:

> Password campo Lunghezza minima 8 caratteri simboli consentiti trattino e trattino basso



## Posso usare un elemento che è nascosto?

Sì, anche se l'elemento è reso invisibile tramite CSS può essere comunque raggiunto ed utilizzato per la descrizione.

{{% notice note "Nota bene" %}}
Normalmente nascondendo con il CSS un elemento, le tecnologie ausiliarie tendono ad ignorarlo.
{{% /notice %}}
