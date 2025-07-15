# Accesso da client Linux e macOS

Gli utenti che utilizzano sistemi operativi Linux e macOS spesso si trovano nella necessità di accedere a condivisioni di rete Samba, che sono comuni soprattutto in ambienti di lavoro e in reti domestici. In questo articolo, spiegheremo come montare condivisioni Samba da client Linux e macOS in modo semplice ed efficace.

## Linux

Su sistemi Linux, il modo più comune per montare una condivisione Samba è utilizzando il comando `mount`. Ecco i passaggi da seguire:

1. Assicurarsi di avere il pacchetto `cifs-utils` installato sul sistema. Se non è già presente, è possibile installarlo utilizzando il gestore dei pacchetti della propria distribuzione.

2. Creare una directory vuota che fungerà da punto di mount per la condivisione Samba. Ad esempio, è possibile creare una directory chiamata `samba` nella directory radice del sistema.

3. Utilizzare il comando `mount -t cifs //indirizzo_ip_condivisione /percorso_directory_di_montaggio -o username=nome_utente,password=password` per montare la condivisione Samba. Sostituire `indirizzo_ip_condivisione`, `percorso_directory_di_montaggio`, `nome_utente` e `password` con i valori corretti.

Una volta eseguiti questi passaggi, sarà possibile accedere alla condivisione Samba dalla directory di montaggio creata.

## macOS

Su macOS, è possibile montare una condivisione Samba utilizzando la funzionalità "Connetti al server" integrata nel Finder. Ecco i passaggi da seguire:

1. Aprire il Finder e selezionare "Vai" dal menu in alto. Successivamente, selezionare "Connetti al server" o utilizzare il comando `CMD + K`.

2. Nella finestra di dialogo che appare, inserire l'indirizzo della condivisione Samba preceduto da `smb://`. Ad esempio, `smb://indirizzo_ip_condivisione`.

3. Fare clic su "Connetti" e inserire le credenziali di accesso richieste.

Una volta completati questi passaggi, la condivisione Samba sarà montata sul desktop o nella cartella "Condivisi" del Finder e sarà accessibile come una normale cartella sul sistema.

In conclusione, accedere a condivisioni Samba da client Linux e macOS è un'operazione relativamente semplice che può essere eseguita utilizzando strumenti integrati nei rispettivi sistemi operativi. Seguendo i passaggi descritti in questo articolo, gli utenti potranno facilmente montare e accedere alle condivisioni Samba senza problemi.