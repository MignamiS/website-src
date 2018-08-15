---
title: "Le molte facce dello stesso campo"
date: 2018-04-11T11:56:02+02:00
draft: false
tags: ["input", "form", "mobile", "validazione"]
categories: ["articoli"]
---

Html5 ha introdotto nuovi tipi di input, perfettamente retro-compatibili e assolutamente da provare.

<!--more-->

Invece di utilizzare il solito `<input type"text"/>`, si possono usare questi (ancora sconosciuti) input, che presentano tre benefici interessanti:

In primo luogo sono **auto-validanti**, cioè se viene inserito un valore scorretto provvedono ad avvisare l'utente in maniera accessibile.

In secondo luogo, se invece del campo di testo viene proposto un widget, questo è solitamente già **accessibile** (feedback vocali, utilizzabile tramite tastiera, ecc.).

Il terzo beneficio, per gli utenti mobile, lo vediamo dopo: ora ecco una carrellata di questi nuovi tipi di input:

color
:	permette di inserire un colore: In alcuni browser viene mostrato il color-picker di sistema.

date
:	per inserire una data (giorno-mese-anno). In alcuni browser appare il calendario di sistema.

email
:	per indirizzi email.

file
:	Permette di selezionare un file da caricare. Il pulsante "sfoglia" è tradotto automaticamente nella lingua di sistema.

month
:	Fornisce all'utente un campo per inserire mese e anno. Firefox al momento lo implementa come un campo di testo semplice, Google Chrome fornisce un widget più complesso, con elenco predefinito.

number
:	Uno spin per inserire valori numerici.

range
:	Fornisce uno slider per selezionare un valore compreso fra un minimo ed un massimo.

tel
:	Per inserire numeri di telefono.

url
:	Per URL. Alcuni browser possono anche validarlo.

Ecco l'
[elenco dei tipi di input](https://www.w3schools.com/html/html_form_input_types.asp)
.
Per alcuni tipi è anche possibile specificare dei vincoli, come un valore massimo o minimo, e addirittura un pattern regex per validare una sequenza complessa.

Esempio pratico:

~~~html
<input type="email" ... />
~~~


Quindi d'ora in avanti, quando dovrai richiedere un input all'utente, consulta questo elenco per vedere se non esiste già un campo adatto.



## Perché l'utente mobile è avvantaggiato se uso questi tipi di input?

Semplicemente perché, a dipendenza del campo, selezionandolo appare la tastiera adatta a compilarlo.

Per esempio la tastiera *email* ha già a portata di dito diversi simboli utili, come la "@" o il ".com".
Per l'input *number*, invece, appare la tastiera numerica che ha le 10 cifre belle in grande, senza lettere.

Una comodità che non puoi far mancare ai tuoi utenti!
