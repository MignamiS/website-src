+++
date = "2017-10-22"
title = "Come"
featureimage = ""
menu = "navbar"
disableComments = true
+++

# Come le persone con handicap navigano un sito web

Questa pagina contiene una panoramica sulle strategie con cui le persone con handicap interagiscono con le pagine web.
Sebbene io sia nell'ambito dell'accessibilità da alcuni anni conosco principalmente le problematiche legate alle **difficoltà visive**.
Va inoltre tenuto conto che non tutti utilizzano le stesse modalità: ciò che per un utente può essere un vantaggio, per un altro può essere una distrazione o addirittura un ostacolo.

Ecco le principali categorie di difficoltà che si possono riscontrare negli utenti:

- Difficoltà visive, come miopia, ipovedenza, fotofobia, cecità, ecc.
- Difficoltà uditive, come incapacità di percepire determinate frequenze, sordità profonda, ecc.
- Difficoltà motorie, come una tendinite, fratture, distrofie muscolari, ecc.
- Problemi cognitivi che possono andare da dislessia, deficit di memoria o di attenzione, epilessia, autismo, ecc.



## Le tecnologie assistive

Esistono diverse tipologie di programmi e dispositivi che permettono di sopperire ad eventuali mancanze di una persona.
Non bisogna però pensare che grazie ad una tecnologia un utente sia perfettamente uguale agli altri: basti pensare ad un semplice paio di stampelle. Una persona con una gamba rotta grazie ad esse può tornare a camminare, ma non lo farà come tutti gli altri e avrà bisogno di particolari accorgimenti per muoversi.
Allo stesso modo se un cieco utilizza una sintesi vocale non è detto che ci veda esattamente come tutti gli altri utenti del sito.

{{< fig src="img/trackball.jpeg" alt="Trackball" caption="Una trackball, simile ad un mouse ma più agevole da utilizzare per utenti con mobilità delle mani ridotta" >}}

Esiste una vasta gamma di prodotti per chi ha una mobilità ridotta, come mouse ergonomici, tastiere con tasti più grandi o con layout differenti e anche puntatori per interagire con un computer utilizzando la bocca o lo sguardo.
Per quanto riguarda le difficoltà uditive ci sono poi software di riconoscimento vocale per la trascrizione dei contenuti audio dei video.

### Ingranditori e screen reader

Per quanto riguarda le **difficoltà visive** esistono gli ingranditori che, come dice il nome, aumentano le dimensioni degli elementi sullo schermo in modo che siano più visibili.
Questi programmi solitamente possiedono funzionalità per modificare dettagli come l'aspetto del mouse, del focus di sistema e dei colori dello schermo.

{{< fig src="img/mouse-circle.png" alt="Cursore del mouse con un cerchio attorno ad esso per migliorarne la visibilità." caption="Gli ingranditori possono modificare vari aspetti del sistema per migliorarne la visibilità" >}}

Ci sono poi gli *screen reader*, conosciuti in italiano come "sintesi vocale", "lettore vocale" o anche col nome di "lettore di schermo".
Questi software lavorano a stretto contatto col sistema operativo e con i programmi, e leggono ad alta voce ciò che appare sullo schermo come finestre, bottoni, testi o pop-up.
Possiedono inoltre un mucchio di comandi da tastiera per attivare le funzioni più disparate: ad esempio per sapere che ora è posso premere la combinazione `CAPS LOCK + F12` una volta, due per il giorno e la data.
Quando poi si ha a che fare con un documento, come una pagina web, si può attivare un pannello contenente elenchi di elementi come link, intestazioni, sezioni o addirittura errori ortografici (nel caso di un documento Word).

{{< fig src="img/search-landmark-list.png" alt="Schermata di NVDA con l'elenco dei landmark di una pagina web" caption="Elenco di sezioni presenti in questo articolo, viste con gli occhi di uno screen reader" >}}

Uno screen reader possiede in genere un set di voci sintetiche che sono in grado di simulare una voce umana.
Spesso le persone che fanno uso di queste tecnologie portano la velocità di lettura a soglie elevate per compensare la mancanza della vista.

Ad esempio una persona parla con una velocità di circa 2 parole al secondo.
Un utente avanzato di uno screen reader può portare la velocità della voce fino ad **8 parole al secondo** riuscendo a capire perfettamente quanto sta leggendo.



## La navigazione tramite tastiera

Nei film capita di vedere l'informatico smanettone di turno che lavora con un computer utilizzando esclusivamente la tastiera.
Alcuni sostengono si tratti di pura finzione, nell'epoca del mouse chiunque utilizza il cursore per attivare funzionalità.
Eppure la tastiera è ancora il mezzo più utilizzato da diverse tipologie di persone, fra cui soprattutto persone con difficoltà visive e motorie.
Questo perché il mouse può essere difficile da impugnare, il cursore difficile da posizionare con precisione o addirittura impossibile da vedere.
Nel mio caso posso lavorare una giornata intera senza mai afferrare il mouse una volta.

Per muoversi si può utilizzare il tabulatore o le frecce, più qualche scorciatoia offerta dallo screen reader.
Per attivare le funzionalità di un bottone o di un link si può usare il tasto *invio* o la barra spaziatrice.
Il menu contestuale è attivabile grazie ad un tasto apposito, non presente in tutte le tastiere, oppure attraverso la combinazione `Shift + F10`.
Infine in menu start di Windows, attivabile attraverso il tasto apposito, fornisce un'ottimo punto di partenza per diverse operazioni, come lanciare un programma o muoversi velocemente nel computer.

Insomma, il mouse non è poi così fondamentale e molti lo considerano quasi una perdita di tempo, dato che le funzioni attivate tramite la tastiera sono più rapide.
Perché un utente possa navigare in un sito web è però necessario un prerequisito importante: **tutte le funzionalità devono essere raggiungibili e attivabili tramite la tastiera**.




## Le principali barriere del web

Senza andare nel dettaglio, perché ognuno di questi punti meriterebbe un articolo a parte, ecco una lista non esaustiva delle principali barriere che le persone possono incontrare nel web:

Semantica inesistente
:	Le tecnologie assistive sono in grado di riconoscere gli elementi di una pagina in quanto sono semanticamente identificati. Ad esempio un link "dice" chiaramente "io sono un link". Ma quando uno sviluppatore, per necessità, costruisce nuovi elementi emulando quelli esistenti spesso si dimentica di segnalarli in modo adeguato. Visivamente, ad esempio, uno *span* si comporta come un bottone, ma per una macchina resta sempre uno *span*, anche se ha l'animazione che si attiva al click.

Contrasto troppo debole
:	Quando il colore di sfondo e dell'elemento non hanno sufficiente luminosità di contrasto sono difficili da scorgere. Ad esempio un testo di colore grigio chiaro su di uno sfondo bianco non supera il valore minimo richiesto per una buona leggibilità.

CAPTCHA
:	La verifica che l'utente non sia in realtà un robot spammer è una spina nel fianco. È vero esiste la versione audio per chi ci vede poco, ma può non essere comunque sufficiente per quelle persone che sono anche deboli di udito.

Immagini senza testo alternativo
:	Il testo alternativo descrive il contenuto visivo dell'immagine. Se questo è mancante l'utente con problemi di vista potrebbe non comprendere l'informazione che questa veicola.

Audio senza trascrizione
:	Senza dei sottotitoli o una trascrizione testuale una persona con difficoltà uditive potrebbe avere problemi nel capire un video o un podcast.

No keyboard no party
:	Per il motivo visto sopra, se una funzionalità è utilizzabile solo tramite il mouse un utente che utilizza la tastiera come mezzo di navigazione non potrebbe farne uso.

La trappola del focus
:	Altro problema in cui incorrono tutti quegli utenti che fanno uso della tastiera per muoversi in una pagina: quando manipolando il focus attraverso uno script può succedere di farlo restare intrappolato in un ciclo dal quale l'utente non può uscire se non chiudendo la pagina.

Cambio di contesto non voluto
:	In generale qualsiasi cambio di contesto non deve essere automatico, ma deve essere l'utente stesso ad attivarlo. Ad esempio il refresh della schermata con la posta in arrivo di un web-client di posta elettronica potrebbe causare confusione in un utente che non ci vede.

Animazioni e lampeggiamenti
:	In generale le animazioni tendono a distrarre gli utenti, soprattutto coloro che hanno dei deficit di attenzione. Ecco perché sarebbe bene evitare, ad esempio, banner pubblicitari animati. nel caso dei lampeggiamenti è inoltre fondamentale evitare che abbiano una frequenza superiore alle 3 volte al secondo, che potrebbero evitare traumi a persone affette da epilessia.

