
Gli archivi sono utili per la memorizzazione permanente dei dati.

E' un insieme **organizzato di informazioni**, caratterizzate da alcune proprietà:
- hanno un **nesso logico** tra loro;
- sono rappresentate in un **formato interpretabile**;
- sono memorizzate in un supporto che permette **lettura e scrittura nel tempo**;
- organizzate per un **facile consulto**.

Le informazioni sono raggruppate in un **unità logica** detta **record**.

La singola informazione è detta **campo**.
L'**elenco dei campi** è detto '**tracciato del record**'.

Un **file** è un **insieme di record**, ovvero di informazioni logicamente omogenee.


## CREAZIONE DI UN ARCHIVIO

Analisi del problema, richiede la definizione delle seguenti specifiche:
- nome:
- elenco dei campi (tracciato del record);
- supporto utilizzato per la memorizzazione; 
- dimensione massima;
- organizzazione 'gerarchica?', come i dati sono strutturati e dipendenti tra loro.


## TRASMISSIONE A BLOCCHI

Ogni trasferimento di dati verso la memoria centrale non riguarda un singolo dato, ma un insieme di dati, detto blocco.
La dimensione del blocco è di qualche kb.

Utilizzato per ottimizzare l'accesso alla memoria.

## MEMORIZZAZIONE A BLOCCHI

Per le operazioni di trasferimento tra periferica e memoria centrale, il pc utilizza una zona di lavoro detta buffer di I/O.

Il blocco è l’unità fisica (o record fisico) di memorizzazione.
Un blocco può contenere più record logici.

Le operazioni di lettura/scrittura quindi riguardano gruppi di record, diminuendo così il numero di accessi alla periferica.

Oltre ai file con record a lunghezza fissa esistono file con record a lunghezza variabile;
è necessario specificare la posizione di termine di ogni singolo record.



