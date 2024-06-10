 Il '**Lock**' blocca la risorsa ad un solo processo.
->  La 'richiesta di lock' viene effettuata da un processo, il controllore della concorrenza decide se permetterla.


-> **TIPOLOGIE**

- <mark style="background: #FFF3A3A6;">Read Lock</mark> (Di sola lettura)
	-  E' detto anche '**Lock condiviso**', concesso a più processi contemporaneamente.
- **<mark style="background: #FFB86CA6;">Write Lock</mark>** (Permette la scrittura, in realtà anche la lettura)
	- Detto anche '**Lock esclusivo'**, un processo tiene l'intera risorsa per se.


**Locking a 2 fasi**:
	Avviene in fase crescente, quando si ottiene prima il read lock e successivamente anche il write lock

**Deadlock** -> situazione di stallo
-> Avviene quando un processo è in attesa di una risorsa utilizzata da un altro processo
-> SOLUZIONE -> Timeout
