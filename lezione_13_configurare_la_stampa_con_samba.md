# Configurare la stampa con Samba

La condivisione di stampanti su una rete locale può essere un'operazione complessa ma indispensabile per garantire la stampa da diversi dispositivi. In questo articolo, spiegheremo come configurare la stampa con Samba, un software open source che facilita la condivisione di risorse tra dispositivi Windows e Linux.

## Passaggio 1: Installazione di Samba

Prima di tutto, assicurati di avere installato Samba sul tuo server Linux. Puoi farlo tramite il gestore di pacchetti della tua distribuzione, ad esempio con il comando:

```
sudo apt-get install samba
```

## Passaggio 2: Configurazione di Samba

Una volta installato Samba, è necessario configurare il file di configurazione `/etc/samba/smb.conf`. Aggiungi le seguenti linee alla fine del file per definire la tua stampante:

```
[printers]
   comment = All Printers
   path = /var/spool/samba
   browseable = yes
   printable = yes
   guest ok = yes
   read only = yes
   create mask = 0700
```

Salva le modifiche e riavvia il servizio Samba con il comando:

```
sudo systemctl restart smbd
```

## Passaggio 3: Aggiunta della stampante

Una volta configurato Samba, puoi aggiungere la tua stampante su un dispositivo Windows o Linux. Per fare ciò, cerca la stampante di rete nella lista delle stampanti disponibili e aggiungila utilizzando il percorso `\\<indirizzo IP del server>\printers`.

## Conclusioni

Configurare la stampa con Samba può sembrare complicato, ma seguendo attentamente i passaggi descritti in questo articolo, potrai condividere la tua stampante su tutta la rete locale in modo semplice ed efficiente. Assicurati di mantenere aggiornato Samba e di controllare regolarmente le impostazioni di condivisione per garantire un corretto funzionamento della stampa.