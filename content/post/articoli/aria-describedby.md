---
title: "Appiccicare una descrizione ad un elemento"
date: 2018-08-15T16:15:42+02:00
lastmod: 2018-08-18T16:15:42+02:00
draft: false
tags: ["aria-describedby", "etichette", "form", "WAI-ARIA"]
categories: ["articoli"]
---

Un trucchetto che ci può levare d'impaccio in alcune situazioni spinose.
Per esempio quando si tratta di aggiungere una descrizione ad un elemento, per renderlo accessibile, ma in circostanze dove lo spazio o il contesto non lo consentono.

<!--more-->

Situazione pratica: abbiamo un campo password con alcuni vincoli imposti, come quali simboli sono ammessi e la lunghezza minima.
Per motivi di design questi vincoli sono nascosti all'utente e appaiono in un fumetto solo quando il cursore entra nel campo.

Non si può:

* Usare un testo visibile solo agli screen reader messo prima del campo per spiegare come deve essere composta la password, perché l'utente salta da un campo all'altro e non può leggerlo.
* Inserire la spiegazione nell'etichetta visibile del campo, perché la renderebbe verbosa e poco estetica.
* Utilizzare il *placeholder*, perché oltre a non essere esteticamente compatibile, può non essere annunciato correttamente dalla sintesi vocale.

Abbiamo visto in questo 
[articolo su aria-label]({{< ref "sovrascrivere-etichette-con-la-forza.md" >}})
come è possibile sovrascrivere un'etichetta.
In questo caso, però, abbiamo già tutto quello che ci serve nella pagina e dobbiamo solo informare le tecnologie ausiliarie su dove andare a prendere le informazioni.

Ecco come viene annunciato il campo dallo screen reader quando è selezionato.

> Campo password

Le istruzioni del fumetto su come deve essere la password sono purtroppo ignorate.

Come soluzione per informare l'utente propongo l'attributo **aria-describedby**.
Esso permette di aggiungere una descrizione all'elemento: quando questo è selezionato dall'utente, viene annunciata prima la sua etichetta testuale, poi la descrizione che abbiamo associato.

Per la descrizione, però, non possiamo usare un testo.
Dobbiamo invece referenziare attraverso un **id** un altro elemento della pagina.

~~~html
<label for="password">Password</label>
<input type="password" id="password" aria-describedby="fumetto-password"/>
<p class="fumetto" id="fumetto-password">Lunghezza minima 8 caratteri, simboli consentiti - e _</p>
~~~

Il fumetto viene mostrato tramite uno script all'utente.
Siccome possiede un id lo possiamo anche referenziare con *aria-describedby*, in modo che il suo contenuto sia letto insieme all'etichetta del campo.

Ecco come appare quindi il nostro campo password ad un utente non-vedente.

> Password campo Lunghezza minima 8 caratteri simboli consentiti trattino e trattino basso



## Posso usare un elemento nascosto per la descrizione?

Sì, anche se l'elemento è reso invisibile tramite CSS può essere comunque raggiunto ed utilizzato per la descrizione.

{{% notice note "Nota bene" %}}
Normalmente nascondendo con il CSS un elemento, le tecnologie ausiliarie tendono ad ignorarlo.
{{% /notice %}}
