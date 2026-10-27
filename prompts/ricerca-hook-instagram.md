# Prompt: ricerca e guida sugli hook per Instagram

> Come usarlo: incolla tutto il blocco qui sotto in una nuova sessione di Claude Code
> aperta su questo repository (oppure lancialo con `claude -p "$(cat prompts/ricerca-hook-instagram.md)"`).
> Prima compila la sezione **Contesto canale**. Rilancialo ogni 3-6 mesi: l'algoritmo cambia.

---

## Obiettivo

Costruisci una guida pratica e aggiornata su **come scrivere e girare hook (primi 1-3 secondi) per Reel Instagram**,
basata su fonti attendibili e recenti, e salvala in `knowledge/instagram-hooks/guida.md`.
La guida verrà letta dalla skill `.claude/skills/hook-instagram` per scrivere gli hook di ogni nuovo video,
quindi deve essere **breve, operativa e con struttura fissa** (vedi "Formato output").

Data di oggi: usala per calcolare la finestra di recency. Considera "recente" = ultimi 12 mesi.

## Contesto canale (compila prima di lanciare)

- Nicchia / argomenti: `<...>`
- Pubblico target: `<...>`
- Lingua dei video: italiano
- Formato tipico (talking head, b-roll + voce, tutorial, ecc.): `<...>`
- Durata media Reel: `<...>`

## Gerarchia delle fonti (rispettala)

| Livello | Tipo | Esempi | Uso |
|---|---|---|---|
| **A** | Ufficiali Instagram/Meta | Adam Mosseri (post/video su IG, Threads), account @creators, about.instagram.com ("Instagram Ranking Explained"), Help Center e Professional Dashboard, blog Meta for Creators/Business | Verità su come funziona la distribuzione |
| **B** | Studi con dati dichiarati | Report con campione e metodologia (es. Buffer, Later, Hootsuite, Sprout Social, Metricool, Socialinsider, Rival IQ, Dash Hudson) | Cosa funziona in media, con numeri |
| **C** | Praticanti riconosciuti | Creator/strategist con risultati verificabili che mostrano esempi concreti | Solo formule ed esempi, mai come prova |

Scarta: listicle senza dati né data, pagine SEO generiche, contenuti più vecchi di 24 mesi
(salvo fonti A ancora valide, segnalandolo), affermazioni su "l'algoritmo" non riconducibili a una fonte A o a dati B.

## Ipotesi da verificare (non darle per vere)

Partono dalla conoscenza pregressa e possono essere superate. Per ognuna: confermata / smentita / cambiata, con fonte.

1. Per i Reel i segnali chiave sono tempo di visione, like per reach e **condivisioni (sends) per reach**, queste ultime pesanti per la reach verso non follower.
2. Negli Insights dei Reel esiste una metrica di **skip rate** (quota di chi scorre via nei primi ~3 secondi).
3. I **Trial Reels** permettono di testare un Reel su non follower prima di mostrarlo ai follower.
4. Instagram privilegia contenuti originali e penalizza repost/aggregatori e watermark di altre app.
5. La durata massima dei Reel e la loro diffusione sono cambiate di recente (verifica i limiti attuali).

## Domande di ricerca

1. Cosa dice Instagram **oggi** sui primi secondi e sulla retention (fonte A)?
2. Quali tipi di hook mostrano dati migliori (verbale, testo a schermo, visivo/pattern interrupt, audio)? Con quali numeri?
3. Quali formule di hook funzionano adesso e quali sono saturate o penalizzate (clickbait, promessa non mantenuta)?
4. Come combinare hook verbale + testo a schermo + primo frame (safe zone, leggibilità, sottotitoli)?
5. Come misurare e testare un hook con gli strumenti nativi (metriche esatte e dove si trovano)?

## Metodo (ottimizzato per i token)

1. **Ricerca a tre binari in parallelo.** Se puoi lanciare subagent, avviane 3 (modello economico va bene), uno per binario:
   fonti A · studi B · formule/esempi C. Ognuno restituisce **massimo 350 parole** in punti elenco,
   ogni punto con `[n]` e una riga fonte (titolo · editore · data · URL · livello A/B/C). Niente testo copiato lungo.
   Senza subagent, fai i tre binari in sequenza con le stesse regole.
2. **Query mirate prima, poi apri solo le pagine migliori.** Usa la ricerca web in modalità standard; passa a "extended" solo se i risultati sono scarsi o datati.
   Query di partenza (adattale, aggiungi l'anno corrente):
   - `Adam Mosseri Reels ranking signals <anno>`
   - `Instagram "skip rate" Reels insights`
   - `Instagram Trial Reels how it works`
   - `Instagram Reels first 3 seconds retention study <anno>`
   - `Reels hook types data study <anno>` · `Instagram Reels benchmark report <anno>`
   - `hook Reel Instagram <anno>` (fonti italiane, solo come livello C)
3. **Leggi con estrazione mirata.** Quando apri una pagina, chiedi solo i passaggi su hook, retention, primi secondi e metriche; non riassumere l'intera pagina.
   Limite: **massimo 12 fonti lette** in tutto, almeno 3 di livello A.
4. **"Scarica" in forma leggera.** Per ogni fonte usata salva `knowledge/instagram-hooks/fonti/NN-slug.md` con:
   URL, titolo, editore, data pubblicazione, data accesso, livello, e **solo gli estratti rilevanti** (citazioni brevi + tue note).
   Non salvare pagine intere (diritti d'autore e token).
5. **Verifica incrociata.** Ogni affermazione numerica o sull'algoritmo deve avere una fonte A o B. Se due fonti si contraddicono, riportalo nella sezione apposita invece di scegliere a caso.
   Se un dato non è verificabile, scrivi "non verificato".
6. **Scrivi la guida** nel formato sotto. Poi rileggila da scettico: elimina tutto ciò che non cambia come si scrive o si gira un hook.

## Formato output: `knowledge/instagram-hooks/guida.md`

Massimo ~1500 parole. Intestazione con `Aggiornata al: <data>` e `Prossima revisione: <data + 4 mesi>`. Sezioni con questi titoli esatti:

1. `## Sintesi` — 8-10 regole operative, una riga ciascuna.
2. `## Come Instagram valuta i primi secondi` — solo fonti A, con `[n]`.
3. `## Tipi di hook e formule` — tabella: tipo · quando usarlo · formula template in italiano · esempio adattato al Contesto canale · evidenza `[n]`.
   Copri almeno: verbale, testo a schermo, visivo/primo frame, audio, e le combinazioni.
4. `## Cosa evitare` — errori e formule saturate/penalizzate, con motivo.
5. `## Rubrica` — tabella di 5-7 criteri, punteggio 0-2 ciascuno, con descrizione di cosa vale 0/1/2. Sarà usata per dare un voto a ogni hook.
6. `## Test e misurazione` — quali metriche guardare (nome esatto negli Insights), dopo quanto tempo, soglie indicative se esistono dati, come usare i Trial Reels per A/B.
7. `## Incertezze e contraddizioni`
8. `## Fonti` — tabella: n · titolo · editore/autore · data · livello · URL.

## Integrazione e chiusura

1. Aggiorna `knowledge/instagram-hooks/registro-hook.csv` solo se serve aggiungere colonne per metriche emerse dalla ricerca (es. skip rate); non cancellare righe esistenti.
2. Se il registro ha già almeno 5 video con metriche, aggiungi alla guida una sezione `## Cosa funziona sul nostro canale` confrontando i tipi di hook: i dati del canale hanno la precedenza su quelli generici.
3. Fai commit con messaggio chiaro e push sul branch di lavoro.
4. Rispondimi in **massimo 10 righe**: le 3 scoperte più importanti, cosa è cambiato rispetto alle ipotesi, e i punti non verificati.
