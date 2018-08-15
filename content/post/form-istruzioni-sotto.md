+++
date = "2017-10-29"
tags = ["form", "usabilità", "etichette"]
title = "Campi e informazioni: il carro davanti ai buoi"
draft = true
+++

In questo articolo alcune considerazioni sul perché sia una cattiva idea mettere le informazioni sotto ad un campo di un form invece che da qualsiasi altra parte.

<!--more-->

Capita spesso di imbattersi in form la cui struttura è la seguente:

{{< fig src="img/form-info-sotto-errore.png" alt="Campo di un form, il testo dell'errore si trova sotto di esso" >}}

Per questioni di spazio e di estetica si ricorre talvolta a questa distribuzione, ma per ragioni di usabilità e accessibilità non è la soluzione migliore.
Nell'immagine è mostrato un errore durante la validazione del contenuto del campo, ma potrebbe trattarsi di qualsiasi altra informazione come ad esempio il numero di caratteri ancora disponibili o i vincoli di conformità di una password.


In primo luogo, nel caso di campi di testo, l'auto-completamento oscura il messaggio sotto di essi.
Per non parlare poi delle list-box che possono mostrare anche 5-6 suggerimenti per volta.
Un altro esempio la finestra di un *date-picker* solitamente appare sotto al campo, per cui nel caso di un sistema di prenotazione di un volo, eventuali informazioni sul limite di anticipo della data verrebbero oscurate.


In secondo luogo, nel caso mobile, è possibile che la tastiera a schermo venga posizionata proprio sotto al campo, nascondendo il resto della pagina.
Così facendo l'utente potrà vedere eventuali feedback solo cambiando elemento.


Infine, l'ordine degli elementi nel DOM implica anche l'ordine di lettura da parte di uno screen reader: ciò significa che le informazioni saranno lette solo dopo che l'utente avrà lasciato il campo.
Nel caso di un errore di inserimento ci potrebbe anche stare, ma se l'informazione riguardasse il numero massimo di caratteri e l'utente avesse scritto un commento troppo lungo, potrebbe anche prendersela a male per non essere stato avvertito prima.

Alcuni spunti per migliorare l'usabilità dei form:

- Quando possibile inserire le istruzioni **prima** del campo o addirittura prima del form stesso.
- Utilizzare l'attributo *aria-describedby* per inserire più informazioni su di un campo, senza appesantire l'etichetta.



## Esempio: le informazioni prima del form





## Esempio: utilizzare aria-describedby
## Esempio: utilizzare il CSS



## In conclusione

Quando si inseriscono delle informazioni, siano messaggi di errore o indicazioni, sarebbe buona cosa non inserirli sotto al campo.
Ecco ad esempio come:

{{< fig src="img/form-info-fianco.png" alt="Form per il login, l'errore è posizionato di fianco al campo" >}}

Ovviamente non è sempre possibile questo tipo di layout, soprattutto in ambito mobile dove lo schermo è più alto che largo.

Se dovessi costruire un form e fossi costretto a sottostare a questa restrizione, pur avendo poco spazio laterale, che soluzione adotteresti?
