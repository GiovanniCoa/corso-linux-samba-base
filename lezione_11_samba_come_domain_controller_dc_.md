# Samba come Domain Controller (DC)

Samba è una suite di software open source che fornisce servizi di file e stampa per sistemi operativi Windows, Linux e UNIX. Uno dei suoi ruoli più importanti è quello di fungere da Domain Controller (DC) per la gestione centralizzata degli account utente, dei permessi e delle risorse di rete in un ambiente Active Directory.

## Configurazione di Samba come DC Active Directory

Per configurare Samba come Domain Controller Active Directory, è necessario seguire una serie di passaggi:

1. **Installazione di Samba**: Assicurarsi di avere Samba installato sul proprio sistema. È possibile utilizzare il gestore di pacchetti della propria distribuzione Linux per installare Samba.

2. **Configurazione di Samba**: Modificare il file di configurazione di Samba (/etc/samba/smb.conf) per abilitare il supporto al Domain Controller. Aggiungere le seguenti righe al file di configurazione:

```ini
[global]
    workgroup = NOME_WORKGROUP
    server role = active directory domain controller
    security = user
```

3. **Creazione del database SAM**: Utilizzare lo strumento `samba-tool` per creare il database SAM, che contiene informazioni sugli account utente e sui gruppi. Eseguire il seguente comando:

```
samba-tool domain provision --use-rfc2307 --interactive
```

Seguire le istruzioni guidate per configurare il proprio dominio Active Directory.

4. **Avvio dei servizi**: Avviare i servizi Samba per attivare il Domain Controller. Eseguire i seguenti comandi:

```
systemctl start samba
systemctl enable samba
```

5. **Configurazione dei client**: Configurare i client Windows per utilizzare il Domain Controller Samba come server di autenticazione. Modificare le impostazioni di rete e aggiungere il Domain Controller come server DNS primario.

Una volta completati questi passaggi, Samba sarà configurato come Domain Controller Active Directory e sarà in grado di gestire gli account utente, i gruppi e le risorse di rete nel proprio ambiente. Questa configurazione offre un'alternativa economica e flessibile alla soluzione proprietaria di Microsoft, consentendo alle organizzazioni di gestire la propria infrastruttura di rete con software open source.

---
Conclusione

Samba come Domain Controller offre una soluzione efficace per la gestione centralizzata degli account utente e delle risorse di rete in un ambiente Active Directory. Seguendo i passaggi di configurazione correttamente, è possibile utilizzare Samba come alternativa economica e flessibile alla soluzione proprietaria di Microsoft.