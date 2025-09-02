# Regaliamo cioccolatini

*Keywords: protocollo TCP, porte logiche*

In questa attività, la lezione di Reti di Computer consisterà nel regalare cioccolatini a studenti della scuola. Forniremo un servizio non richiesto, ma che speriamo risulti comunque gradito ai fortunati destinatari.

La classe è suddivisa in coppie, ad ogni coppia è affidato un cioccolatino ed un bigliettino, su cui il fortunato destinatario potrà scrivere un breve ringraziamento.

Si identificano poi alcune aule della scuola e si sceglie un numero a caso compreso tra 1 e 30.

Qualche coppia avrà in dotazione anche un bigliettino, su cui lo studente che riceve il cioccolatino può scrivere un ringraziamento.

Ogni coppia dovrà consegnare il cioccolatino allo studente della classe individuata avente come numero di registro il numero scelto. 

Le coppie con bigliettino, dovranno chiedere a chi riceve il cioccolatino di scrivere un breve ringraziamento sul bigliettino.

Al rientro ogni coppia deve raccontare come è andata la consegna.

Uno o due studenti eseguono la funzione del sistema operativo: danno il via libera per la partenza, annotano in un log, ad esempio alla lavagna, la spedizione e il risultato. Dovranno annotare:
- biglietto: si o no
- aula destinatario
- studente destinatario
- orario di partenza

Nel caso dei gruppi con biglietto, dovranno annotare anche il ritorno del gruppo:
- biglietto compilato: si o no
- esito della spedizione
- orario di rientro

Cosa può accadere?

* Cioccolatino inviato con successo, biglietto di ringraziamento individuato e restituito
* Cioccolatino consegnato, ma non è stato possibile compilare il ringraziamento
* L'aula non esiste
* Un alunno col numero di registro indicato non esiste, o era assente
* L'aula era vuota, nessun gruppo aveva lezione in quell'aula
* Il docente della classe non ha acconsentito alla consegna
* Impossibile raggiungere la classe
* Altro

## Fuori di metafora

Un'aula rappresenta un host in una rete locale. Possiamo identificare l'aula con il suo indirizzo: Italiano 1, Matematica 2, Economia 3... Questo dato però non è sufficiente ad identificare uno studente.

Per poter consegnare un cioccolatino ad uno studente preciso abbiamo bisogno di una informazione di indirizzamento in più, che identifichi uno studente di una classe in modo univoco: ad esempio, il numero di registro dello studente.

Lo stesso accade quando un client invia una richiesta ad un server o, viceversa, un server invia una risposta ad un client.

L'indirizzo IP non è sufficiente ad identificare un'applicazione client o server: in un host potremmo avere tanti client o tanti server in esecuzione. E' dunque necessaria una informazione aggiuntiva che, nel protocollo TCP, è costituita da una *Porta TCP*

Ogni applicazione client o server invia o attende comunicazioni su una specifica porta. Quando un pacchetto TCP arriva ad un host, è inoltrato all'applicazione che sta usando la porta indicata nell'intestazione del pacchetto.

Per evitare ambiguità, due server o client non possono lavorare sulla stessa porta. Ai servizi di utilizzo più comune è assegnato sempre lo stesso numero di porta. SI parla in questo caso di *porte note* (*well-known ports*), stabilite da un organismo di standardizzazione detto *IANA*.

### Il firewall

Un docente può negare, per vari motivi, l'accesso all'aula. Nella comunicazione di rete questo è il ruolo svolto dal *firewall*, che ha il compito di filtrare tutte le comunicazioni in ingresso o in uscita in base alla porta di destinazione, o all'indirizzo o porta del mittente, in base ad una configurazione predefinita o stabilita dall'utente.

Il server da noi rappresentato potrebbe essere considerato indesiderato e la comunicazione interrotta. Probabilmente se fosse entrato in aula un collaboratore con una richiesta da parte del dirigente, questa comunicazione sarebbe stata accettata.

### Protocolli orientati alla connessione

I gruppi con bigliettino hanno simulato l'invio usando un protocollo orientato alla connessione. Se il bigliettino è stato compilato e restituito, siamo certi che l'invio ha avuto successo. Altrimenti, non siamo sicuri che l'invio sia stato eseguito correttamente. Questo è il comportamento del protocollo *TCP*, che garantisce al mittente la completezza e correttezza della spedizione.
Se la risposta (*ACK*) non arriva entro un certo tempo, la spedizione va in *Timeout*: il sistema di rete smette di attendere e programma l'invio di una nuova copia del pacchetto.
Questo protocollo viene usato nelle applicazione di rete che richiedono che un messaggio sia inviato in modo corretto e completo: ad esempio nella comunicazione WWW, email, sistemi di messaggistica istantane.

I gruppi senza biglietto hanno invece simulato l'invio usando un protocollo orientato alla velocità di spedizione, come l'*UDP*. Non è stato necessario attendere la compilazione del bigliettino e la sua restituzione, ma non abbiamo certezza che la spedizione sia avvenuta correttamente.
Questo comportamento è utile quando la completezza della comunicazione non è richiesta, ma la velocità è un requisito importante: ad esempio, nell'invio di contenuti multimediali quali audio e video in streaming. 

### Errori di comunicazione

Cosa può accadere, dunque, durante l'invio di un pacchetto TCP?
* La spedizione può avere successo, il destinatario invia un messaggio di conferma
* La spedizione viene effettuata, ma il destinatario non invia un messaggio di conferma
* L'indirizzo di destinazione non esiste (aula inesistente)
* Nell'host di destinazione non esiste un server o un client in ascolto su quella porta (alunno non trovato)
* Il sistema di rete del destinatario non inoltra il messaggio al destinatario, eventualmente a causa della presenza di un firewall
* Errore di rete, impossibile raggiungere il destinatario 



