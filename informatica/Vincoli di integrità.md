
E' una proprietà che ogni istanza di deve rispettare.


## -> Chiave primaria

Una chiave primaria è un attributo o un insieme di attributi che identifica in modo univoco un record all'interno di una tabella.<br>
Caratteristiche:
- Univocità;
- Non null;
- Immutabile.
## -> Chiave esterna

Una chiave esterna è un campo (o più campi), utilizzato per unire logicamente due tabelle.<br>
Caratteristiche:
- Riferimento alla chiave primaria;
- Integrità referenziale: i valori di chiave esterna in una tabella corrispondono ad una chiave primaria in un altra tabella;

## -> Vincoli impliciti

I vincoli impliciti sono quelli imposti dalla struttura dei dati.<br>
Si dividono in:
- vincoli di chiave primaria:
	- le istanze di una tabella devono essere tutte diverse tra loro
 - vincoli referenziali:
	 - Dato A che dipende da B, al variare di B deve necessariamente variare anche A

## -> Vincoli espliciti

Impongono delle restrizioni sul modo in cui le informazioni possono essere rappresentate.<br>
Es. età > 0 and età < 100.<br>
Non è obbligato dalla base di dati ma da chi la gestisce.