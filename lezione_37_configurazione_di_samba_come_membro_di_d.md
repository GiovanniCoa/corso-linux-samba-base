# Configurazione di Samba come membro di dominio

## Introduzione
La configurazione di Samba come membro di dominio è un'operazione essenziale per consentire a un server Linux di partecipare a domini Active Directory esterni. Questo permette agli utenti di accedere alle risorse con le proprie credenziali di dominio, garantendo un maggiore livello di sicurezza e facilitando la gestione delle autorizzazioni.

## Passaggi da seguire
Di seguito sono elencati i passaggi da seguire per configurare Samba come membro di dominio:

1. Installazione di Samba: assicurarsi di avere installato il pacchetto Samba sul server Linux. Utilizzare il gestore di pacchetti del sistema operativo per installare Samba.

2. Modifica del file di configurazione di Samba: aprire il file di configurazione di Samba (/etc/samba/smb.conf) e aggiungere le seguenti linee di configurazione:

```
[global]
workgroup = NOME_DEL_DOMINIO
security = ADS
realm = NOME_DEL_DOMINIO.LOCAL
```

3. Join al dominio: eseguire il comando seguente per unirsi al dominio Active Directory esterno, sostituendo "NOME_DEL_DOMINIO" con il nome effettivo del dominio e "NOME_UTENTE_ADMIN" con un utente con privilegi di amministratore del dominio:

```
sudo net ads join -U NOME_UTENTE_ADMIN
```

4. Verifica della configurazione: eseguire il comando seguente per verificare la corretta configurazione di Samba come membro di dominio:

```
net ads testjoin
```

5. Riavvio dei servizi: riavviare il servizio Samba per applicare le modifiche alla configurazione:

```
sudo systemctl restart smbd
sudo systemctl restart nmbd
```

## Conclusioni
Configurare Samba come membro di dominio è un'operazione fondamentale per consentire l'integrazione di un server Linux in un ambiente Active Directory esterno. Seguendo i passaggi sopra descritti, è possibile garantire un accesso sicuro e gestire in modo efficiente le autorizzazioni degli utenti. Prestare attenzione alla corretta configurazione e alla verifica delle impostazioni per garantire il corretto funzionamento del sistema.