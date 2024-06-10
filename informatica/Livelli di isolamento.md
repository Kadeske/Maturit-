
1. **Read Uncommitted**: 
	1. Le transazioni possono vedere i dati modificati da altre transazioni non ancora confermate (*dirty read*). 
	2. Non offre protezione contro anomalie.
2. **Read Committed**: 
	1. Le transazioni possono vedere solo i dati confermati (committed) da altre transazioni. Previene i *dirty read*, ma non i *non-repeatable read* o i *phantom read*.
3. **Repeatable Read**: 
	1. Garantisce che se una transazione legge un valore, lo stesso valore sarà visto in tutte le letture successive durante la transazione. 
	2. Previene i *dirty read* e i *non-repeatable read*, ma non i *phantom read*.
4. **Serializable**: 
	1. Il livello più alto di isolamento. 
	2. Le transazioni sono eseguite come se fossero seriali, cioè una dopo l'altra, prevenendo tutte le anomalie (*dirty read*, *non-repeatable read*, e *phantom read*). 
	3. Assicura la massima consistenza, ma può ridurre la concorrenza e le prestazioni.
