# Configurazione di shadow copies

Le shadow copies sono una funzionalità di Windows che consente di creare versioni precedenti di file e cartelle, consentendo agli utenti di ripristinare facilmente versioni precedenti in caso di perdita o modifica accidentale dei dati. Quando si utilizza Samba come server di file, è possibile configurare le shadow copies per le condivisioni Samba in modo da offrire agli utenti una maggiore flessibilità e sicurezza nella gestione dei dati.

## Configurazione di shadow copies su Samba

Per abilitare le shadow copies su una condivisione Samba, è necessario configurare il server Samba per supportare questa funzionalità. Ecco i passaggi da seguire per configurare le shadow copies su Samba:

1. Assicurarsi che il server Samba supporti le shadow copies. È possibile verificare questa funzionalità eseguendo il comando `smbstatus -V` e verificando che il supporto alle shadow copies sia abilitato.

2. Configurare il file `smb.conf` per abilitare le shadow copies per la condivisione desiderata. Aggiungere le seguenti righe al file di configurazione:

```
[volume]
path = /percorso/condivisione
vfs objects = shadow_copy2
shadow:snapdir = /percorso/snapshots
shadow:basedir = /percorso/condivisione
```

Dove `/percorso/condivisione` è il percorso della condivisione Samba e `/percorso/snapshots` è il percorso in cui verranno memorizzate le shadow copies.

3. Riavviare il servizio Samba per applicare le modifiche alla configurazione:

```
sudo systemctl restart smbd
```

Una volta completati questi passaggi, le shadow copies dovrebbero essere abilitate per la condivisione specificata su Samba. Gli utenti saranno in grado di accedere alle versioni precedenti dei file e delle cartelle nella condivisione utilizzando la funzionalità di shadow copies di Windows.

## Utilizzo delle shadow copies su Samba

Una volta configurate le shadow copies su Samba, gli utenti possono utilizzare questa funzionalità per recuperare facilmente versioni precedenti dei file e delle cartelle. Per accedere alle shadow copies, è sufficiente fare clic con il tasto destro del mouse sul file o sulla cartella desiderata, selezionare "Proprietà" e passare alla scheda "Versioni precedenti" per visualizzare e ripristinare le versioni precedenti.

Le shadow copies offrono agli utenti una maggiore flessibilità e sicurezza nella gestione dei dati su una condivisione Samba, consentendo loro di recuperare facilmente i file e le cartelle in caso di perdita o modifica accidentale. Configurare le shadow copies su Samba è un modo efficace per migliorare la gestione dei dati e garantire la disponibilità delle versioni precedenti dei file e delle cartelle per gli utenti.

In conclusione, la configurazione delle shadow copies su Samba è un'operazione relativamente semplice che offre numerosi vantaggi in termini di gestione dei dati e sicurezza. Seguendo i passaggi descritti in questo articolo, è possibile abilitare