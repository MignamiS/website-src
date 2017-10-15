+++
date = "2017-10-11"
tags = ["tabelle", "layout", "role"]
title = "Il Medioevo dell'impaginazione"
+++

Nei "secoli bui" del web, quando ancora struttura e stile condividevano lo stesso documento, venivano usate le tabelle per gestire il layout della pagina.
Ancora oggi si possono trovare porzioni di pagina che utilizzano una tabella per posizionare gli elementi secondo un certo schema.

Siccome queste abitudini sono dure a morire ecco qualche consiglio su come gestire al meglio queste situazioni dal punto di vista dell'accessibilità.


<!--more-->

Con l'introduzione dei *div* la pratica di gestire il layout delle pagine tramite tabelle è caduta in disuso.
Tuttavia restano alcune parti, come i form, dove per comodità vengono ancora utilizzate per allineare i campi e semplificarsi la vita.

Contrariamente alla provocazione nel titolo del post, questo articolo non è stato scritto per polemizzare sul fatto che sia meglio, o meno, adoperare questo sistema.
Può capitare che ci si trovi a dover adoperare del legacy code e che non sia possibile convertire in tempo utile una serie di pagine utilizzando i container di HTML.
Come fare per rendere accessibile la pagina?

È opportuno distinguere fra [tabelle destinate ai dati]({{< ref "tabelle-intestazione.md" >}})
e quelle destinate invece ai **layout**.
Le prime contengono, appunto, dei dati e sono strutturate in modo da dichiarare esplicitamente all'utente che naviga con uno screen reader, in che riga e colonna si trova.
Quando egli si muove in una nuova cella viene annunciato il nome della colonna prima del suo contenuto.

Per quanto riguarda le **tabelle destinate al layout**, si tratta invece di ottenere l'effetto opposto, cioè **nascondere all'utente il fatto che si trovi in una tabella**.
Ad esempio nel caso di un form la posizione del cursore viene determinata non tanto dalla colonna, bensì dall'etichetta associata.
Se non agissimo in questo modo l'utente si sentirebbe dire:

{{< screen_reader "Colonna 1 nome utente, colonna 2 campo di testo vuoto, colonna 1 password, ..." >}}

Sebbene possa sembrare un'agevolazione, in caso di form più complessi la situazione diventa insostenibile, soprattutto nel caso di celle fuse insieme.




## Nascondere la tabella all'utente

Se mediante il CSS è possibile nascondere una tabella visivamente, è necessario farlo anche in codice in modo che gli screen reader non annuncino la posizione del cursore.
Ecco un esempio di layout gestito tramite una tabella:

{{< fig src="img/tabella-layout-example.png" alt="Una tabella contenente i campi nome utente e password" caption="Un form in una tabella, le celle tratteggiate sono invisibili" >}}

Per fare ciò è necessario **evitare di inserire l'intestazione**.
Grazie ad un algoritmo lo screen reader si accorge da solo che si tratta di una tabella destinata a posizionare gli elementi sullo schermo e si muoverà nelle colonne "silenziosamente", senza cioè rendere partecipe l'utente che sta in realtà navigando in una tabella.

La tabella presenta una struttura che è valida solo per chi può vederla con i propri occhi. Ecco quindi perché è utile nascondere la sua presenza alle tecnologie assistive.
Per rinforzare il ruolo di **presentazione** della tabella esiste un [ARIA role](https://www.w3.org/TR/wai-aria/roles#presentation):

~~~html
<table role="presentation">
~~~




## Conclusioni

Le tabelle destinate a impaginare degli elementi sono esclusivamente appannaggio della presentazione di una pagina.
Essendo integrate nel codice e non nel CSS è pertanto necessario **nasconderle** alle tecnologie che si appoggiano al DOM per descrivere i contenuti di una pagina, in modo che vengano ignorate.

Evitando di includere la header e utilizzando l'ARIA-role "presentation" è possibile suggerire agli screen reader che la tabella ha solo un fine estetico.
Non bisogna ovviamente dimenticarsi di rendere accessibile il contenuto delle celle!


## Articoli correlati

- Altre informazioni sulle [tabelle di dati]({{< ref "tabelle-intestazione.md" >}})
