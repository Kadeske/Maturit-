
#### Cos'è una VPN?

Una **VPN (Virtual Private Network)** è una rete privata che utilizza segmenti di rete pubblica per trasmettere dati in modo sicuro e privato. Attraverso il processo di tunneling, i dati riservati vengono incapsulati e cifrati, rendendo i nodi della rete pubblica inconsapevoli del fatto che la trasmissione faccia parte di una rete privata.

---

#### Tunneling

**Tunneling**: Processo di trasmissione di dati riservati attraverso una rete pubblica.

- **Suddivisione dei Dati**: I dati vengono suddivisi in pacchetti e trasmessi nel tunnel fino alla destinazione.
- **Cifratura e Incapsulamento**: Durante il tragitto, i dati vengono cifrati e incapsulati.
- **Livelli di Tunneling**:
  - **Livello 2**: Livello di collegamento dati (Protocollo PPTP).
  - **Livello 3**: Livello di rete (Protocollo L2TP).

---

#### Protocolli di Tunneling

- **PPTP (Point-to-Point Tunneling Protocol)**:
  - Mantiene i dati al sicuro su reti pubbliche.
  - Consente agli utenti autorizzati di connettersi a una VPN.
  - Estende una LAN su più sedi tramite l'incanalamento dei pacchetti.
  - Non cifra i dati, li incapsula solamente.

- **L2TP (Layer 2 Tunneling Protocol)**:
  - Combina PPTP con l'inoltro a livello 2.
  - Usato per supportare le VPN come parte di servizi ISP.
  - Non fornisce crittografia direttamente, ma utilizza un protocollo di crittografia all'interno del tunnel.

---

#### Tipologie di VPN

- **VPN Site-to-Site**:
  - Collega due reti private attraverso un canale pubblico.
  - Richiede un router VPN in ciascuna sede.

- **VPN End-to-Site**:
  - Permette l'accesso remoto a una rete privata.
  - Utilizza un client VPN per realizzare il tunnel tra la rete e il terminale.
  - Solitamente impiega un'autenticazione semplice.

- **VPN End-to-End**:
  - Connessione tra due terminali.
  - Conosciuto anche come protocollo "remote desktop".
  - Il canale di trasmissione può essere sia pubblico che privato.

---

### Campo di Applicabilità delle VPN

- **Sicurezza delle Comunicazioni**: Garantisce la trasmissione sicura dei dati su reti pubbliche.
- **Accesso Remoto**: Permette agli utenti di accedere alle risorse di rete da luoghi remoti.
- **Estensione delle Reti**: Estende le reti locali (LAN) su diverse sedi geografiche.
- **Privacy**: Protegge la privacy degli utenti incanalando il traffico dati in modo cifrato.
- **Collaborazione tra Sedi**: Facilita la collaborazione tra uffici distanti collegandoli tramite una rete privata virtuale.

---

### Vantaggi delle VPN

- **Sicurezza**: Cifratura dei dati per proteggere le informazioni sensibili.
- **Flessibilità**: Accesso remoto alle risorse aziendali da qualsiasi luogo.
- **Costo-Efficacia**: Riduce i costi associati alla configurazione di reti private fisiche.
- **Privacy**: Nasconde il traffico dati dagli osservatori non autorizzati.
- **Affidabilità**: Offre una connessione stabile e sicura per le comunicazioni aziendali.

### Svantaggi delle VPN

- **Prestazioni**: La cifratura e il tunneling possono introdurre latenze.
- **Complessità**: Configurazione e gestione possono essere complesse.
- **Dipendenza dalla Connettività Internet**: La qualità della VPN dipende dalla qualità della connessione Internet.

---

### Schema Riepilogativo

```plaintext
+--------------------+
|      VPN           |
+--------------------+
| - Rete privata     |
| - Passa su rete    |
|   pubblica         |
+--------------------+
         |
         V
+--------------------+
|     Tunneling      |
+--------------------+
| - Livello 2: PPTP  |
| - Livello 3: L2TP  |
+--------------------+
         |
         V
+--------------------+
|    Tipologie VPN   |
+--------------------+
| - Site-to-Site     |
| - End-to-Site      |
| - End-to-End       |
+--------------------+
         |
         V
+--------------------+
| Campo di           |
| Applicabilità      |
+--------------------+
| - Sicurezza        |
| - Accesso remoto   |
| - Estensione LAN   |
| - Privacy          |
| - Collaborazione   |
+--------------------+
         |
         V
+--------------------+
| Vantaggi           |
+--------------------+
| - Sicurezza        |
| - Flessibilità     |
| - Costo-efficacia  |
| - Privacy          |
| - Affidabilità     |
+--------------------+
         |
         V
+--------------------+
| Svantaggi          |
+--------------------+
| - Prestazioni      |
| - Complessità      |
| - Dipendenza       |
|   dalla connettività|
+--------------------+
```