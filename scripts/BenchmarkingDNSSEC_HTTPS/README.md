
Lo script `scriptKdig.sh` permette di eseguire il benchmarking dei protocolli DNSSEC e DNS-over-HTTPS utilizzando automaticamente `dnssec_httpsPerf.sh`.

##### Esempio di utilizzo
**Per HTTPS:**
Innanzitutto bisogna inserire l'indirizzo IP del server da testare e il flag `+https-get` all'interno del file `dnssec_httpsPerf.sh`, la cui riga numero sette quindi sarà: `kdig +https-get $1 @IPserver +short >> /dev/null`. Infine basterà eseguire `./scriptKdig.sh fileRecordsBenchmarking.txt`, il file `fileRecordsBenchmarking.txt` contiene le richieste da effettuare. 

**Per DNSSEC**
Innanzitutto bisogna inserire l'indirizzo IP del server da testare e il flag `+dnssec` all'interno del file `dnssec_httpsPerf.sh`, la cui riga numero sette quindi sarà: `kdig +dnssec $1 @IPserver +short >> /dev/null`. Infine basterà eseguire `./scriptKdig.sh fileRecordsBenchmarking.txt`, il file `fileRecordsBenchmarking.txt` contiene le richieste da effettuare. 

**NOTA:** questo script produce un file in cui è presente una lista di latenze, gli script per la generazione dei grafici accettano in input un file in cui le latenze sono separate da virgola. In questo lavoro tale modifica è stata effettuata utilizzando il comando `tr '\n' ','`
