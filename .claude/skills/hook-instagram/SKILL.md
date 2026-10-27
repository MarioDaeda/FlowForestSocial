---
name: hook-instagram
description: Scrive, valuta e registra gli hook (primi 1-3 secondi) dei prossimi Reel Instagram applicando la guida in knowledge/instagram-hooks/guida.md. Usala quando si prepara un nuovo video, uno script o una caption per Instagram, quando si chiede "fammi l'hook", "come apro questo video", o quando si inseriscono i risultati di un Reel pubblicato.
---

# Hook Instagram per i prossimi video

## Prima di tutto

1. Leggi `knowledge/instagram-hooks/guida.md`, solo le sezioni `Sintesi`, `Tipi di hook e formule`, `Cosa evitare`, `Rubrica`.
   Se il file non esiste, fermati e di' di lanciare prima `prompts/ricerca-hook-instagram.md`.
2. Se la data in `Prossima revisione` è passata, segnalalo in una riga (non bloccare il lavoro).
3. Leggi `knowledge/instagram-hooks/registro-hook.csv`. Se ha almeno 5 righe con metriche,
   dai priorità ai tipi di hook che hanno performato meglio sul canale.

## Modalità A: nuovo video

Input: argomento o script del video (e, se c'è, il momento più forte del video).

1. Individua la **promessa** del video in una frase: cosa ottiene chi guarda fino alla fine.
2. Scrivi **5 hook di tipi diversi** (dalla tabella della guida). Per ognuno indica:
   - battuta parlata (max ~12 parole, si dice in meno di 3 secondi)
   - testo a schermo (max ~7 parole, diverso dalla battuta ma coerente)
   - primo frame / azione visiva
3. Valuta ognuno con la `Rubrica` della guida (tabella compatta, punteggio totale).
   Scarta quelli che promettono più di quanto il video mantiene.
4. Consiglia **i 2 migliori** come test A/B (es. uno sul Reel principale, uno come Trial Reel, se la guida lo conferma).
5. Aggiungi le righe dei 2 hook scelti al registro con `stato=pianificato` e metriche vuote.

Output: breve, una tabella + raccomandazione in 2 righe. Niente teoria ripetuta dalla guida.

## Modalità B: risultati di un Reel pubblicato

Input: metriche dagli Insights (o screenshot).

1. Aggiorna la riga del video nel registro (`stato=pubblicato`, metriche, data).
2. Confronta con la mediana del canale nel registro e scrivi una riga di lettura (meglio/peggio e probabile perché).
3. Ogni 5 video nuovi, proponi in 3 righe cosa cambiare nella guida (sezione `Cosa funziona sul nostro canale`).
