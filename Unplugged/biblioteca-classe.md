---
marp: true
---

# Biblioteca di classe 

*Esperimenti di routing*

---

Il docente porta in classe alcuni libri. Li consegna a due studenti situati in ultima fila. Questi studenti assumeranno il ruolo di **bibliotecari**

Torna in cattedra e compila un biglietto. Su un lato scrive: richiesta per il bibliotecario. Sull'altro lato il nome del libro che vuole avere.

---

## Preparazione

Avendo già svolto l'attività "cioccolatini in classe", già sappiamo che il biglietto deve essere recapitato al bibliotecario passandolo al compagno più vicino.

:bulb: *Attività preparatoria: ognuno deve valutare in anticipo a chi può passare il biglietto per raggiungere uno dei bibliotecari (o il prof). Compilare una tabella di questo tipo*

| Destinatario | Vicino | Direzione | Tempo stimato |
|--------------|--------|-----------|---------------|
| Biblio1      | Luca   | Sinistra  | 2s            |
| ...          | ...    |  ...      | ...           |

**possiamo anche indicare più percorsi verso uno stesso destinatario**

---

## Inviamo richieste e risposte

Il prof poi consegna il biglietto ad uno degli studenti in prima fila, chiedendo di farlo arrivare al bibliotecario, senza alzarsi.

Lo studente dovrà farlo arrivare al bibliotecario, passandolo allo studente che, secondo la tabella di routing, è stato scelto come percorso migliore per aggiungere il destinatario.

A questo modo, di mano in mano, il biglietto raggiunge il bibliotecario, il quale prepara il libro e lo invia al destinatario, indicandone il nome sul biglietto.

---

## Tracciamo il percorso

Inviando un biglietto, incaricare una coppia di studenti di annnotare:
- per quali studenti il biglietto è passato
- quanto tempo è stato impiegato ad arrivare ad ogni studente

---

# Traceoute

Abbiamo così simulato il funzionamento del comando **traceroute**

Questo comando, che si può lanciare da terminale a questo modo:

```
> traceroute google.it
> traceroute 8.8.4.4
```

consente di visualizzare tutti i router che la nostra richiesta attraversa prima di giungere al destinatario specificato come parametro. E' anche riportato un tempo (approssimato) impiegato a raggiungere ognuno dei router intermedi




