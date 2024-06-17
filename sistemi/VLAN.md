
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

**Operazioni degli switch in una VLAN basata su porta:**
1. **Ingress**: Il frame entra nello switch su una porta appartenente a una VLAN specifica e viene associato automaticamente a quella VLAN senza necessità di ulteriori identificazioni.
2. **Forwarding**: Il frame viene inoltrato solo alle porte dello switch che appartengono alla stessa VLAN di origine.
3. **Egress**: Il frame esce dalla porta specifica associata alla VLAN di appartenenza e può essere trasmesso senza ulteriori modifiche al frame stesso.

### VLAN Tagged, Untagged e Ibride

#### VLAN Tagged (802.1Q)

- Permette di condividere una VLAN in più switch, modificando il formato del pacchetto aggiungendo 4 byte (**TAG**) che contengono più informazioni sulla VLAN.
- Ogni porta tagged è chiamata **trunk**.

**Porte tagged (trunk):**
- Una porta ***trunk*** è una porta di uno switch configurata per trasportare traffico appartenente a più VLAN contemporaneamente.
- Se una porta è TAGGED, i frame trasporteranno le informazioni di TAG, che indica l'appartenenza ad una VLAN.
- Queste porte sono dette **trunk**, il loro link associato è detto **trunk link**.


**Formato del TAG:**
- **Primi 2 byte**: chiamati **TPI** (Tag Protocol Identifier), contengono il numero **EtherType**, che evidenzia il nuovo formato del frame.
- **Byte 3-4**: detti **TCI** (Tag Control Information), contengono il livello di priorità del frame.

**Operazioni degli switch in una VLAN tagged:**
- Quando un pacchetto con tag VLAN *x* entra in una porta <mark style="background: #ABF7F7A6;">tagged</mark> possono succedere due cose:
	- se la porta è <mark style="background: #ABF7F7A6;">tagged</mark> VLAN *X* il pacchetto viene fatto passare
	- altrimenti, se la porta è <mark style="background: #ABF7F7A6;">tagged</mark> VLAN *Y* il pacchetto viene scartato
- Il pacchetto dopo essere entrato su una porta <mark style="background: #ABF7F7A6;">tagged</mark> potrà essere inoltrato solo su porte (<mark style="background: #ABF7F7A6;">tagged</mark> o <mark style="background: #FF5582A6;">untagged</mark>) della stessa VLAN.
	- se esce da una porta <mark style="background: #ABF7F7A6;">tagged</mark>, sarà taggato come VLAN *x*
	- se esce da una porta <mark style="background: #FF5582A6;">untagged</mark> sarà privato del TAG.
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