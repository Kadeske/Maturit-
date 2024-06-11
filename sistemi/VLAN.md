
Le **VLAN** sono LAN realizzate utilizzando lo standard **802.1Q**.

- Lavorano al livello **2**.
- Ogni VLAN si comporta come se fosse una LAN separata dalle altre, inclusi i pacchetti di **broadcast**.
- La comunicazione interna tra VLAN è gestita al livello **2** mentre la connettività fisica al livello **3**.

### Caratteristiche

- Consentono una migliore manutenzione e modifica della infrastruttura di rete.
- Rimpiazzano lo spostamento fisico di cavi e PC attraverso strumenti software.
- Riducono il traffico isolando il broadcast, aumentando la sicurezza evitando accessi indebiti e migliorando le prestazioni e l’ampiezza di banda.

### Pro e Contro

**Pro:**
- **Isolamento del traffico**: migliora la sicurezza e la gestione della rete.
- **Facilità di gestione**: semplifica la gestione e la modifica della rete senza interventi fisici.
- **Migliori prestazioni**: riduce il traffico di broadcast, aumentando l’efficienza della rete.

**Contro:**
- **Vulnerabilità allo spoofing**: possono essere soggette a attacchi di spoofing attraverso errori di configurazione delle porte Trunk.
- **Complessità di configurazione**: richiedono una configurazione accurata per evitare errori di rete.

### Caratteristiche VLAN Port Based

- Utilizza i numeri delle porte per realizzare VLAN differenti, ogni porta viene chiamata **Access port**.
- È un metodo semplice ma meno sicuro; qualunque dispositivo fisicamente connesso farà parte di quella VLAN.

**Operazioni degli switch in una VLAN port based:**
- **Ingress**: il frame appartiene alla VLAN stessa e non ha bisogno di essere identificato.
- **Forwarding**: il frame può essere inviato solo su porte appartenenti alla stessa VLAN.
- **Egress**: determinata porta in cui passa il frame, può essere trasmesso senza modifiche.

### VLAN Tagged, Untagged e Ibride

#### VLAN Tagged (802.1Q)

- Permette di condividere una VLAN in più switch, modificando il formato del pacchetto aggiungendo 4 byte (**TAG**) che contengono più informazioni sulla VLAN.
- Ogni porta tagged è chiamata **trunk**.

**Operazioni degli switch in una VLAN tagged:**
- Quando un pacchetto (appartenente ad una VLAN) entra in una porta trunk, verranno aggiunti 4 byte di **TAG** (i quali indicano l’appartenenza alla VLAN). Se sta uscendo da una porta trunk, quei byte verranno rimossi.
- Se il pacchetto esce da una porta untagged, verrà privato del TAG.

**Formato del TAG:**
- **Primi 2 byte**: chiamati **TPI** (Tag Protocol Identifier), contengono il numero **EtherType**, che evidenzia il nuovo formato del frame.
- **Byte 3-4**: detti **TCI** (Tag Control Information), contengono il livello di priorità del frame.

**Porte tagged (trunk):**
- Se una porta è TAGGED, i frame trasporteranno le informazioni di TAG, che indica l'appartenenza ad una VLAN.
- Queste porte sono dette **trunk**, il loro link associato è detto **trunk link**.

#### VLAN Untagged (Access)

- I frame che passano per queste porte non trasportano TAG, sono dette **access port** (access link).

#### VLAN Ibride

- Le porte ibride possono accettare sia frame taggati che non taggati.
- Questo tipo di porta può essere utilizzato per configurazioni più flessibili in cui è necessario gestire più tipi di traffico.

### Protocollo VTP (Virtual Trunking Protocol)

Consente di configurare le VLAN in un solo switch che poi le distribuisce agli switch della rete (dotati di protocollo **802.1Q**).

---

## Inter VLAN

Si utilizza per comunicare tra più VLAN. La connessione tra router e switch deve avere tante interfacce quante VLAN. Ad ogni interfaccia appartiene un indirizzo **IP** appartenente ad una VLAN. Le porte connesse al router devono essere di tipo **access**.

---

## Router on a Stick

Si utilizza per comunicare tra più VLAN. Il router è connesso ad uno switch della LAN attraverso una sola interfaccia impostata in modalità **trunk**.

---

## Domande aggiuntive

### Digest

Un digest è il risultato di un algoritmo di hash monodirezionale che fornisce una rappresentazione univoca e di dimensione fissa dei dati.

### Native VLAN

La **native VLAN** è una VLAN di default a cui appartengono tutti i pacchetti non taggati. Non è necessario modificarla in contesti semplici.

### Challenge-Response

Il meccanismo di **challenge-response** è un metodo di autenticazione in cui una parte chiede una risposta specifica per un dato "challenge" (sfida). Questo metodo aumenta la sicurezza delle autenticazioni.

### Differenza tra PUT e POST

- **PUT**: crea una risorsa sul server, ad esempio caricando un file.
- **POST**: passa informazioni ad un'entità che le gestisce, senza necessariamente salvare i dati come una risorsa sul server.

---