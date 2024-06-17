
---

#### Conoscere i Componenti di una Rete Wireless

- **Rete Wireless**: Rete in cui tutti i terminali accedono tramite canali senza fili.

#### Famiglie di Reti Wireless

1. **Reti Radiomobili**:
   - Terminali utenti che possono spostarsi senza perdere la connettività con la rete (es. rete cellulare).

2. **WLAN (Wireless LAN)**:
   - Forniscono copertura e servizi di una LAN tramite connessione senza fili.

#### Classificazione per Superficie Coperta

- **BAN**: 1m
- **PAN**: 10m
- **WLAN**: 500m
- **WWAN**: >500m

#### Altre Tecnologie Wireless

- **HiperLAN**:
  - Derivato da 802.11a con TPC (Transmitter Power Control) e DFS (Dynamic Frequency Selection).
- **IrDA**:
  - Tecnologia di interconnessione a infrarossi, bidirezionale tra dispositivi visibili reciprocamente.
- **DECT**:
  - Standard per telefoni cordless con 120 canali su 12 frequenze.
- **WIpLL**:
  - Servizi voce e dati su ampio raggio.
- **LoRaWAN**:
  - Rete per IoT, ottimo range, scarsa larghezza di banda.
- **FWA**:
  - Rete mista in fibra fino alla stazione, ultimo tratto wireless.
- **Reti Satellitari**:
  - Ottima larghezza di banda, hardware specifico.

---

### Apprendere le Topologie e gli Standard di Comunicazione Wireless

#### Problemi di Trasmissione

1. **Attenuazione del Segnale**:
   - Le radiazioni elettromagnetiche subiscono un indebolimento della potenza a seconda del materiale che attraversano.
2. **Interferenze da Parte di Altre Sorgenti**:
   - L'etere è saturo di 'rumori' radio che causano interferenze.
3. **Propagazione su Più Cammini**:
   - Il segnale si riflette sugli oggetti dividendosi in più cammini, indebolendosi.
4. **Shadowing**:
   - Le onde elettromagnetiche sono bloccate da edifici e ostacoli.
5. **Effetto Doppler**:
   - La frequenza della trasmissione può cambiare in base al moto dell'utente (es. ambulanza che passa veloce).

#### Problemi Specifici

- **Stazione Nascosta**:
  - Stazioni agli estremi che non si 'sentono' a vicenda possono causare interferenze durante la comunicazione.
- **Stazione Esposta**:
  - Un dispositivo che sente il rumore da una connessione evita di comunicare, anche se non disturberebbe effettivamente.

#### Architettura delle Reti WLAN

- **Infrastruttura di Rete**: Rete a cui l'host vuole connettersi.
- **Host Wireless**: Dispositivo con scheda di rete wireless.
- **Collegamenti**: Connessione dei dispositivi alla stazione tramite etere.
- **Stazione Base**: Funziona da ripetitore, invia pacchetti della rete cablata (es. access point).

#### Tassonomia delle Reti Wireless

1. **Hop Singolo, Senza Infrastruttura**:
   - Nessuna stazione base, composta da un singolo nodo (es. Bluetooth).
2. **Hop Singolo, Con Infrastruttura**:
   - Una stazione collegata alla rete cablata, dispositivi connessi con un singolo hop.
3. **Hop Multipli, Senza Infrastruttura**:
   - Nessuna stazione base, destinazione raggiungibile tramite nodi intermedi.
4. **Hop Multipli, Con Infrastruttura**:
   - Host connesso all'infrastruttura, nodi che trasmettono dati.

---

### Conoscere le Modalità di Sicurezza WPA2

- **WPA2**: Modalità di sicurezza avanzata per reti wireless.
  - **Cifratura dei Dati**: Utilizzo di algoritmi di crittografia avanzati.
  - **Autenticazione Utenti**: Richiede autenticazione per accedere alla rete.
  - **Integrità dei Dati**: Verifica che i dati non siano stati alterati.

---

### Comprendere il Sistema di Autenticazione 802.1X

- **Autenticazione 802.1X**: Sistema di controllo degli accessi per le reti wireless.
  - **Supplicant**: Dispositivo che richiede l'accesso alla rete.
  - **Authenticator**: Punto di accesso che controlla l'accesso.
  - **Authentication Server**: Server che verifica le credenziali e autorizza l'accesso.


---

### Schema Riepilogativo

```plaintext
+------------------------------------+
|     Sicurezza nelle Reti Wireless  |
+------------------------------------+
| - Conoscere i Componenti           |
| - Apprendere le Topologie e        |
|   Standard                         |
| - Conoscere le Modalità di         |
|   Sicurezza WPA2                   |
| - Comprendere il Sistema di        |
|   Autenticazione 802.1X            |
+------------------------------------+
         |
         V
+------------------------------------+
| Componenti di una Rete Wireless    |
+------------------------------------+
| - Reti Radiomobili                 |
| - WLAN                             |
| - Classificazione per Superficie   |
+------------------------------------+
         |
         V
+------------------------------------+
| Altre Tecnologie Wireless          |
+------------------------------------+
| - HiperLAN                         |
| - IrDA                             |
| - DECT                             |
| - WIpLL                            |
| - LoRaWAN                          |
| - FWA                              |
| - Reti Satellitari                 |
+------------------------------------+
         |
         V
+------------------------------------+
| Problemi di Trasmissione           |
+------------------------------------+
| - Attenuazione del Segnale         |
| - Interferenze                     |
| - Propagazione su Più Cammini      |
| - Shadowing                        |
| - Effetto Doppler                  |
+------------------------------------+
         |
         V
+------------------------------------+
| Architettura delle Reti WLAN       |
+------------------------------------+
| - Infrastruttura di Rete           |
| - Host Wireless                    |
| - Collegamenti                     |
| - Stazione Base                    |
+------------------------------------+
         |
         V
+------------------------------------+
| Tassonomia delle Reti Wireless     |
+------------------------------------+
| - Hop Singolo, Senza Infrastruttura|
| - Hop Singolo, Con Infrastruttura  |
| - Hop Multipli, Senza Infrastruttura|
| - Hop Multipli, Con Infrastruttura |
+------------------------------------+
         |
         V
+------------------------------------+
| Modalità di Sicurezza WPA2         |
+------------------------------------+
| - Cifratura dei Dati               |
| - Autenticazione Utenti            |
| - Integrità dei Dati               |
+------------------------------------+
         |
         V
+------------------------------------+
| Sistema di Autenticazione 802.1X   |
+------------------------------------+
| - Supplicant                       |
| - Authenticator                    |
| - Authentication Server            |
+------------------------------------+
```

(NON SONO SUL DOCUMENTO DEL 15 MAGGIO)

#### Reti IBSS (ad hoc)

- **Definizione**: La forma più semplice di rete ad hoc.
- **Composizione**: Insieme di stazioni che comunicano senza infrastruttura.
- **Caratteristiche**:
    - Nessuna stazione comune.
    - Ogni host è una stazione.
    - Accordi tra gli host sui protocolli da utilizzare.

#### Reti ESS (infrastruttura)

- **Definizione**: Reti caratterizzate dalla presenza di una LAN che interconnette diversi BSS (Basic Service Set).
- **Composizione**:
    - **Access Point (AP)**: Ripetitore che invia pacchetti della rete cablata nella sua copertura.
    - **BSS**: Insieme di stazioni associate a un AP.
- **Gestione del Passaggio tra Stazioni**:
    - Transizione tra ESS: Movimento tra BSS e due ESS diversi, con perdita temporanea di connettività.
    - Transizione tra BSS: Movimento tra due BSS parzialmente sovrapposti, gestito in modo trasparente.
    - Statica: Stazione immobile o che si sposta solo all'interno della BSS.

#### Scansione delle ESS

- **Scopo**: Trovare una rete e connettersi ad essa, inizializzare una IBSS, o connettersi a un AP in roaming.
- **Tipi**:
    - **Passive Scanning**: Basato sulla ricezione periodica dei beacon che contengono SSID e indirizzo MAC.
    - **Active Scanning**: Richiede una ricerca attiva inviando tre tipi di pacchetti (sondaggio, autenticazione, associazione).

#### Servizi Offerti da DSS (Distributed System Services)

- **Associazione**: Accesso a un AP da parte di una stazione.
- **Disassociazione**: Terminazione immediata di un'associazione.
- **Reassociazione**: Spostamento di un protocollo da un AP all'altro, con notifica al DS.
- **Distribuzione**: Scambio di informazioni tra AP attraverso il DS.
- **Integrazione**: Traduzione da 802.11 a 802.x.

#### Servizi Offerti da SS (Station Services)

- **Autenticazione**: Dimostrazione dell'autorizzazione a utilizzare i servizi di trasmissione.
- **Deautenticazione**: Notifica di uscita dalla rete.
- **Privacy**: Crittografia dei frame tramite RC4.
- **Trasmissione**: Servizio principale per la comunicazione all'interno dell'ESS.