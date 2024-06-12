**Architettura di Flynn (1972):**

- Basata su flusso delle istruzioni e dei dati.
- Combinazioni possibili:
    - **SISD (Single Instruction Single Data):** Esegue un programma alla volta in modalità sequenziale.
    - **SIMD (Single Instruction Multiple Data):** Elaborazione su più flussi di dati con un singolo flusso di istruzioni.
    - **MISD (Multiple Instruction Single Data):** Esecuzione di più istruzioni sullo stesso flusso di dati.
    - **MIMD (Multiple Instruction Multiple Data):** Flusso di istruzioni e dati multiplo.

**MIMD (Multiple Instruction Multiple Data):**

- Classificazione in base alla memoria:
    - **Memoria condivisa (Multiprocessor):** Comunicazione tramite variazione di bit e sincronizzazione degli accessi.
    - **Memoria privata (Multicomputer):** Comunicazione tramite scambio esplicito di messaggi.

### Cluster Computing

- Sistema costituito da nodi omogenei connessi da una rete locale ad alta velocità.
- **Caratteristiche:**
    - Potenza di elaborazione ad alte prestazioni.
    - Velocità di trasferimento dati.
    - Centralizzazione fisica delle macchine.
    - Presenza di un'applicazione di management.
- **Architetture possibili:**
    - Organizzazione gerarchica con un singolo nodo principale.
    - Organizzazione Single System Image con bilanciamento automatico del carico.

### Grid Computing

- Sistema distribuito di calcolo decentralizzato con nodi eterogenei disposti a griglia.
- Coordinazione della trasmissione di informazioni e risorse.

### Sistemi Distribuiti Pervasivi

- Nodi piccoli e mobili con connessioni di rete wireless.
- **Esempi:**
    - Sistemi domestici, assistenza sanitaria, reti di sensori.
- **Requisiti:**
    - Cambi di contesto, composizione ad hoc, facilità di configurazione, condivisione come default.

### Architetture Distribuite Software

**Architettura a Terminali Remoti:**

- Operazioni effettuate da un'unica unità centrale con terminali remoti privi di capacità di elaborazione.

**Architettura Client-Server:**

- I client hanno capacità di elaborazione e inviano richieste ai server.
- I server elaborano e rinviano le risposte.
- Possibilità di più server e client eterogenei.

**Architettura WEB-centric:**

- Applicazioni convertite al web con il server al centro del sistema.
- Computazione avviene nei server con gestione dei documenti in comune con i client.

**Architettura Cooperativa:**

- Basata su entità autonome che esportano e richiedono servizi secondo il modello a componenti.
- Standardizzazione delle modalità di offerta e richiesta dei servizi.

**Architettura Completamente Distribuita:**

- Collaborazione di gruppi di entità paritetiche che comunicano tra loro offrendo e richiedendo servizi.

**Architettura a Livelli:**

- Introduzione dei middleware per alleggerire il carico elaborativo dei serventi.
- **Scopi del middleware:**
    - Garantire interoperabilità delle applicazioni su diversi OS.
    - Permettere connettività tra servizi su piattaforme distribuite.
- **Funzionalità middleware:**
    - Servizi di astrazione e cooperazione, per applicazioni, amministrazione del sistema, comunicazione, ambiente di sviluppo applicativo.