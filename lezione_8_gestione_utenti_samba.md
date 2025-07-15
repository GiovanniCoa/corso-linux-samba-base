# Gestione utenti Samba

## Introduzione
La corretta gestione degli utenti Samba rappresenta un passo fondamentale per garantire una corretta configurazione e sicurezza del servizio di condivisione di file e stampanti su una rete locale. In questo articolo verrà illustrato come creare e gestire utenti Samba separati dagli utenti di sistema, al fine di mantenere un adeguato livello di controllo e sicurezza.

## Creazione degli utenti Samba
Per creare un utente Samba separato dagli utenti di sistema è necessario utilizzare il comando `smbpasswd`, che consente di associare una password agli utenti Samba. Per aggiungere un nuovo utente, è sufficiente eseguire il seguente comando:

```
$ sudo smbpasswd -a <username>
```

Una volta inserita la password richiesta, l'utente sarà correttamente aggiunto al database di Samba e potrà accedere alle risorse condivise sulla rete.

## Gestione degli utenti Samba
Per gestire gli utenti Samba è possibile utilizzare il comando `pdbedit`, che consente di visualizzare e modificare le informazioni degli utenti presenti nel database di Samba. Per visualizzare la lista degli utenti, è sufficiente eseguire il seguente comando:

```
$ sudo pdbedit -L
```

Per modificare le informazioni di un utente, è possibile utilizzare il comando `pdbedit -e <username>`, specificando il nome utente dell'utente da modificare.

## Separazione degli utenti Samba dagli utenti di sistema
Per separare gli utenti Samba dagli utenti di sistema, è possibile utilizzare la direttiva `username map`, che consente di mappare gli utenti Samba con gli utenti di sistema. Per configurare questa direttiva, è necessario modificare il file di configurazione di Samba `smb.conf`, aggiungendo le seguenti righe:

```
[global]
    username map = /etc/samba/smbusers
```

Successivamente, è possibile creare il file `/etc/samba/smbusers` e definire le corrispondenze tra gli utenti Samba e gli utenti di sistema, ad esempio:

```
sambauser = systemuser
```

In questo modo, sarà possibile gestire separatamente gli utenti Samba dagli utenti di sistema, garantendo un maggiore controllo e sicurezza.

## Conclusioni
La corretta gestione degli utenti Samba rappresenta un aspetto fondamentale per garantire un'adeguata configurazione e sicurezza del servizio di condivisione di file e stampanti su una rete locale. Creando e gestendo utenti Samba separati dagli utenti di sistema, sarà possibile mantenere un elevato livello di controllo e sicurezza, riducendo al minimo i rischi di accessi non autorizzati e vulnerabilità. Seguendo le indicazioni fornite in questo articolo, sarà possibile creare e gestire utenti Samba in modo efficace e professionale.