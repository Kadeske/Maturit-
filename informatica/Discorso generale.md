
([[Teoria del database]])
Un dato è la descrizione elementare della realtà. 

L'informazione è un dato interpretato in un determinato contesto.

Un **database** può essere visto come un insieme di informazioni logicamente collegate tra loro.
- E' **sicuro**: programmato per evitare danni accidentali, 
- **integro**: gli utenti autorizzati non devono poter provocare danni, 
- **consistente**: i dati devono essere significativi ed interpretabili, 
- **condivisibile**: sia applicazioni che utenti devono poter accedere agli stessi dati, 
- **persistente**: il suo tempo di vita non si limita al solo tempo di utilizzo, scalabile: deve poter essere ingrandito senza modificare o interrompere il suo funzionamento.

La [[Progettazione di un database]] parte dalla **Progettazione logica**, in cui vengono decise le tipologie di dati e i linguaggi da adottare, ed è seguita dalla **progettazione fisica**, la quale tratta la descrizione dell'organizzazione fisica dei file, nomi e tipologie dei campi.

Un [[Sistema informativo]] è un insieme di strumenti, procedure, risorse umane e materiali necessari per la gestione delle informazioni inerenti ad un'azienda.

Il [[Sistema informatico]] è la parte automatizzata del sistema informativo.

Un [[Archivio]] è un insieme organizzato di informazioni, ha il compito di memorizzare permanentemente dei dati al suo interno.

E' composto da **record**, ogni record ha al suo interno delle **informazioni**, *dette campi*.
L'*elenco dei campi* di un record è detto **tracciato del record**.
Per la sua **definizione** è necessario definire delle specifiche quali: *nome*, *supporto di memoria*, *elenco dei campi*, *dimensione massima*, *organizzazione tra informazioni*.

All'interno degli **archivi** i dati vengono *salvati a blocchi*, per effettuare meno accessi in memoria.

La **differenza** principale tra **archivi** e **database**, è che i dati all'interno dei database sono logicamente collegati tra loro.

Un grande problema delle basi di dati è la **ridondanza**, ovvero la ripetizione dello stesso dato in più punti.
Può causare *confusione* ed un *rallentamento* dato dalla memorizzazione di dati in più.

Per risolvere questo problema ci si affida alla [[Normalizzazione]], la quale propone un metodo per creare delle basi di dati senza Anomalie.
Si divide in 3 forme dette normali:
La **prima forma** dice che in una tabella deve essere *identificata una chiave primaria* ed ogni *campo* deve essere *atomico*; la **seconda forma** dice che nessun campo può *dipendere* da solamente una parte della chiave primaria, ma *dall'intera chiave*; la **terza forma** dice che non vi devono essere *dipendenze transitive*, ovvero un campo non deve dipendere da un altro campo non chiave.

I [[Vincoli di integrità]] si dividono principalmente in vincolo di chiave primaria e vincolo di chiave esterna.
Una **chiave primaria** è un attributo o un insieme di attributi che identificano in modo univoco un record all'interno di una tabella. Deve essere *univoca*, *non nulla* e *immutabile*.
Una **chiave esterna** è un campo (o più campi) utilizzato per unire più tabelle in modo logico.
Deve riferirsi alla chiave primaria della tabella a cui si riferisce.

Esistono altri due tipi di **[[Vincoli di integrità]]**: **impliciti** ed **espliciti**. 
I **vincoli impliciti** sono quelli dettati dalla struttura dei dati stessa, si dividono in vincoli di *chiave primaria*, ovvero le istanze di una tabella devono essere diverse tra loro; e *vincoli referenziali*, dato A che dipende da B, al variare di B varia anche A.
I **vincoli espliciti** riguardano la rappresentazione delle informazioni, sono create da chi gestisce la base di dati in base alle necessità.

La [[Progettazione di un database]] avviene in tre fasi: La **progettazione concettuale**, la quale si concentra sulla definizione delle entità necessarie e le relazioni tra esse; successivamente si crea un **modello logico relazionale**: una rappresentazione dettagliate del database non curante del DBMS che verrà utilizzato; infine si traduce in uno **schema fisico**: schema finale del database adattato al DBMS utilizzato.

La [[Realizzazione di un database]] si divide in due fasi: **progettazione logica**, in cui si trasforma l'*idea concettuale in idea logica*, analizzando le necessità; e **progettazione fisica**, in cui si tratta la *definizione delle strutture*, dell'*organizzazione fisica dei campi* , *definizione* dei *nomi* dei campi e delle *tipologie* di essi.

Il **[[DBMS (Database Management System)]]** è un sistema di gestione della base di dati, offre dei vantaggi quali l'**integrazione** (dati strutturati senza ridondanze), **indipendenza fisica e logica** e i**ntegrità dei dati**. Inoltre suddivide l'utenza che accede al database in: programmatori, utenti finali, utenti avanzati, amministratori. Per interagire con esso sono utilizzai dei **linguaggi specifici**: i linguaggi **DDL** per la definizione e i linguaggi **DML** per l'interazione.

La **[[Molteplicità]]** indica quante istanze di una tabella possono essere associate ad un altra tabella.
La **[[Partecipazione]]** indica l'obbligatorietà o no della presenza di un entità in una relazione.

Per evitare l'interruzione dell'elaborazione durante un guasto, si utilizzano delle tecniche dette [[Fault tolerance]], sono tecniche basate sulla ridondanza dei dati e si dividono in 3 tipologie:
- Mirroring: si copia l'intero supporto di memoria contenente i dati rilevanti;
- Duplexing: oltre alla copia del disco, viene fatta la copia dei controller del disco, anche le loro posizioni;
- Copia totale: effettua una copia dell'intero sistema, garantisce la continuità del lavoro davanti a qualsiasi guasto.

Una **transazione** è un insieme di istruzioni viste come una sola cosa.
Una transazione ha più stati: **begin**, **aborted**, **committed**, **partially committed**.

Le [[Transazioni]] hanno delle proprietà dette [[Proprietà ACID]]:
- **Atomicità**: le transazioni devono essere eseguite come un unica cosa;
- **Consistenza**: in nessuna fase devono interferire con l'integrità dei dati;
- **Isolamento**: due transazioni non devono mai entrare in conflitto;
- **Persistenti**: i dati dopo i commit devono essere salvati in modo permanente.



Possono essere gestite in maniera *sequenziale* o attraverso in *maniera concorrente*.
Nel primo metodo non si riscontrano problemi, ma le prestazioni sono decisamente troppo basse.

Nel secondo caso posso invece nascere delle [[Anomalie]].
Le possibili anomalie sono 4: **perdita di aggiornamenti**, avviene quando 2 processi aggiornano un processo, uno degli aggiornamenti viene ignorato; l**ettura fantasma**, quando si utilizza un dato aggiornato con uno non aggiornato; **letture sporche**, quando si legge un valore errato, dato dalla modifica da un altro processo durante l'esecuzione del primo; **letture inconsistenti**, quando, durante il processo, la lettura della stessa risorsa da due risultati diversi.

Per *prevenire queste anomalie* si utilizzano i [[Lock]].
La richiesta di lock viene effettuata da processi concorrenti, per ottenere il permesso di lettura e/o scrittura.
I **lock** si dividono in **Read** (di sola lettura), possono essere concessi a più utenti contemporaneamente, e **Write** (scrittura e lettura), sono concessi a un solo processo alla volta.
Il **locking a due fasi** avviene quando un processo richiede prima il read lock e successivamente il write lock.

Il **deadlock** è una situazione di stallo che avviene quando un processo è in attesa di una risorsa in uso da un altro processo. Si possono risolvere con dei timeout.


I [[Livelli di isolamento]] sono dei metodi utilizzati per impedire le anomalie.
Sono:
- *Read uncommitted*:
	- non offre protezioni;
	- una transazione può leggere dati non ancora committati, sporchi;
- *Read committed*:
	- blocca le dirty read;
	- una transazione può leggere solamente dati committati;
- *Repeated read*:
	- blocca le dirty read e le non-repeatable read;
	- una transazione leggera lo stesso valore della risorsa durante l'intera esecuzione;
- *Serializable*:
	- Difende da tutte le anomalie (dirty read, non-repeatable read, phantom read)
	- gestisce le transazione una alla volta
	- efficace ma limita la concorrenza dei processi
	

Le [[Stored routine]] si dividono in [[Stored Procedure]] e [[Stored function]]. I loro vantaggi sono: la **semplificazione** del **lavoro** dei programmatori, maggiore **sicurezza**, **riusabilità**, e **riducono il traffico** in rete.
Le [[Stored Procedure]] sono delle procedure chiamate tramite il *comando CALL*, non restituiscono un valore ma lo visualizzano Hanno inoltre una *elevata portabilità*.
Le [[Stored function]], come tutte le funzioni SQL, *restituiscono un valore* e sono utilizzate in altri comandi SQL.

I [[Trigger]] sono dei meccanismi che eseguono delle istruzioni quando una condizione viene soddisfatta. Hanno gli stessi vincoli delle [[Stored function]].
Sono utilizzati per mantenere l'**integrità referenziale** delle *tabelle* e dei loro *dati*, verificare la **validità dei campi**, **creare backup**.


