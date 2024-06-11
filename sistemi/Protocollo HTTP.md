
**HTTP** è un protocollo che consente di **trasmettere risorse** fra server e client. <br>
Opera al **livello di applicazione**.

---
# Identificazione delle risorse


Le **risorse** sono identificate da un **URI** o un **URL**:

- **URI (Uniform Resource Identifier)**: set generico di nomi o indirizzi che rappresentano stringhe assegnate alle risorse.
- **URL (Uniform Resource Locator)**: termine informale, usato solo in specifiche particolari con protocolli popolari.
- **URN (Uniform Resource Name)**: sottoinsieme di URI che rimane persistente anche quando la risorsa non è più disponibile.

---

Un tipico indirizzo **URL** è formato da:

- **Schema**: definisce il protocollo;
- **Host**: identifica il server, può essere un nome simbolico o un indirizzo IP;
- **Porta**: è opzionale (80 per HTTP, 443 per HTTPS);
- **Path**: identifica la risorsa all’interno del server attraverso un percorso;
- **Query**: utilizzato per passare informazioni dal client al server;
- **Fragment**: indica un punto preciso all’interno di una risorsa.


---
# Utilizzo delle sessioni

**HTTP** utilizza le sessioni per comunicare: ogni sessione inizia connettendosi al server con **TCP** alla porta **80**, poi il client invia una richiesta che contiene un **URL**. Il server risponde e chiude la connessione immediatamente.

- Il server rimane in ascolto sulla **porta 80**
- Il client apre una connessione **TCP** sulla **porta 80**
- Il server accetta la connessione
- Il client invia una richiesta
- Il server invia la risposta al client
- Il server chiude la connessione (solo in **HTTP 1.0**)

# Versioni
## --> HTTP 1.0

**HTTP 1.0** è detto protocollo **stateless** perché né client né server mantengono informazioni sui messaggi scambiati in precedenza. Dopo ogni risposta, il server chiude la connessione.

---
## --> HTTP 1.1

**HTTP 1.1** introduce diverse migliorie rispetto alla versione 1.0:

- Il server lascia la connessione **aperta** anche dopo aver inviato la risposta, permettendo comunicazioni successive sulla stessa connessione.
- È possibile **criptare i dati**.
- Attraverso il **pipelining**, il client può inviare molteplici richieste prima di terminare la ricezione delle risposte. Le risposte sono poi inviate in ordine.
- Nelle connessioni permanenti, il server chiude la connessione solo se si raggiunge il tempo di **timeout** o se il client si disconnette.

Esistono due tipi di connessioni permanenti:

1. **Incanalata**: la successione di richieste è memorizzata nella coda detta **pipeline**, le richieste vengono processate nello stesso ordine.
2. **Non incanalata**: il server accetta nuove richieste solo quando la precedente è stata esaudita.


---
# Messaggi e risposte HTTP

---
## Messaggi HTTP

I messaggi HTTP sono formati da:

- **Riga iniziale**: contiene la versione **HTTP** e il tipo di **richiesta**.
- **Header lines**: righe successive che contengono informazioni sul client e sulla richiesta. Gli header si concludono con una **riga vuota** e sono formati da una coppia di **nome** e **valore** separati da due punti.
- **Entity body**: contiene il corpo del messaggio (le risorse da trasmettere).

---

## Risposte HTTP

Le risposte HTTP sono molto simili ai messaggi HTTP, con alcune differenze:

- Contengono una **riga di stato** al posto della riga della richiesta.
- Comunicano più informazioni tramite i **codici di stato**.

---
# Metodi HTTP


I metodi HTTP sono attributi di una richiesta e rappresentano le intenzioni del client. I metodi sono necessari per conversare con il server.

Le **API per HTTP** consentono di eseguire operazioni sui dati presenti sui server. Le applicazioni **RESTful** usano le API per effettuare operazioni sui server.

---
#Operazioni-CRUD
# Operazioni CRUD (Create, Retrieve, Update, Delete)

Permettono di:

- **Chiedere dati al server (GET)**
- **Creare dati sul server (POST)**
- **Modificare o sostituire dati sul server (PUT)**
- **Eliminare risorse dal server (DELETE)**

---

### GET

- **Richiede una risorsa al server**
- La richiesta è di sola lettura, ma una volta ricevuta la risorsa il client è libero di utilizzarla.
- La risorsa può essere chiesta:
    - **In modo assoluto**
    - **Condizionale** (solo se soddisfatto un criterio nell’header)
    - **Parziale** (parte di una risorsa)

---

### PUT

- Chiede la memorizzazione sul server di una risorsa all’**URL** specificato.
- Permette di trasmettere informazioni da client a server. A differenza del **POST**, la risorsa viene creata.
- Il suo argomento è la risorsa da inserire.
- **Non è sicuro.**

---

### POST

- Utilizzato, per esempio, per inviare dati di un form ad un’applicazione.
- I dati vengono processati da un’entità apposita all’interno del server.
- **Non esistono limiti di lunghezza** nel POST.
- **Non è sicuro.**
- Nell’**URI** si indica un oggetto che possa processare i dati inviati.

---

### DELETE

- Si richiede l’eliminazione della risorsa all’**URI** specificata.
- Non c'è una garanzia che questa venga eliminata anche con codice 200.

---

### HEAD

- Variante di **GET** per testing e debugging.
- Il server risponde infatti solo con il codice di stato e senza né header né body.

---

### OPTIONS

- Usato per verificare le capacità di un server web.
- Può essere utilizzato anche dai client per determinare la versione di **HTTP** supportata.
- Permette di conoscere i metodi di codifica della risorsa stessa.

---

### TRACE

- Richiesta di diagnostica per la verifica da parte del client del percorso di rete che i messaggi seguono per raggiungere il server.
- Traccia una “strada” tra il client e il server.

---

### CONNECT

- È riservato all’uso con proxy per creare un tunnel sicuro, come nel caso di comunicazione **SSL**.

---
## Codici di Stato HTTP

- **100 - 199 (Information)**: forniscono informazioni temporanee alla richiesta durante il suo svolgimento.
- **200 - 299 (Successful)**: completamento di una richiesta con successo.
- **300 - 399 (Redirection)**: stati non di errore ma che richiedono un trattamento particolare dal browser.
- **400 - 499 (Client Error)**: errori del comportamento del client.
- **500 - 599 (Server Error)**: errori verificati nel server.