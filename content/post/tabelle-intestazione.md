+++
date = "2017-10-06"
tags = ["tabelle", "semantica", "stile"]
title = "Una tabella senza intestazione è come una barca senza il timone"
+++

Rendere accessibile una tabella è semplice e bastano poche righe di codice.
Se si trascura questo dettaglio un elenco di dati può diventare un ammasso di numeri e scritte senza nessuna forma, completamente illeggibile.

In questo articolo approfondiremo le tabelle e il modo per renderle accessibili a tutti: dagli screen reader ai motori  di ricerca.

<!--more-->

Una tabella è composta, come minimo, da due parti: l'**intestazione** e i **dati**.
Prendiamo ad esempio questa [tabella sul Sistema solare](https://it.wikipedia.org/wiki/Sistema_solare)
che ho trovato su Wikipedia.

Pianeta 	| Distanza media (milioni di km)	| Perielio (milioni di km)
---------	| ------------------------				| --------------------------
Mercurio 	| 57,91 													| 46
Venere		| 108 														| 107,5
Terra 		| 149,6														| 147,1
Marte 		| 227,94													| 206,6

Le due parti sono ben definite e trovare la distanza media del nostro pianeta è solo questione di incrociare la riga della Terra con la colonna della distanza.
Ecco invece come appare una tabella non accessibile quando viene letta da uno screen reader.

{{< screen_reader "Pianeta Distanza media (milioni di km) Perielio (milioni di km) Mercurio 57,91 46 Venere 108 107,5 Terra 149,6 147,1 Marte 227,94 206,6 ..." >}}

Immagina di dover estrapolare lo stesso dato da una sequenza come questa...



## Come rendere accessibile una tabella

Per rendere accessibile una tabella è sufficiente aggiungere l'**intestazione** (*header*).
Grazie all'intestazione possiamo dare una forma ai dati anche se questi vengono letti sequenzialmente.
Questo perché uno screen reader è in grado di determinare programmaticamente l'etichetta associata alla cella che intende leggere, in modo da annunciare prima a quale colonna corrisponde.

Se ad esempio volessi trovare la distanza media di Venere nella tabella di prima, raggiungo la riga muovendomi verticalmente. Poi mi sposto a destra e la voce annuncia.

{{< screen_reader "Distanza media (milioni di km) 108" >}}

In questo modo anche tabelle enormi possono essere navigate con facilità.


### Il codice

Questo è il codice per generare la tabella con le informazioni dei pianeti:

~~~html
<table>
	<tr>
		<th>Pianeta</th>
		<th>Distanza media</th>
		<th>Perielio</th>
	</tr>
	<tr>
		<td>Mercurio</td>
		<td>57,91</td>
		<td>46</td>
	</tr>
	<tr>
		<td>Venere</td>
		<td>108</td>
		<td>107,5</td>
	</tr>
</table> 
~~~

La parte più importante è rappresentata dalla prima riga (*TR*): essa contiene le celle dichiarate come *TH*, cioè *table header*.
Questo permette di determinare programmaticamente:

1. La struttura della tabella, in questo caso **verticale**. In questo modo anche una macchina sarà consapevole che la prima colonna è composta da nomi di pianeti.
2. L'etichetta della colonna è "Pianeta" e verrà annunciata tutte le volte che un utente che naviga utilizzando uno screen reader ci entrerà.

Nota che non è necessario indicare come header anche la colonna dei pianeti: questo perché quando un utente si muove di riga in riga tenderà già a spostarsi nella prima colonna e saprà che, muovendosi lateralmente, i dati sono relativi a quello specifico pianeta.

Per quanto riguarda le **tabelle orizzontali** il discorso è analogo: cambia solamente l'ordine dei tag:

~~~html
<table>
	<tr>
		<th>Nome</th>
		<td>Alberto</td>
	</tr>
	<tr>
		<th>Cognome</th>
		<td>Lupo</td>
	</tr>
	<tr>
		<th>Età</th>
		<td>35</td>
	</tr>
</table> 
~~~

Questo codice produce una tabella di 2 colonne che, se navigata verticalmente risulta così annunciata:

{{< screen_reader "Nome Alberto Cognome Lupo Età 35" >}}

Maggiori [informazioni sulle tabelle](https://www.w3.org/WAI/tutorials/tables/one-header/) sul sito della W3c.



## Lo stile dell'intestazione

Aggiungere il tag **TH** permette di agevolare la creazione dello stile della tabella.
Non è necessario, infatti, attribuire classi differenti alla prima riga per poter modificare dimensioni o allineamento del font dell'intestazione.

Già per default le celle marcate come *th* hanno uno stile differente.
Inoltre avendo un tag diverso rispetto alle celle con i dati, è possibile sfruttarlo come selettore nel CSS.

~~~css
td {
  ...
}

th {
  ...
}
~~~




## Didascalia

Aggiungere una didascalia (*caption*) ad una tabella può essere conveniente: in primo luogo permette di agevolare gli utenti nell'interpretazione dei dati contenuti.
Questo si applica bene all'esempio dei pianeti: una delle colonne che non ho copiato, per semplificare l'esempio, conteneva un'unità di misura chiamata UA (Unità Astronomica).
Se avessi inserito la forma per esteso nell'etichetta della colonna, questa sarebbe risultata troppo lunga.

~~~html
<table>
	<caption>Elenco dei pianeti nel sistema solare con le rispettive distanze. L'unità di misura UA è un'abbreviazione per Unità Astronomica.</caption>
	...
</table>
~~~

Inoltre semanticamente è più corretto inserire le informazioni inerenti alla tabella nella didascalia.
Questo crea una relazione esplicita che è determinata programmaticamente da una macchina.
Siccome il tag *caption* si trova all'interno del tag *table* si crea una relazione di parentela fra il contenuto della tabella e della didascalia.

**Nota**: la didascalia deve contenere qualche manciata di parole, non paragrafi interi.
L'analisi e la spiegazione dei dati vanno messe nella pagina.

Infine per facilitare la comprensione della tabella sarebbe utile inserire la didascalia appena dopo l'apertura del tag *table*.
In questo modo verrà posizionata prima della tabella e non sotto di essa, dove sarà letta per ultima.

Queste informazioni si applicano anche al tag *figure*.




## Conclusioni

Una tabella senza header è poco accessibile e anche i motori di ricerca potrebbero soffrirne dato che non è possibile determinare programmaticamente le relazioni di questi dati.
Indicando semplicemente quale cella è l'intestazione della colonna permette di rendere un ammasso informe di dati una struttura ben organizzata e comprensibile.
