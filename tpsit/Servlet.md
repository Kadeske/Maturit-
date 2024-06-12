
### Cosa Sono le Servlet
Le servlet sono componenti software scritti in Java che vengono eseguiti su un server web per generare contenuti web dinamici. Sono gestite da un container, che le carica, esegue e gestisce il loro ciclo di vita. A differenza delle CGI, le servlet vengono caricate una sola volta e possono gestire più richieste tramite multithreading, offrendo un approccio più efficiente e portabile.

### Quando Usarle
Le servlet sono utilizzate per creare applicazioni web interattive e dinamiche. Sono ideali quando si necessita di:
- Gestire richieste e risposte HTTP.
- Interagire con database.
- Implementare logiche di business lato server.
- Mantenere la sessione dell'utente.

### Vantaggi e Svantaggi
#### Vantaggi
- **Efficienza:** Caricate una sola volta e poi gestite tramite thread.
- **Portabilità:** Scritte in Java, eseguibili su qualsiasi server web con JVM.
- **Sicurezza:** Maggiore controllo sulla gestione delle sessioni e sulla sicurezza delle applicazioni.
- **Integrazione:** Facile integrazione con altri componenti Java come JSP e EJB.

#### Svantaggi
- **Dipendenza da Java:** Necessitano di conoscenze approfondite di Java.
- **Performance:** Potenzialmente meno efficienti rispetto a soluzioni native per il server.
- **Complexity:** La configurazione e gestione può essere complessa, specialmente per applicazioni di grandi dimensioni.

### Struttura
Una servlet è una classe Java che estende `HttpServlet` e implementa metodi come `doGet()` e `doPost()` per gestire le richieste HTTP. La gerarchia delle classi servlet include:
- `Servlet`
- `GenericServlet`
- `HttpServlet`

Il codice base di una servlet include l'implementazione dei metodi `doGet()` e `doPost()` per gestire rispettivamente le richieste HTTP GET e POST.

### Ciclo di Vita
Il ciclo di vita di una servlet è gestito dal container e include tre fasi principali:
1. **Inizializzazione (`init()`)**: Il container chiama questo metodo una volta, quando la servlet viene caricata per la prima volta.
2. **Esecuzione (`service()`)**: Gestisce le richieste e invoca i metodi `doGet()` e `doPost()`.
3. **Distruzione (`destroy()`)**: Chiamato quando il container rimuove la servlet dalla memoria.

### Deployment
Il deployment di una servlet include la configurazione e posizionamento dei file necessari all'interno di una struttura specifica:
- **Root Directory:** Contiene i file HTML e JSP.
- **WEB-INF Directory:** Contiene il file `web.xml` (Deployment Descriptor), la cartella `classes` per i file `.class` delle servlet, e la cartella `lib` per eventuali librerie `.jar`.

#### Esempio di Struttura:
```
webapps
└── <nome_applicazione>
    ├── index.html
    └── WEB-INF
        ├── web.xml
        ├── classes
        │   └── <nome_servlet>.class
        └── lib
            └── <librerie>.jar
```
Per eseguire l'applicazione, si può accedere tramite il browser all'URL:
```
http://localhost:8080/<nome_applicazione>/index.html
```
oppure direttamente alla servlet:
```
http://localhost:8080/<nome_applicazione>/servlet/<nome_servlet>.class
```

