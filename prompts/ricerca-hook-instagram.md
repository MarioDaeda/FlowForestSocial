# Prompt: guida agli hook Instagram per FlowForest

> Come usarlo: incolla tutto il blocco qui sotto in una nuova sessione di Claude Code
> aperta su questo repository (oppure lancialo con `claude -p "$(cat prompts/ricerca-hook-instagram.md)"`).
> Prima conferma o correggi la sezione **FlowForest**. Rilancialo ogni 3-6 mesi: l'algoritmo cambia.

---

## Obiettivo

Costruisci una guida pratica e aggiornata su **come scrivere e girare gli hook (primi 1-3 secondi) dei Reel di FlowForest**,
la pagina Instagram dedicata al bosco, basata su fonti attendibili e recenti.
Salvala in `knowledge/instagram-hooks/guida.md`.
La guida verrà letta dalla skill `.claude/skills/hook-instagram` per scrivere gli hook di ogni nuovo video,
quindi deve essere **breve, operativa, con esempi sul bosco e con struttura fissa** (vedi "Formato output").

Data di oggi: usala per calcolare la finestra di recency. "Recente" = ultimi 12 mesi.

## FlowForest (conferma o correggi prima di lanciare)

- Pagina: FlowForest, profilo Instagram `@<handle>`, contenuti sul bosco, in italiano.
- Filoni di contenuto (tieni quelli veri, aggiungi i mancanti):
  vita nel bosco e stagioni · alberi e piante · fauna (tracce, avvistamenti) · funghi e raccolta ·
  lavori nel bosco (legna, sentieri, cura) · suoni e momenti di relax · curiosità scientifiche e miti da sfatare.
- Formato tipico: `<voce fuori campo su riprese / talking head nel bosco / solo musica e testo>`
- Durata media dei Reel: `<...>` secondi
- Obiettivo principale: `<crescita follower / condivisioni / community locale / altro>`

Il tono del bosco tende al lento e contemplativo; l'hook deve fermare lo scroll **senza tradire quell'atmosfera**.
È il nodo centrale da risolvere nella guida.

## Gerarchia delle fonti (rispettala)

| Livello | Tipo | Esempi | Uso |
|---|---|---|---|
| **A** | Ufficiali Instagram/Meta | Adam Mosseri (post/video su IG, Threads), account @creators, about.instagram.com ("Instagram Ranking Explained"), Help Center e Professional Dashboard, Meta for Creators | Verità su come funziona la distribuzione |
| **B** | Studi con dati dichiarati | Report con campione e metodologia (es. Buffer, Later, Hootsuite, Sprout Social, Metricool, Socialinsider, Rival IQ, Dash Hudson) | Cosa funziona in media, con numeri |
| **C** | Creator della nicchia natura/bosco | Divulgatori forestali e naturalistici italiani (es. From Roots to Leaves) e creator internazionali nature/outdoor/foraging con profili molto seguiti | Solo formule ed esempi reali, mai come prova |

Scarta: listicle senza dati né data, pagine SEO generiche, contenuti più vecchi di 24 mesi
(salvo fonti A ancora valide, segnalandolo), affermazioni su "l'algoritmo" non riconducibili a una fonte A o a dati B.

## Ipotesi da verificare (non darle per vere)

Partono da conoscenze precedenti e possono essere superate. Per ognuna: confermata / smentita / cambiata, con fonte.

1. Per i Reel i segnali chiave sono tempo di visione, like per reach e **condivisioni (sends) per reach**; queste ultime pesano molto sulla reach verso non follower.
2. Negli Insights dei Reel esiste una metrica di **skip rate** (quota di chi scorre via nei primi ~3 secondi).
3. I **Trial Reels** permettono di testare un Reel su non follower prima di mostrarlo ai follower.
4. Instagram privilegia contenuti originali e penalizza repost, aggregatori e watermark di altre app (rilevante per riprese naturalistiche spesso ripubblicate).
5. Nei contenuti natura i primi secondi funzionano meglio con **movimento o rivelazione visiva** (animale, cambio di luce, prima/dopo) che con una persona che parla. Verificalo sugli esempi C.

## Domande di ricerca

1. Cosa dice Instagram **oggi** sui primi secondi e sulla retention (fonte A)?
2. Quali tipi di hook mostrano dati migliori (verbale, testo a schermo, visivo/primo frame, audio)? Con quali numeri?
3. Come aprono i Reel i creator natura/bosco che crescono adesso? Raccogli **10-15 hook reali** con tipo, primo frame e testo a schermo.
4. Come si concilia l'atmosfera rilassante (suoni del bosco, ritmo lento) con lo stop dello scroll? Suono naturale o voce nel primo secondo?
5. Quali hook funzionano per ciascun filone FlowForest? Pensa in particolare a curiosità, stagionalità ("cosa succede nel bosco a novembre"), miti da sfatare e momenti di "rivelazione".
6. Quali formule sono saturate o penalizzate (clickbait, promessa non mantenuta) e quali sono **rischiose nel bosco**?
   Per esempio: indicare funghi o piante come commestibili da un video, disturbare animali, ignorare le regole regionali sulla raccolta.
7. Come girare il primo frame nel bosco: luce bassa, inquadratura verticale e safe zone, vento sul microfono, testo leggibile su sfondi verdi e complessi.
8. Come misurare e testare un hook con gli strumenti nativi (nomi esatti delle metriche e dove si trovano)?

## Metodo (ottimizzato per i token)

1. **Ricerca a tre binari in parallelo.** Se puoi lanciare subagent, avviane 3 (va bene un modello economico), uno per binario:
   fonti A · studi B · nicchia natura/bosco C. Ognuno restituisce **massimo 350 parole** in punti elenco,
   ogni punto con `[n]` e una riga fonte (titolo · editore · data · URL · livello A/B/C). Niente testo copiato lungo.
   Senza subagent, fai i tre binari in sequenza con le stesse regole.
2. **Prima ricerche mirate, poi apri solo le pagine migliori.** Usa la ricerca web in modalità standard; passa a "extended" solo se i risultati sono scarsi o datati.
   Query di partenza (adattale, aggiungi l'anno corrente):
   - A: `Adam Mosseri Reels ranking signals <anno>` · `Instagram "skip rate" Reels insights` · `Instagram Trial Reels how it works`
   - B: `Instagram Reels first 3 seconds retention study <anno>` · `Instagram Reels benchmark report <anno>`
   - C: `nature Instagram Reels hook examples` · `forest creator Instagram reels` · `foraging reels hook` ·
     `nature ASMR reels retention` · `divulgazione bosco Instagram` · `reel natura hook <anno>`
3. **Leggi con estrazione mirata.** Quando apri una pagina, estrai solo i passaggi su hook, retention, primi secondi, metriche e riprese in natura; non riassumere tutta la pagina.
   Limite: **massimo 14 fonti lette** in tutto, almeno 3 di livello A e almeno 4 di livello C della nicchia.
4. **"Scarica" in forma leggera.** Per ogni fonte usata salva `knowledge/instagram-hooks/fonti/NN-slug.md` con:
   URL, titolo, editore, data di pubblicazione, data di accesso, livello e **solo gli estratti rilevanti** (citazioni brevi e tue note).
   Non salvare pagine intere (diritti d'autore e token).
5. **Verifica incrociata.** Ogni affermazione numerica o sull'algoritmo deve avere una fonte A o B. Se due fonti si contraddicono, riportalo nella sezione apposita invece di scegliere a caso.
   Se un dato non è verificabile, scrivi "non verificato".
6. **Scrivi la guida** nel formato qui sotto. Poi rileggila da scettico: elimina tutto ciò che non cambia come FlowForest scrive o gira un hook.

## Formato output: `knowledge/instagram-hooks/guida.md`

Massimo ~1800 parole. In testa: `Aggiornata al: <data>` e `Prossima revisione: <data + 4 mesi>`. Sezioni con questi titoli esatti:

1. `## Sintesi` — 8-10 regole operative per FlowForest, una riga ciascuna.
2. `## Come Instagram valuta i primi secondi` — solo fonti A, con `[n]`.
3. `## Tipi di hook e formule` — tabella: tipo · quando usarlo · formula template in italiano · esempio FlowForest · evidenza `[n]`.
   Copri almeno: verbale, testo a schermo, visivo/primo frame (rivelazione, movimento, prima/dopo), audio (suono del bosco vs voce) e le combinazioni.
4. `## Hook per filone` — per ogni filone FlowForest: 2 formule pronte e il tipo di primo frame consigliato.
5. `## Girare il primo frame nel bosco` — checklist tecnica breve (luce, inquadratura, audio, testo leggibile).
6. `## Cosa evitare` — errori, formule saturate o penalizzate e rischi specifici del bosco, con motivo.
7. `## Rubrica` — tabella di 5-7 criteri, punteggio 0-2 ciascuno, con cosa vale 0/1/2.
   Tra i criteri includi la coerenza con l'atmosfera FlowForest e la promessa mantenuta. Sarà usata per dare un voto a ogni hook.
8. `## Test e misurazione` — quali metriche guardare (nome esatto negli Insights), dopo quanto tempo, soglie indicative se esistono dati, come usare i Trial Reels per l'A/B.
9. `## Incertezze e contraddizioni`
10. `## Fonti` — tabella: n · titolo · editore/autore · data · livello · URL.

## Integrazione e chiusura

1. Aggiorna `knowledge/instagram-hooks/registro-hook.csv` solo se servono colonne nuove per metriche emerse dalla ricerca; non cancellare righe esistenti.
2. Se il registro ha già almeno 5 video con metriche, aggiungi alla guida la sezione `## Cosa funziona su FlowForest` confrontando i tipi di hook: i dati della pagina hanno la precedenza su quelli generici.
3. Fai commit con messaggio chiaro e push sul branch di lavoro.
4. Rispondimi in **massimo 10 righe**: le 3 scoperte più importanti per FlowForest, cosa è cambiato rispetto alle ipotesi e i punti non verificati.
