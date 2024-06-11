
**HTTPS** utilizza **TCP/IP** insieme a **SSL** (Secure Sockets Layer, crittografia) e **TLS** (Transport Layer Security, autenticazione). Trasmettono dati usando un algoritmo di cifratura a chiave simmetrica (**AES**) con chiave generata da una delle due parti con algoritmo a chiave asimmetrica (**RSA**).

Questo permette solo al client e al server di conoscere il contenuto e impedisce a terze parti di manomettere i contenuti. Solo il server è autenticato, il browser rimane anonimo. Questo serve al client e all’utente, il browser valida il certificato del server verificando la firma digitale con cifratura a chiave pubblica.

**TLS** offre un’autenticazione bilaterale, richiedendo che anche il client possieda un certificato digitale.

---

## Autenticazione

**L’autenticazione** è il processo che consente di stabilire se un client è idoneo per l’accesso a una risorsa. L’autenticazione tramite browser avviene in 3 fasi:

1. Chiede **username** e **password**;
2. Genera un **header** con le credenziali di accesso;
3. Utilizza quell’header per tutte le successive richieste di accesso alle risorse.

---

## Tecniche per Restringere le Trasmissioni HTTP ai Soli Utenti Autorizzati

### Filtro su un Set di Indirizzi IP

- Detta anche **IAAF** (IP Address Auth Filter), utilizza l’indirizzo **IP** per identificare il client.
- Questo blocco può essere aggirato utilizzando l’**IP spoofing**, che falsifica il campo **Source Address** con un IP fasullo.

### HTTP Basic Auth

- Il server può rifiutare una transazione richiedendo all’utente di identificarsi (con **username** e **password**).
- Se l'autenticazione è positiva, la risorsa viene inviata; altrimenti, viene ripetuta un’altra sezione di challenge-response.

### HTTP Digest Auth

- Il server utilizza solo una **digest** della password per l'autenticazione.
- Per calcolare il digest, si usano funzioni di **hashing**.
- Risolve il problema dell’invio della password in chiaro.