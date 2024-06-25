
Transazioni -> insieme di operazione da eseguire come se fossero un'unica operazione (cosa).

Es. prelievo da sportello atm

-> Esempio trasferimento soldi tra conti

-> Schema stati fondamentali di una transazione
	![[Pasted image 20240603210211.png]]

-> Stati della transazione:

| BEGIN               | Inizio transazione                                 |
| ------------------- | -------------------------------------------------- |
| ABORTED             | Transazione annullata                              |
| COMMITTED           | Transazione terminata con successo ed inviata      |
| PARTIALLY COMMITTED | Transazione terminata con successo ma non inviata. |


Le transazioni possono essere eseguite in maniera:
-  **Sequenziale** -> lenta ma efficace
- **Concorrente**

Esecuzione Concorrente

Viene gestita da un '**Transaction Manager**', garantisce che le transazioni non interferiscano tra loro.
Con accesso a risorse differenti non si ha alcun problema.
Con medesime risorse si possono riscontrare delle [[Anomalie]]
