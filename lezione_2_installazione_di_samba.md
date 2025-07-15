# Installazione di Samba

Samba è un software open source che permette la condivisione di file e stampanti tra sistemi operativi diversi, come Linux e Windows. In questo articolo vedremo come installare Samba su distribuzioni Linux comuni.

## **Passo 1: Aggiornare il sistema**

Prima di installare Samba, è consigliabile aggiornare il sistema per garantire di avere le ultime versioni dei pacchetti. Apri il terminale e esegui i seguenti comandi:

```bash
sudo apt update
sudo apt upgrade
```

## **Passo 2: Installare Samba**

Una volta che il sistema è aggiornato, è possibile procedere con l'installazione di Samba. Esegui il seguente comando nel terminale:

```bash
sudo apt install samba
```

Al termine dell'installazione, Samba sarà pronto per essere configurato.

## **Passo 3: Configurare Samba**

La configurazione di Samba avviene modificando il file di configurazione `/etc/samba/smb.conf`. È possibile utilizzare un editor di testo come `nano` o `vim` per aprire il file e apportare le modifiche necessarie. 

Ecco un esempio di configurazione base per condividere una cartella:

```plaintext
[shared]
   path = /path/to/shared/folder
   writable = yes
   valid users = user1 user2
   read only = no
```

Assicurati di sostituire `/path/to/shared/folder` con il percorso della cartella che desideri condividere e `user1 user2` con gli utenti autorizzati ad accedere alla condivisione.

## **Passo 4: Riavviare il servizio Samba**

Dopo aver apportato le modifiche al file di configurazione, riavvia il servizio Samba per applicare le modifiche:

```bash
sudo systemctl restart smbd
```

## **Passo 5: Configurare autorizzazioni**

Assicurati di configurare le autorizzazioni corrette sulla cartella condivisa per consentire l'accesso agli utenti autorizzati. Puoi farlo utilizzando il comando `chmod`:

```bash
sudo chmod -R 755 /path/to/shared/folder
```

## **Passo 6: Accesso alla condivisione da Windows**

Una volta configurato Samba, puoi accedere alla condivisione da un computer Windows utilizzando l'indirizzo IP del server Linux e le credenziali dell'utente autorizzato.

## **Conclusione**

In questo articolo abbiamo visto come installare e configurare Samba su distribuzioni Linux comuni. Seguendo i passaggi descritti, sarai in grado di condividere file e stampanti tra sistemi operativi diversi in modo semplice e sicuro. Buona condivisione!