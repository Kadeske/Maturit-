
- **Perdita di aggiornamento / lost update** -> es. due comprano l'ultimo biglietto contemporaneamente
- **Lettura fantasma / phantom row** -> db non aggiornato, dato non trovato
- **Letture sporche / dirty read** -> db non ancora aggiornato, legge lo stato precedente
- **Letture inconsistenti / unrepeatable read**

**PERDITA DI AGGIORNAMENTO**
-> Avviene quando due processi concorrenti aggiornano un dato e uno dei due è ignorato.

**LETTURA FANTASMA**
-> Legge un dato non aggiornato e lo utilizza con uno aggiornato, che non doveva esserci?
-> Non 'vede' un dato che è stato inserito da un altro processo prima del suo commit.

**LETTURE SPORCHE**
->  Quando si legge un dato con un valore non corretto
->  Es. un processo legge un dato modificato da un altro processo in corso, il quale ha fatto un rollback, rendendo il dato errato.

**LETTURE INCONSISTENTI**
->  Quando, durante lo stesso processo, la lettura dello stesso dato da due valori differenti.


Le anomalie vengono prevenute con i [[Lock]]


