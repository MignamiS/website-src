---
title: "Inserire errori nel titolo della pagina è una cosa buona"
date: 2018-05-14T16:11:34+02:00
draft: false
tags: ["titolo", "title", "form", "validazione-form"]
categories: ["articoli"]
---

No, non sono diventato eretico né intendo suggerire comportamenti autolesionistici.

Durante la validazione di un form può davvero essere utile modificare il titolo della pagina, vediamo il perché.

<!--more-->

Il titolo della pagina è la prima cosa che viene letta dallo screen reader.
Per rendere attento l'utente che ha commesso degli errori nel form, possiamo usare questo canale per informarlo.

{{% notice note "Nota bene" %}}
Questo sistema funziona se la pagina viene **ricaricata**.
Se il form è validato dinamicamente con uno script, non è detto che l'utente ne sia informato.
{{% /notice %}}

Spesso i framework lato-server utilizzano il pattern della validazione sincrona; dopo che l'utente ha inviato il form contenente errori, la pagina viene ritornata con i campi da correggere contrassegnati.

L'utente con **difficoltà visive**, però, è costretto a scorrere tutti i campi cercando di capire cosa non ha funzionato, causando spesso frustrazione.
Possiamo rendere attento l'utente modificando il titolo della pagina.

Ipotizziamo che l'utente si stia registrando al nostro sito.
Il form chiede di inserire nome, cognome, email, password e conferma della password.

Immaginiamo che l'utente commetta un errore proprio in quest'ultimo campo, che sarà puntualmente segnalato da un messaggio, ad esempio "Errore, la conferma non corrisponde alla password inserita".
In fase di rendering della pagina da ritornare all'utente, possiamo cambiare il titolo come segue:

> Registrazione - 1 errore in Conferma password- MioSito.com

Ecco i principali benefici:

1. Inserendo la notifica dell'errore subito dopo il nome della pagina sarà letto come prima cosa quando la pagina viene caricata.
2. Il numero degli errori commessi informa sull'entità del problema e su quanti campi saranno da correggere.
3. Inserire il nome dei campi interessati aiuta a velocizzare le operazioni di correzione.

{{% notice note "Nota bene" %}}
Il titolo della pagina è modificato solo temporaneamente e dopo un'azione, non c'è pericolo per l'indicizzazione da parte dei motori di ricerca.
{{% /notice %}}
