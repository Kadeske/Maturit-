
Le applicazioni Java, incluse le servlet, possono connettersi e comunicare con diverse tipologie di database tramite il protocollo JDBC (Java Database Connectivity). JDBC è uno standard industriale indipendente dal DBMS impiegato, che permette di mantenere il principio del "Write Once, Run Anywhere" di Java. Questa flessibilità consente di scrivere un codice riutilizzabile e compatibile con vari database senza doverlo modificare per ciascuno di essi.

#### Tipi di Driver JDBC

I driver JDBC si classificano in quattro categorie principali, ognuna con caratteristiche e utilizzi specifici:

1. **Bridge JDBC-ODBC (Tipo 1)**:
    
    - Questo driver funge da ponte tra JDBC e ODBC, permettendo l'accesso a qualsiasi database per cui esiste un driver ODBC. Tuttavia, richiede l'installazione delle librerie ODBC sul client, compromettendo il principio WORA (Write Once, Run Anywhere). Questo driver è stato deprecato a partire da Java 8.
2. **Driver con API Native (Tipo 2)**:
    
    - Questi driver utilizzano API native del database, come le API di Oracle, per connettersi direttamente al DBMS senza passare per ODBC. Sono molto performanti ma richiedono che le librerie native siano presenti sul client.
3. **Pure Java Driver for Database Middleware (Tipo 3)**:
    
    - Questi driver sono scritti interamente in Java e utilizzano un middleware per convertire le chiamate JDBC nel protocollo del database. Sono particolarmente adatti per ambienti distribuiti e applet/servlet, offrendo un'alta compatibilità con vari DBMS.
4. **Direct-to-Database Pure Java Driver (Tipo 4)**:
    
    - Questi driver, interamente scritti in Java, trasformano le chiamate JDBC direttamente nel protocollo del database, senza necessità di middleware. Sono ideali per le applicazioni Java, poiché non richiedono componenti aggiuntivi sul client e rispettano pienamente il principio WORA.