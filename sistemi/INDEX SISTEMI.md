
- ISO/OSI
	- [[Protocollo FTP (File Transfer Protocol)]]
	- [[Protocollo Telnet]]
	- [[Protocollo HTTP]]
		- [Vai alle Operazioni CRUD](Protocollo%20HTTP.md#Operazioni-CRUD)


		- codici di stato
- VLAN
	- caratteristiche
	- pro e contro
	- caratteristiche VLAN port based
	- VLAN tagged, untagged e ibride
	- Protocollo VTP
- Crittografia
	- definizione
	- Simmetrica
	- Asimmetrica 
	- Firma digitale
	- Algoritmo MD5 (Hashing)
- Sicurezza nelle reti
	- Problematiche
	- Protocollo SSL/TLS
	- Firewall
		- tipologie
		- proxy firewall
		- DMZ
	- VPN e applicazioni 


### Schema comparativo dei protocolli

| Protocollo | Funzione principale           | Applicazioni comuni                                         | Pro                                                              | Contro                                                   |
| ---------- | ----------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------- |
| FTP        | Trasferimento file            | Download/upload file                                        | Semplicità, Velocità, Compatibilità                              | Sicurezza, Controllo limitato, Problemi con firewall/NAT |
| HTTP       | Trasferimento ipertestuale    | Navigazione web, API                                        | Universalità, Supporto ampio, Facilità d'uso                     | Sicurezza (dati in chiaro), Performance (in alcuni casi) |
| Telnet     | Accesso remoto                | Amministrazione remota                                      | Semplicità, Versatilità, Diagnostica                             | Sicurezza, Obsolescenza, Funzionalità limitate           |
| SSH        | Accesso remoto sicuro         | Amministrazione remota, trasferimento sicuro di file (SFTP) | Sicurezza elevata, Crittografia, Tunneling, Autenticazione       | Complessità di configurazione, Overhead computazionale   |
| SSL/TLS    | Sicurezza delle comunicazioni | Comunicazioni sicure (HTTPS, email, VPN)                    | Crittografia avanzata, Integrità dati, Autenticazione            | Complessità di implementazione, Overhead computazionale  |
| VTP        | Gestione delle VLAN           | Configurazione automatica delle VLAN sui switch             | Facilita gestione delle VLAN, Riduzione errori di configurazione | Complessità, Rischio di propagazione errori              |