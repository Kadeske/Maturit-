#### Cos'è un Firewall?

Un **firewall** è un sistema software, spesso con hardware dedicato, progettato per la **difesa perimetrale** di una rete. Il suo obiettivo è proteggere la rete interna filtrando il traffico di pacchetti in entrata e in uscita secondo regole predefinite. Generalmente è costituito da più macchine che lavorano insieme come un [sistema distribuito](Sistemi%20distribuiti).

#### Principi Fondamentali dei Firewall

1. **Punto Unico di Contatto**: Il firewall deve essere l'unico punto di contatto tra la rete interna e quella esterna.
2. **Autorizzazione**: Solo i pacchetti autorizzati possono attraversare il firewall.
3. **Sicurezza del Firewall**: Il firewall stesso deve essere un sistema altamente sicuro.

---

### Tipologie di Firewall

#### In base al tipo di protezione offerta:
- **Ingress Firewall**: Controlla i collegamenti in arrivo dall'esterno.
- **Egress Firewall**: Controlla i collegamenti in uscita, impedendo al traffico malevolo di uscire dalla LAN.

#### In base al numero di host protetti:
- **Personal Firewall**: Protegge il singolo host, di default consente qualsiasi traffico verso l'esterno e blocca quello in arrivo.
- **Network Firewall**: Posto tra la LAN e Internet, controlla tutto il traffico passante.

#### In base al livello di intervento:
- **Filtro di Pacchetto IP**: Blocca o abilita selettivamente il traffico e i protocolli in base all'indirizzo IP e alla porta indicata sul pacchetto.
- **Server Proxy**: Intrattiene le connessioni per conto di altri nella rete interna, agendo in base a IP, porta, connessione e contenuto dei pacchetti.

---

### Classificazione dei Network Firewall

1. **Packet-Filtering Router**: Opera a livello di rete, filtra i pacchetti in base alle informazioni IP.
2. **Circuit Gateway**: Opera a livello di trasporto, gestisce le connessioni a livello di circuito.
3. **Proxy Server**: Opera a livello di applicazione, ispeziona il contenuto dei pacchetti.

#### Access Control List (ACL)

Le regole di filtraggio dei pacchetti sono definite in liste chiamate **ACL**, basate su:
- **Indirizzo Sorgente/Destinazione**
- **Protocolli di Porta dei Livelli Superiori**

Due filosofie di base:
- **Open Security Policy**: Di default tutto è permesso, le ACL raccolgono i divieti.
- **Closed Security Policy**: Di default tutto è vietato, le ACL raccolgono gli accessi permessi (più adottata).

---

### Tipologie di Firewall Specifiche

#### Packet Filtering

**Vantaggi**:
- **Trasparenza**: L'utente non si accorge della presenza del firewall.
- **Velocità**: Meno controlli rispetto ad altri firewall.
- **Immediatezza**: Una sola regola può proteggere un'intera rete.
- **Gateway-Only**: Non richiede configurazioni per i client.
- **Topologia Interna Invisibile**: Dall'esterno è visibile solo il gateway.

**Svantaggi**:
- **Basso Livello**: Non può elaborare informazioni da livelli superiori.
- **Mancanza di Servizi Aggiuntivi**: Non gestisce autenticazione o filtraggio di URL.
- **Logging Limitato**: Poche informazioni nei log.
- **Vulnerabile allo Spoofing**: Filtra solo in base alla provenienza.
- **Testing Complesso**: Prove di funzionamento lunghe e complicate.

---

#### Firewall Stateful

**Vantaggi**:
- **Buon Rapporto Prestazioni/Sicurezza**: Controllo sulla connessione più sicuro.
- **Protezione da IP Spoofing e Session Hijacking**: Migliore controllo sulla connessione.
- **Tutti i vantaggi del Packet Filtering**

**Svantaggi**:
- **Protocollo Unico**: Difficile da usare in altre infrastrutture di rete.
- **Servizio di Auditing Limitato**: Dati nei log ancora insufficienti.
- **Mancanza di Servizi Aggiuntivi**
- **Testing Complesso**

---

#### Proxy Firewall

**Vantaggi**:
- **Controllo Completo**: Doppio controllo sul contenuto dei pacchetti.
- **Log Dettagliati**: Include informazioni del livello applicativo.
- **Nessuna Connessione Diretta**: Tutti i dati sono analizzati e ricostruiti.
- **Sicurezza in Caso di Crash**: La LAN rimane isolata.
- **Supporto per Connessioni Multiple**: Gestisce più connessioni per applicazione.
- **User-Friendly**: Più semplice da configurare.
- **Autenticazione e Filtraggio Contenuti**
- **Cache**: Riduce il traffico inutile.

**Svantaggi**:
- **Poco Trasparente**: Richiede configurazioni specifiche per ogni PC della LAN.
- **Richiede un Proxy per Ogni Applicazione**
- **Basse Performance**: Richiede molta elaborazione dalla CPU.

---

#### Bastion Host

Un **bastion host** è un host critico per la difesa della rete interna, spesso associato a un packet filter.

**Caratteristiche**:
- Unico calcolatore della rete interna raggiungibile dall'esterno.
- Software essenziale, privo di bug utilizzabili.
- Proxy server in ambiente isolato (chrooting).
- File system a sola lettura.
- Minimo di servizi e nessun account utente.
- Salvataggio e controllo dei log.
- Eliminazione dei servizi non fidati e disattivazione del source routing.

---

#### DMZ (Demilitarized Zone)

Una **DMZ** è una zona della rete che separa la rete interna da quella esterna, fornendo sicurezza perimetrale.

**Caratteristiche**:
- Servizi della DMZ accessibili dalla rete pubblica ma non fidati dalla rete privata.
- Protezione della rete interna da eventuali compromissioni dei servizi DMZ.
- La DMZ si pone tra la LAN interna (privata e protetta) e la WAN esterna (Internet e sedi remote connesse).