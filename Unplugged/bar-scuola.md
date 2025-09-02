# Il bar della scuola

*keywords: architettura client server*

Primi giorni di scuola, l'aria è ancora calda, il ricordo dell'estate ancora vivo... perchè stare seduti in un'aula scolastica? Meglio una bella passeggiata con i propri compagni di classe per i corridoi della scuola... e dove andare, per trovare uno spazio in cui chiacchierare liberamente, senza timore di disturbare le lezioni che si svolgono in altre, sfortunate classi? Ovviamente al bar della scuola.

Ci dirigiamo lì in silenzio, sperando di non incontrare il Dirigente dietro l'angolo, o di non innervosire qualche sorvegliante annoiata. 

Arrivati al bar si presenta la tipica scena di una mattinata qualunque: la barista sta pulendo il bancone dopo il disastro della prima ricreazione, in attesa di qualche professore in pausa o di qualche studente che è riuscito a sottrarsi alla prima lezione:

> Osservazione 1: cosa sta facendo la barista quando siamo entrati?

Il prof è in vena di regali, ed è disposto ad offrire il caffè allo studente con media voti nell'anno precedente più bassa. Passa una moneta da un euro allo studente e lo invia a richiedere il proprio caffè.

> Osservazione 2: descrivere quali azioni svolgono lo studente e la barista, indicando l'esatta sequenza in cui tali azioni si svolgono

---

Gli studenti più estroversi, però, non sono contenti. Anche loro vorrebbero iniziare l'anno scolastico con un caffè offerto dal prof.
Perché scontentarli? Il prof fornisce tre monete ad altrettanti studenti e li lascia liberi di andare a chiedere il proprio caffè.

> Osservazione 3: quanto tempo impiega la barista a preparare un caffè?
> Osservazione 4: quanto tempo impiega il primo studente ad essere servito? Quanto impiegheranno il secondo ed il terzo?
> Osservazione 5: in che ordine sono stati serviti gli studenti? Chi è stato servito prima, il primo che si è messo in fila o l'ultimo?
> Osservazione 6: riusciamo a prevedere quanto tempo impiegherà lo studente 5? Il 10? Riusciamo a dedurre una formula generale per calcolare il tempo di attesa?

Attenzione, arriva il preside! Anche lui vuole un caffè! Che si fa? Ovviamente gli studenti, che si sentono già in colpa per stare al bar invece che in classe, lo fanno passare avanti... lui apprezza, la sosta al bar è salva!

> Osservazione 7: è giusto aver dato la precedenza al preside? 
> Osservazione 8: cosa fa la barista dopo aver servito l'ultimo caffè?

Ora però si è creata un ingiustizia: alcuni hanno avuto il loro caffè e alcuni no! Purtroppo è ora di rientrare in classe, non c'è tempo a sufficienza perché tutti gli studenti abbiano il proprio caffè. Pazienza, sarà per la prossima volta.

> Osservazione 9: Come il bar della scuola avrebbe dovuto gestire la situazione di un'intera classe che vuole il proprio caffè, in modo da rendere più basso possibile il tempo di attesa?

Prima di andare però facciamo uno scherzo allo studente più antipatico della scuola che vediamo sopraggiungere proprio in questo momento. Anche lui vuole il caffè! Allora al diavolo la fretta, tutti quanti mettiamoci in fila a chiedere un caffè. Anche chi l'ha già avuto... così lo scherzo sarà più divertente!

> Osservazione 10: quanto tempo impiegherà lo studente antipatico ad avere il proprio caffè?

## Fuori di metafora

La barista ha svolto il ruolo di server:
- all'inizio del proprio turno, ha acceso e predisposto la macchina del caffè, poi si è messa in attesa di clienti.
- al sopraggiungere del primo studente, ha ascoltato la sua richiesta, l'ha processata utilizzando la macchina del caffè, ha appoggiato il risultato dell'elaborazione, ossia la tazza di caffè, sul bancone.
- poi si è nuovamente seduta, in attesa di altri clienti.

Gli studenti hanno svolto il ruolo di client:
- hanno richiesto un servizio alla barista. Si sono avvicinati al banco, hanno descritto la loro richiesta, sono rimasti in attesa del caffè.

Quando più studenti hanno richiesto il caffè, la barista li ha serviti secondo una strategia FIFO: first in first out,  il primo arrivato è stato il primo ad essere servito. Gli studenti hanno atteso in coda, il tempo di attesa prima di poter inviare la propria richiesta è stato pari a (studenti in coda - 1) * (tempo di preparazione).

Quando è arrivato il preside, la *strategia* per la gestione della coda è stata modificata da FIFO a *Coda a priorità*: prima il client più importante, poi quelli meno importanti, nell'ordine in cui sono entrati.

Il bar della scuola potrebbe funzionare in modo più rapido aumentando il numero di baristi: raddoppiandone il numero si dimezza il tempo di attesa, anche se andrà a raddoppiare il costo di gestione del bar. Un servizio può essere dunque fornito in modo più rapido aumentando il numero di server e distribuendo i client in ingresso sui server disponibili. Un nuovo client verrà inviato al server con la coda di attesa più corta.

## il Denial of Service

Lo scherzo combinato allo studente antipatico è una metafora dell'attacco DOS, con cui dei client maliziosi rendono un server irreperibile inviando un numero eccessivo di richieste che non è in grado di gestire. Un client innocente che volesse inviare una richiesta a questo server, vedrà la propria richiesta restare in attesa per un tempo indefinito, trovando il server indaffarato a gestire le richieste dei client maliziosi.

