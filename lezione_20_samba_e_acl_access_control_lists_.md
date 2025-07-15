# Samba e ACL (Access Control Lists)

## Introduzione

In un ambiente di rete complesso, la gestione dei permessi sui file e sulle cartelle diventa cruciale per garantire la sicurezza e la corretta condivisione delle risorse tra gli utenti. Samba, il software open source che permette di condividere file e stampanti su una rete Windows, offre una serie di strumenti avanzati per la gestione dei permessi, tra cui le Access Control Lists (ACL).

## Cosa sono le ACL

Le ACL sono un meccanismo avanzato per definire i permessi di accesso ai file e alle cartelle su un sistema operativo. A differenza dei tradizionali permessi di tipo user-group-other, le ACL consentono di specificare in modo dettagliato i permessi per singoli utenti o gruppi, rendendo la gestione dei permessi molto più flessibile e precisa.

## Configurazione delle ACL con Samba

Per abilitare le ACL su una condivisione Samba, è necessario configurare correttamente il file di configurazione di Samba (`smb.conf`). È possibile definire le ACL direttamente nella configurazione della condivisione, specificando i permessi per singoli utenti o gruppi.

Ad esempio, per concedere al gruppo "marketing" il permesso di scrittura su una determinata cartella condivisa, è possibile aggiungere le seguenti righe al file `smb.conf`:

```bash
[marketing]
path = /path/to/shared_folder
valid users = @marketing
writable = yes
create mask = 0770
directory mask = 0770
```

In questo modo, solo gli utenti appartenenti al gruppo "marketing" avranno il permesso di scrittura sulla cartella condivisa.

## Gestione delle ACL

Una volta configurate le ACL, è possibile gestirle direttamente da riga di comando utilizzando il comando `setfacl`. Ad esempio, per aggiungere il permesso di lettura e scrittura per l'utente "alice" su un file, è possibile utilizzare il seguente comando:

```bash
setfacl -m u:alice:rw file.txt
```

In questo modo, l'utente "alice" avrà il permesso di lettura e scrittura sul file specificato.

## Conclusioni

Le ACL offrono un modo avanzato e flessibile per gestire i permessi sui file e sulle cartelle condivise tramite Samba. Configurare correttamente le ACL permette di garantire la sicurezza e la corretta gestione delle risorse condivise in un ambiente di rete complesso. Con una corretta configurazione e gestione delle ACL, è possibile garantire un accesso sicuro e controllato alle risorse condivise su una rete Windows utilizzando Samba.