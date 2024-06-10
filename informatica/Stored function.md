
Le stored function sono utilizzate all'interno di altri comandi.
Restituiscono un valore come le altre funzioni SQL.

```sql
DELIMETER //
CREATE FUNCTION GetSec(Tempo Float)
RETURNS Int
BEGIN

DECLARE Minuti, Secondi Int;
SET Minuti = Floor(Tempo);
SET Secondi = (Tempo – Minuti) * 60;
RETURN Secondi;

END//
DELIMETER;
```

