# Ping pong

Oggi in classe si gioca a ping pong. Il professore si procura una pallina e prova a "pingare" gli studenti lanciando loro la pallina.

Il docente deve lanciare la pallina a vari studenti, a turno. Ogni studente che la riceve deve, a sua volta, rilanciarla al prof.

Inviare la pallina anche a studenti assenti.

Uno studente viene incaricato di eseguire un'attività di cronometraggio, usando ad esempio uno smartphone: deve far partire il cronometro nel momento in cui il professore lancia la pallina e bloccare nel momento in cui lo stesso professore la riceve.
Un'altro studente deve annotare alla lavagna l'esito del lancio:
- FALLITO: pallina non restituita entro un tempo prefissato, ad esempio 30 secondi
- RIUSCITO: annotare il tempo intercorso tra il momento in cui il professore ha lanciato la pallina e quando l'ha riavuta indietro.

- Osservazione 1: Quali informazioni sugli studenti possiamo dedurre da questa attività? L'abilità dello studente nell'acchiappare la pallina al volo non conta.

Possiamo anche provare a lanciare più volte la pallina ad uno stesso studente. Potremmo calcolare il tempo di risposta complessivo calcolando la media dei tempi di ricezione dei vari lanci.

## Fuori di metafora

*ping* è un servizio di rete che consente di sapere se un host è raggiungibile dal nostro computer. Consiste nell'invio di un piccolo pacchetto dati all'host su cui vogliamo avere informazioni, identificandolo con il suo indirizzo IP.

Possiamo utilizzare questo servizio da terminale, eseguendo:

```
ping <IP destinazione>
```

Gli studenti a cui il docente ha lanciato la pallina rappresentano gli *host* su cui il professore vuole raccogliere informazioni.

Quali informazioni sono fornite dall'utilizzo di questa applicazione?

1) se l'host destinatario è raggiungibile. Se entro un certo tempo il pacchetto dati inviato non viene ricevuto, l'applicazione ping indica un errore di rete (*timeout*: tempo di attesa scaduto!)
2) la *latenza* della comunicazione: il tempo necessario al pacchetto dati di prova per raggiungere l'host destinatario e tornare. Viene espressa in ms, millisecondi, dunque un'unità di tempo.
Una rete più veloce ha un valore di latenza più bassa, una rete più lenta presenta valori di latenza più alti. 