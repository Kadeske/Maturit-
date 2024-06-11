
### Definizione
La crittografia è una tecnica utilizzata per proteggere la segretezza dei dati, assicurare l'autenticità e l'integrità dei documenti, e prevenire il ripudio. Essa si basa su algoritmi di cifratura che trasformano il testo in chiaro in testo cifrato, il quale può essere decifrato solo da chi possiede la chiave corretta.

### Simmetrica
La crittografia simmetrica utilizza la stessa chiave sia per cifrare che per decifrare i dati. Questo metodo è rapido ed efficiente, ma comporta la difficoltà di scambiare in modo sicuro la chiave segreta tra le parti.


```python
if key_crypt == key_decrypt:
    schema = "SIMMETRICO" or "PRIVATO"
    key = "ASIMMETRICO" or "PUBBLICO"
```

**DES (Data Encryption Standard)**
- È stato uno dei primi sistemi crittografici moderni sviluppato negli USA nel 1976.
- Suddivide il testo in blocchi di 8 byte e applica una funzione cifrante per 16 volte.
- È stato violato nel 1998 in meno di 60 ore.

**AES (Advanced Encryption Standard)**
- Progettato per resistere a tutti i tipi di attacco, è veloce e compatto.
- Cifra i dati in blocchi di 128 bit con chiavi di 128, 192 o 256 bit.
- Effettua operazioni di sostituzione, shift, mix delle colonne e aggiunta della chiave.

### Asimmetrica
La crittografia asimmetrica utilizza una coppia di chiavi: una pubblica per cifrare e una privata per decifrare. Questo metodo risolve il problema dello scambio sicuro delle chiavi.

**Esempio:**
```python
if key_crypt != key_decrypt:
    schema = "ASIMMETRICO"
    key_crypt = "PUBBLICA"
    key_decrypt = "PRIVATA"
```

**RSA (Rivest-Shamir-Adleman)**
- Utilizza una funzione matematica basata sui numeri primi.
- Ogni utente ha una chiave pubblica e una chiave privata.
- Permette di garantire sia la confidenzialità che l'autenticità dei messaggi.

**Funzionamento:**
1. B sceglie due numeri primi e calcola il loro prodotto (n).
2. B invia n ad A.
3. A cifra il messaggio con n e lo invia a B.
4. B decifra il messaggio usando i numeri primi.

### Firma digitale
La firma digitale utilizza la crittografia asimmetrica per garantire l'autenticità e l'integrità di un documento, nonché la non ripudiabilità.

**Processo di firma digitale:**
1. L'utente crea una firma digitale utilizzando una chiave privata.
2. Il destinatario verifica la firma con la chiave pubblica dell'utente.
3. Il documento viene "imbustato" in un file crittografato (es. documento.txt.p7m).

**Requisiti legali:**
- Un dispositivo di firma sicuro.
- Protezione tramite pin segreto.

### Algoritmo MD5 (Hashing)
MD5 è un algoritmo di hashing che produce una stringa di 128 bit (32 caratteri) indipendentemente dalla lunghezza dell'input. Viene utilizzato per garantire l'integrità dei dati.

**Fasi dell'MD5:**
1. **Padding**: Aggiunta di bit di riempimento fino a raggiungere un multiplo di 512.
2. **Aggiunta della lunghezza**: Gli ultimi 64 bit contengono la lunghezza del messaggio originale.
3. **Inizializzazione del buffer**: Creazione di un buffer di quattro parole a 32 bit.
4. **Compressione**: Elaborazione dei blocchi di 512 bit con funzioni ausiliarie.

### Considerazioni aggiuntive
- **SHA (Secure Hash Algorithm)**: Serie di algoritmi di hashing con diverse lunghezze di output.
- **Certification Authority (CA)**: Enti che certificano l'identità degli utenti associando le chiavi pubbliche alle identità.
- **PKI (Public Key Infrastructure)**: Sistema che gestisce le chiavi pubbliche e private per garantire la sicurezza delle comunicazioni.

Questi elementi fondamentali della crittografia sono cruciali per garantire la sicurezza nelle reti e nelle comunicazioni digitali, proteggendo i dati da accessi non autorizzati e garantendo l'integrità e l'autenticità delle informazioni scambiate.