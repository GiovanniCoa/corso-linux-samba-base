# Configurare la sincronizzazione oraria

La sincronizzazione oraria è un aspetto fondamentale per garantire che tutti i dispositivi di una rete siano allineati temporalmente. Nel contesto di un dominio Samba, è particolarmente importante configurare correttamente la sincronizzazione oraria per evitare problemi di autenticazione e di gestione delle risorse condivise.

## Passaggi per configurare la sincronizzazione oraria

Per configurare la sincronizzazione oraria in un dominio Samba, è possibile utilizzare un server NTP (Network Time Protocol) per garantire che tutti i dispositivi della rete siano allineati temporalmente. Ecco i passaggi da seguire per configurare la sincronizzazione oraria:

1. **Installare e configurare un server NTP**: Il primo passo è installare e configurare un server NTP sulla rete. È possibile utilizzare software come `ntpd` o `chronyd` per gestire la sincronizzazione oraria.

2. **Configurare i client**: Una volta configurato il server NTP, è necessario configurare i client della rete per sincronizzare l'ora con il server. È possibile farlo tramite il file di configurazione del client NTP o utilizzando il comando `ntpdate`.

3. **Verificare la sincronizzazione**: Dopo aver configurato il server e i client NTP, è importante verificare che la sincronizzazione oraria funzioni correttamente. È possibile farlo utilizzando comandi come `ntpq -p` per controllare lo stato della sincronizzazione.

4. **Integrare la sincronizzazione oraria con il dominio Samba**: Infine, è possibile integrare la sincronizzazione oraria con il dominio Samba per garantire che tutti i dispositivi siano allineati temporalmente. È possibile farlo utilizzando le impostazioni di configurazione di Samba per specificare il server NTP da utilizzare.

## Conclusioni

Configurare correttamente la sincronizzazione oraria in un dominio Samba è essenziale per garantire il corretto funzionamento della rete e prevenire problemi di autenticazione e gestione delle risorse condivise. Seguendo i passaggi sopra descritti, è possibile garantire che tutti i dispositivi della rete siano allineati temporalmente e che la sincronizzazione oraria funzioni correttamente.