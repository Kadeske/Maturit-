#### Funzioni Principali di SSL/TLS

1. **Privatezza (Confidenzialità)**: 
   - Garantita attraverso algoritmi di crittografia a chiave simmetrica, che proteggono i dati durante la trasmissione, rendendoli illeggibili a chi non possiede la chiave di decodifica.

2. **Autenticazione**:
   - Assicura che le parti coinvolte nella comunicazione siano effettivamente chi dichiarano di essere. Utilizza la crittografia a chiave pubblica e meccanismi di certificazione per garantire che si stia comunicando con il server corretto.

3. **Affidabilità (Integrità)**:
   - Il livello di trasporto include un controllo sull'integrità chiamato MAC (Message Authentication Code), che utilizza funzioni di hash sicure per verificare che i dati non siano stati alterati durante la trasmissione.

#### Accoppiamento con Altri Protocolli

- **HTTPS** (HTTP + SSL/TLS): Utilizzato per proteggere dati sensibili trasmessi tra browser web e server.
- **S-HTTP**: Poco diffuso, incapsula dati HTTP per la sicurezza.
- **SMTPS/POPS/IMAPS**: Protegge il contenuto delle email durante l'invio e la ricezione.

### Protocollo TLS: Dettagli e Componenti

#### Struttura di TLS

TLS (Transport Layer Security) è un protocollo di livello 5 (sessione) che opera sopra il livello di trasporto. Si divide in due componenti principali:

1. **TLS Record Protocol**:
   - Opera a livello più basso, sopra un protocollo di trasporto sicuro (es. TCP).
   - Utilizzato per i protocolli del livello superiore, prende i dati dall'applicazione, li suddivide in blocchi, eventualmente li comprime, calcola il MAC, cifra tutto e trasmette il risultato.

2. **TLS Handshake Protocol**:
   - Autentica l'interlocutore e condivide le chiavi segrete.
   - Suddiviso in tre sottoprotocolli:
     1. **Handshake Protocol**: Responsabile della negoziazione dei parametri di sicurezza di una sessione.
     2. **Change Cipher Spec Protocol**: Notifica i cambiamenti nei parametri di cifratura.
     3. **Alert Protocol**: Permette di notificare eventuali situazioni di errore.

#### Parametri di Sicurezza

- **Connection end**: Specifica se l'entità è server o client.
- **Bulk encryption algorithm**: Indica i dati dell'algoritmo di cifratura, inclusi i parametri e la lunghezza della chiave.
- **MAC algorithm**: Indica l'algoritmo di autenticazione e i suoi parametri.
- **Compression Algorithm**: Indica l'algoritmo di compressione e i suoi parametri.
- **Master secret**: Sequenza di 48 byte condivisa tra gli interlocutori.
- **Client random**: 32 byte casuali generati dal client.
- **Server random**: 32 byte casuali generati dal server.

### Processo di Handshake TLS

La fase di handshake viene iniziata dal client e prevede i seguenti passi:

1. **Client --> Server**:
   - Messaggio di 'hello' per iniziare la sessione, proponendo la versione del protocollo e le cipher suite supportate.
   - Il server sceglie il protocollo e le opzioni presenti nella suite. In caso di disaccordo, si cerca un'intesa.

   Parametri necessari per la comunicazione:
   - **Session identifier**: Identifica la sessione, scelto dal server.
   - **Peer certificate**: Certificato X.509 dell'interlocutore (non obbligatorio).
   - **Compression method**: Algoritmo di compressione.
   - **Cipher spec**: Algoritmo di cifratura e autenticazione, con relativi parametri crittografici.
   - **Master secret is resumable**: Flag che indica se la sessione può essere riutilizzata per nuove connessioni.

2. **Server --> Client**:
   - Invio del certificato che attesta l'identità del server e la chiave pubblica.

3. **Client --> Server**:
   - Generazione della chiave di sessione casuale cifrata con la chiave pubblica del server, se il certificato è stato verificato correttamente.

4. **Server**:
   - Decifra il messaggio e ottiene la chiave di sessione, completando la fase di handshake.

### Sintesi

TLS definisce il **Record Protocol** per trasferire i dati dell'applicazione e stabilisce la sessione utilizzando l'**Handshake Protocol**. Il TLS Record Protocol si occupa di prendere i dati dal livello superiore, suddividerli in blocchi, calcolare il MAC, cifrare tutto e trasmettere il risultato in modo sicuro.