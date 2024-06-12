
Il modello **client-server** è costituito da un insieme di host server ed un insieme di host client. Tuttavia, non sono gli host ad essere server o client, ma i processi in esecuzione su di essi. Un host può avere più processi contemporaneamente, quindi può essere sia server che client.

Oggi il modello client-server è in grado di gestire applicazioni molto complesse, con le seguenti caratteristiche:

- **Molti utenti concorrenti** richiedono i servizi.
- **Logica applicativa** diversa.
- **Archivi di grandi dimensioni** con organizzazione complessa e distribuita.
- **Notevoli requisiti di sicurezza**.
- **Sistemi di transazione**.

## Schema Temporale

1. Il client manda una richiesta al server.
2. Il server (in attesa) riceve la richiesta.
3. Il server esegue il servizio richiesto.
4. Il server manda una risposta e degli eventuali dati.
5. Il client riceve la risposta e gli eventuali dati.

Queste attività avvengono in modo trasparente ad entrambi i processi. Questo meccanismo viene utilizzato sia nel caso in cui i processi si trovano su due calcolatori differenti sia sul medesimo.

## Esempi di Architetture Client-Server

- **[Telnet](Protocollo%20Telnet)**
- **[HTTP](Protocollo%20HTTP)**
- **[FTP](Protocollo%20FTP)**

## Distinzione tra Client e Server

Un programma **client** richiede dei servizi a dei programmi chiamati **server**. Un server è un programma che risiede su un computer chiamato **host**. Un server rimane in ascolto tramite un **socket** in una determinata porta, in attesa che un client invii una richiesta. Un client per comunicare con un server tramite il protocollo TCP/IP deve prima “connettersi” al suo socket specificando l’indirizzo IP e il numero della porta sulla quale il server è in ascolto.

## Comunicazione Unicast e Multicast

Esistono due tipi di comunicazione:

- **Unicast**: il server comunica con un solo client alla volta.
- **Multicast**: il server può comunicare con più client contemporaneamente.

## Livelli e Strati

Le architetture client-server sono organizzate a **livelli**. Ogni livello corrisponde ad uno o più nodi elaborativi del sistema. Ogni livello fa da server ai livelli precedenti e da client ai livelli successivi.

Solitamente è utilizzato insieme al modello a **strati**. Ogni strato è definito dal punto di vista funzionale, come un “livello di astrazione”.

Troviamo tre funzionalità principali:
- **Front-end (presentation tier)**: l’interfaccia vista dall’utente.
- **Logica applicativa (middle tier)**.
- **Back-end (data tier)**: gestisce l’accesso a risorse e dati.

### Presentation Layer (PL)

È costituito dall’insieme delle procedure dedicate alla presentazione dei dati all’utente.
*(mostra le interfacce belle)*

### Resource Management Layer (RML)

È composto dall’insieme delle procedure che gestiscono i dati.
*(tocca i dati)*

### Business Logic Layer (BLL) o Application Layer

Comprende la logica dell’elaborazione e le relazioni tra le risorse.
*(robe noiose e amministrazione)*

## Architetture

### Architettura a 1 Livello (1 Tier)

Non rientra nell’architettura client-server.
*(inventata prima dell’avvento dei sistemi distribuiti)*
Ha un solo mainframe al quale sono collegati terminali (stupidi) utilizzati per le operazioni I/O.

### Architettura a 2 Livelli (2 Tier)

Utilizza l’architettura client-server. Si dividono in:
- **Thin client**: il server è responsabile della logica applicativa e della gestione dei dati, il client è responsabile della grafica.
- **Thick client**: il server è responsabile della gestione dei dati, il client è responsabile della grafica e della logica applicativa.

### Architettura a 3 Livelli (3 Tier)

Utilizza l'architettura client-server. Ha tre livelli:
- **Front-end**
- **Middle tier**
- **Back-end**

**Vantaggi:**
- Prestazioni
- Facilmente scalabile
- Tollerante ai guasti
- Sicurezza facilmente gestibile

**Svantaggi:**
- Comunicazione lenta
- Progettazione difficile
- Sviluppo difficile
- Amministrazione difficile

### Architettura N-Tier

È una generalizzazione del modello client-server a tre livelli. Introduce livelli e server intermedi.