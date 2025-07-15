# Usare NetBIOS e WINS con Samba

## Introduzione
In un ambiente di rete basato su sistemi operativi Windows, l'utilizzo di NetBIOS e WINS è fondamentale per la corretta identificazione e comunicazione tra i dispositivi. Quando si utilizza Samba per creare un server di file condiviso su una rete mista di Windows e Linux, è importante configurare correttamente NetBIOS e WINS per garantire una corretta interoperabilità.

## Ruolo di NetBIOS e WINS
NetBIOS (Network Basic Input/Output System) è un protocollo di livello applicativo che consente ai dispositivi di una rete di comunicare tra loro. Esso fornisce servizi di denominazione, risoluzione degli indirizzi IP e gestione delle sessioni. WINS (Windows Internet Name Service) è un servizio di risoluzione dei nomi che consente ai dispositivi di rete di ottenere gli indirizzi IP associati ai nomi NetBIOS.

## Configurazione di NetBIOS e WINS con Samba
Per utilizzare NetBIOS e WINS con Samba, è necessario configurare correttamente il file di configurazione di Samba (/etc/samba/smb.conf). Di seguito sono riportate alcune linee di configurazione da aggiungere al file smb.conf:

```
[global]
   workgroup = NOME_GRUPPO_DI_LAVORO
   wins support = yes
   wins server = INDIRIZZO_IP_DEL_SERVER_WINS
   netbios name = NOME_DEL_SERVER_SAMBA
```

Nel blocco [global], sostituire "NOME_GRUPPO_DI_LAVORO" con il nome del gruppo di lavoro della rete, "INDIRIZZO_IP_DEL_SERVER_WINS" con l'indirizzo IP del server WINS e "NOME_DEL_SERVER_SAMBA" con il nome del server Samba.

## Test e verifica
Dopo aver configurato correttamente NetBIOS e WINS con Samba, è consigliabile testare la connettività di rete e la risoluzione dei nomi. È possibile utilizzare il comando "nmblookup" per verificare la risoluzione dei nomi NetBIOS e il comando "smbclient -L server" per visualizzare l'elenco delle risorse condivise sul server Samba.

## Conclusioni
Utilizzare NetBIOS e WINS con Samba è fondamentale per garantire una corretta interoperabilità tra dispositivi Windows e Linux su una rete mista. Configurando correttamente NetBIOS e WINS nel file di configurazione di Samba, è possibile semplificare la gestione della rete e migliorare le prestazioni della condivisione dei file. Seguendo i passaggi descritti in questo articolo, è possibile creare un ambiente di rete stabile e efficiente con Samba.