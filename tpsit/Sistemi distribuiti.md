
#### Sistemi Centralizzati vs. Sistemi Distribuiti
**Sistemi Centralizzati:**

- Applicazioni e dati risiedono in un unico nodo elaborativo.
- Le applicazioni girano su un singolo processore o host.

**Sistemi Distribuiti:**

- Applicazioni costituite da più processi cooperanti eseguiti in parallelo da unità di elaborazione autonome.
- Un sistema è distribuito se presenta almeno una delle seguenti caratteristiche:
    - **Elaborazione distribuita:** Applicazioni risiedono su più host cooperanti.
    - **Base di dati:** Informazioni ospitate su più host.

Non esiste una definizione univoca di sistema distribuito, ma esempi includono:

1. Un insieme di macchine collaboranti percepite come una singola entità dall'utente (Tanenbaum).
2. Un sistema di componenti hardware e software collegati che comunicano solo tramite messaggi (Coulouris e Donnimore).
3. Un sistema in cui il fallimento di un singolo calcolatore può rendere inutilizzabile un altro calcolatore (Lamport).
4. Un insieme di applicazioni logicamente indipendenti che collaborano per un obiettivo comune attraverso hardware e software.

Ogni componente esegue un programma specifico in base al compito svolto e al proprio ruolo nella rete:

- **Client:** Utilizza servizi offerti da altre applicazioni.
- **Server:** Fornisce servizi ad altre applicazioni.
- **Actor:** Può agire sia da client che da server a seconda del contesto.

Differenza tra sistemi distribuiti e paralleli:

- **Sistemi Distribuiti:** Insieme di computer indipendenti che comunicano e possono cooperare.
- **Sistemi Paralleli:** Insieme di computer che comunicano e cooperano per risolvere problemi di grandi dimensioni.

### Classificazione dei Sistemi Distribuiti

**Famiglie di Sistemi Distribuiti:**

1. **Sistemi di calcolo distribuiti:** Configurati per il calcolo ad alte prestazioni.
    - **Cluster Computing:** Unione di PC omogenei tramite rete per parallelizzare il calcolo.
    - **Grid Computing:** Unione di PC eterogenei tramite rete.
2. **Sistemi informativi distribuiti:** Esempi includono il web e software aziendali.
3. **Sistemi distribuiti pervasivi:** Reti wireless e parte di sistemi più grandi (es. PAN, reti di sensori).

### Benefici dei Sistemi Distribuiti

**Affidabilità:**

- Grazie alla ridondanza, un SD può sopravvivere al guasto di un componente tramite algoritmi che sostituiscono le entità danneggiate.
- La difficoltà di questi algoritmi aumenta con l’autonomia delle entità.
- Classificazione:
    - **Accoppiamento debole:** Risorse controllate da un'autorità comune.
    - **Accoppiamento forte:** Risorse controllate da unità autonome che cooperano.

**Integrazione:**

- Capacità di integrare componenti eterogenei (hardware e software).
- Interfaccia uniforme con il sottosistema di comunicazione.

**Trasparenza:**

- Vedere il sistema distribuito come un singolo elaboratore.
- ANSA identifica 8 forme di trasparenza:
    - Accesso, locazione, concorrenza, replicazione, guasti, migrazione, prestazioni, scalabilità.

**Economicità:**

- Migliore rapporto qualità/prezzo rispetto ai sistemi centralizzati.
- Capacità di connettere sistemi legacy a basso costo.

**Apertura:**

- Favorisce l’interoperabilità, portabilità e ampliabilità attraverso protocolli standard.

**Connettività e collaborazione:**

- Condivisione di risorse comporta vantaggi economici e arricchisce ogni utilizzatore.

**Prestazioni e scalabilità:**

- Crescita del sistema con l’aggiunta di risorse e miglioramento delle prestazioni (scalabilità orizzontale).

**Tolleranza ai guasti:**

- Replicazione delle risorse per mantenere il sistema funzionante in caso di guasto (guasto parziale).
- Approcci:
    - Duplicazione completa delle risorse (costoso e rallentante).
    - Utilizzo di software di recupero.

### Svantaggi dei Sistemi Distribuiti

**Produzione di software:**

- Necessità di aggiornare costantemente le competenze dei programmatori.
- Evoluzione in tre tappe:
    - Standard TCP/UDP per comunicazione.
    - Architetture web per migliorare lo sviluppo software.
    - Diffusione del linguaggio Java e JVM.

**Complessità:**

- Maggiore complessità rispetto ai sistemi centralizzati.
- Richiede strumenti per interconnessione tra host e instradamento dei dati.

**Sicurezza:**

- Necessità di proteggere l’accesso ai dati e risorse da utenti non autorizzati.
- Protezione dall’intercettazione dei dati (sniffing).

**Comunicazione:**

- Richiede nuove tipologie di sistemi di telecomunicazione per migliorare la qualità del servizio.
- Imprevedibilità delle richieste genera situazioni di “casualità”.