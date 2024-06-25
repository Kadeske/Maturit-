# Socket e Protocolli per la Comunicazione di Rete

## Applicazione di Rete

### Cos'è?

Un'applicazione di rete è costituita da un insieme di programmi eseguiti su due o più computer contemporaneamente. Questi operano interagendo tra loro, usando risorse comuni mediante la rete di comunicazione che li connette. 

L’applicazione di rete è anche chiamata **applicazione distribuita** perché non viene eseguita su un solo elaboratore.

> Un’applicazione distribuita è composta da più elementi cooperanti in esecuzione su macchine diverse all’interno della stessa rete.

## Protocollo di Comunicazione

### Cos'è?

Il **protocollo di comunicazione** è l’insieme delle regole di comunicazione che devono essere imposte a due o più macchine connesse tra loro per comprendersi. È come essere più persone nella stessa stanza che parlano la stessa lingua: il protocollo di comunicazione è una 'lingua' per calcolatori.

### Cosa Fa?

Il protocollo di comunicazione stabilisce tutti gli aspetti della comunicazione, dai più fisici (es. supporto fisico) ai più logici (es. regole di codifica).

### Come Sono Organizzati?

I protocolli utilizzati dai calcolatori sono organizzati secondo una gerarchia, in cui ogni protocollo si 'appoggia' a un protocollo di livello più basso per fornire un servizio di qualità superiore.

## Porte di Comunicazione e Socket

### Da Sapere

Un processo (presente su un host) per poter comunicare con un qualsiasi host, deve identificare il processo destinatario in modo univoco.

### A Cosa Servono le Porte Logiche?

Le porte logiche permettono di ricevere ed inviare dati in modo corretto a più host per calcolatore, nonostante ogni calcolatore abbia una sola porta fisica.

### Come Funzionano?

Ogni porta logica è identificata da un numero detto **port address**. In questo modo, per poter avere più comunicazioni contemporaneamente sulla rete, è sufficiente utilizzare porte logiche diverse. Il numero di porta è identificato con 2 byte, da 0 a 65.535, e identifica un particolare canale utilizzabile per la connessione.

### Convenzioni delle Port Address

- **Porte da 0 a 1023**: Riservate ad applicazioni particolari (es. HTTP, FTP, DNS, Telnet). Chiamate "well-known port numbers", possono essere usate solo da server in apertura passiva.
- **Porte da 1024 a 49.151**: Riservate a porte registrate, usate da alcuni servizi ma possono anche essere utilizzate dai client.
- **Porte da 49.152 a 65.535**: Libere per essere assegnate dinamicamente dai processi applicativi.

### Identificazione di un Servizio

L’identificazione di un servizio avviene combinando l’indirizzo IP della macchina nella rete e la porta logica utilizzata dal processo richiesto.

- **Indirizzo IP**: Indirizza il nodo su cui opera il processo desiderato.
- **Porta Logica**: Identifica la porta utilizzata dal particolare processo all’interno del nodo.

### Cos'è un Socket?

Il **socket** è il meccanismo con cui avviene l’identificazione univoca di un processo in esecuzione.

### Da Cosa è Composto un Socket?

Un socket è composto dalla coppia {indirizzo IP:numero porta}.

### A Cosa Serve un Socket?

Un socket consente di comunicare attraverso la rete utilizzando la pila TCP/IP, ed è parte integrante del protocollo. Le API (application programming interface) mettono a disposizione del programmatore tutti gli strumenti utili alla codifica della connessione e all’uso del protocollo di comunicazione.

## Socket e Processi Client

### Cosa Deve Fare il Client per Connettersi con un Server?

Il client, per connettersi con un server, deve conoscere il socket del server desiderato. Il client può utilizzare qualsiasi porta logica libera a patto che la comunichi al server per comunicare.

> Al server possono arrivare numerose richieste di connessione da client diversi sulla stessa porta, o richieste dallo stesso host su porte diverse.

## Famiglie e Tipi di Socket

### Cos'è una Famiglia di Socket?

Una famiglia di socket è l’insieme dei socket che utilizzano gli stessi protocolli sottostanti. Ogni famiglia ha un sottoinsieme di stili di comunicazione e un proprio formato di indirizzamento.

### Esempi

- **Internet Socket (AF_INET)**: Permette il trasferimento dati tra processi posti su macchine remote connesse tramite LAN o Internet.
- **Unix Domain Socket (AF_UNIX)**: Permette il trasferimento di dati tra processi sulla stessa macchina Unix.

### Tipi di Socket

- **Stream Socket** — Livello applicativo
- **Datagram Socket** — Livello applicativo
- **Raw Socket** — Usati nello sviluppo di protocolli, esulano gli obiettivi della trattazione.

## Stream Socket

### Che Tipo di Connessione Utilizza?

Utilizza una connessione sequenziale tipicamente asimmetrica, affidabile e full-duplex basata su stream di byte di lunghezza variabile.

### Come Funziona?

Ogni processo crea il proprio endpoint (es. creando l’oggetto socket in Java). Successivamente:

- Il server si mette in ascolto fino all’arrivo di una richiesta di connessione che esaudisce (es. tramite metodo `Socket.accept()` in Java) creando un nuovo socket dedicato alla connessione.
- Il client si mette in coda sul socket del server; quando viene ‘accettato’, crea implicitamente il binding con la porta locale.

## Datagram Socket

### Cosa Permette di Fare?

I datagram socket permettono lo scambio di dati senza connessione fissa tra i due host (UDP), mediante l’invio di datagrammi contenenti messaggi di dimensione variabile e indirizzo di provenienza. Non garantisce ordine o arrivo dei pacchetti, quindi si ha una comunicazione inaffidabile. Permettono di inviare da un socket a più destinazioni e ricevere su un socket da più sorgenti (modello 'molti a molti').

## Trasmissione Unicast e Multicast

### Unicast

L’unicast è la situazione "normale" di invio di un messaggio al mittente con l’eventuale inversione dei ruoli.

### Multicast

Il multicast è utilizzato per trasmettere informazioni a più host contemporaneamente (one-to-many), ad esempio nelle videoconferenze.

### Cosa è Necessario per Implementare un Sistema Multicast?

È necessario definire uno schema di indirizzamento dei gruppi ed un supporto che registri la corrispondenza tra gruppo e partecipante. Si può anche ottimizzare l’uso della rete in caso di invio di pacchetti ad un gruppo (tramite multicast router).

### Descrizione degli Indirizzi nel Multicast

- **Permanenti**: L’indirizzo multicast viene assegnato e rimane tale anche se in un certo momento non ci sono più partecipanti connessi. Sono detti well-known.
- **Temporanei**: Richiedono la definizione di un protocollo per evitare conflitti nell’attribuzione degli indirizzi ai gruppi.

### Comunicazione Multicast

La comunicazione multicast utilizza il paradigma connectionless per poter gestire più connessioni contemporaneamente.

> Il broadcast può essere visto come un multicast estremo, detto "one-to-all".