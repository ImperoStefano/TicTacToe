# Tris Svanente

Un Tris (Tic Tac Toe) a due giocatori sullo stesso tabellone 3×3. La svolta: ogni giocatore può
avere solo un numero massimo di simboli in campo — appena ne piazza uno in più, il suo simbolo più
vecchio svanisce. Bisogna quindi pensare non solo a fare tris, ma anche a *quando* i propri segni
stanno per sparire.

Estetica ispirata al set "Lucite Tic Tac Toe": tabellone come vassoio acrilico con i rivetti agli
angoli, sfondo lavanda, O arancio e X lime — gli stessi colori e forme dei pezzi acrilici della
foto di riferimento. Il simbolo più vecchio, prima di svanire, lampeggia per avvisarti.

**Fatto da Stefano Kolta**

## File inclusi

- `tris-svanente.html` — il gioco completo. Un solo file, nessuna dipendenza esterna, nessuna
  installazione: si apre semplicemente in un browser.
- `README.md` — questo documento.

## Come si gioca

1. All'avvio inserisci solo i nickname dei due giocatori (O arancio = Giocatore 1, X lime =
   Giocatore 2). Ogni giocatore può tenere al massimo **4 simboli** sul tabellone
   contemporaneamente (regola fissa).
2. I giocatori si alternano cliccando/toccando una cella vuota per piazzare il proprio simbolo.
3. **Meccanica di svanimento**: se un giocatore ha già 4 simboli in campo e ne piazza un altro, il
   suo simbolo più vecchio ancora presente sul tabellone **svanisce automaticamente**, lasciando la
   cella libera. Il simbolo che sta per svanire lampeggia già dal turno prima, così sai a cosa stai
   rinunciando se giochi ancora.
4. Vince il round chi fa **tre in fila** (riga, colonna o diagonale) con i simboli attualmente
   presenti sul tabellone, dopo che l'eventuale svanimento è avvenuto.
5. Se il tabellone si riempie senza che nessuno faccia tris, il round finisce in pareggio (nessun
   punto assegnato).
6. Il pannello centrale mostra sempre **di chi è il turno** (banner colorato + scheda giocatore
   evidenziata), mentre le due schede laterali mostrano nickname e punteggio (numero di round
   vinti) di ciascun giocatore.
7. Alla fine di ogni round si può passare subito al successivo mantenendo il punteggio, oppure
   ricominciare tutto da capo (nickname e punteggi azzerati).

## Controlli

Si gioca semplicemente **cliccando o toccando** una cella vuota della griglia: nessuna tastiera
necessaria. L'interfaccia è ottimizzata anche per smartphone: su schermi stretti le due schede dei
giocatori si affiancano sotto al tabellone (che si ingrandisce per sfruttare lo spazio), i campi
della schermata iniziale non attivano lo zoom automatico di iOS, e le finestre di dialogo restano
leggibili anche sui telefoni più piccoli.

## Animazioni e rifiniture

- **Linea vincente**: quando qualcuno fa tris, una linea colorata (nel colore del vincitore) si
  disegna con un'animazione fluida sopra le tre celle vincenti, che pulsano con un leggero alone
  luminoso. Il tabellone resta visibile per un istante prima che si apra la finestra di fine round,
  così si vede bene la combinazione vincente.
- **Comparsa dei simboli**: ogni O o X piazzato entra con un piccolo effetto di rimbalzo, invece di
  apparire di scatto.
- **Svanimento animato**: il simbolo che sta per svanire lampeggia già dal turno prima; quando
  sparisce davvero, si rimpicciolisce e ruota leggermente invece di scomparire di colpo.
- **Click non validi**: cliccare su una cella già occupata la fa vibrare leggermente, per segnalare
  che la mossa non è valida.
- **Cambio turno**: il nome del giocatore attivo ha una piccola animazione di comparsa ad ogni
  cambio turno, oltre al banner colorato.
- **Finestre di dialogo**: la schermata iniziale e quella di fine round entrano con una dissolvenza
  e un leggero effetto di scala, invece di comparire bruscamente.

## Note tecniche

- Nessuna libreria esterna: HTML, CSS e JavaScript vanilla in un unico file.
- Ogni giocatore ha una propria coda (in ordine di piazzamento) dei simboli sul tabellone: quando
  la coda supera il massimo consentito, il simbolo più vecchio (in testa alla coda) viene rimosso.
- Il controllo del tris avviene *dopo* l'eventuale svanimento, quindi conta sempre lo stato finale
  del tabellone al termine della mossa.
- La linea vincente è un elemento SVG disegnato dinamicamente in base alla posizione reale delle
  celle, quindi resta perfettamente allineata a qualunque dimensione del tabellone.

Buon divertimento!
