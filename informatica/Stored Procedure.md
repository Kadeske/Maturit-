
Sono chiamate con il comando CALL

Non restituiscono dati ma li visualizzano

Possono chiamare comandi SQL, al contrario delle funzioni

```sql
END
// DELIMETER;
CREATE PROCEDURE
NuovoStudente (IN Matr varchar(5), IN Cognome varchar(30), IN Nom varchar(20),
IN Indir varchar(30), IN Facolta varchar(5), OUT NumStud Int )
BEGIN
INSERT INTO Studenti VALUES (Matr, Cogn, Nom, Indir, Facolta);
NumStud = SELECT * FROM Studenti WHERE Facolta = Facolta;
END//
```


Le **stored procedure** migliorano la portabilità perché cambiando ambiente operativo **MySql** sarà eseguibile in tutti gli ambienti.