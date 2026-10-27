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

- Pagina: FlowForest, profilo Instagram `@<handle>`, dedicata a un bosco reale, pubblico italiano.
- Formato: **nessuna voce, nessun parlato.** Musica + scene di paesaggio del bosco + persone che fanno attività nel bosco.
  Gli unici strumenti di hook sono quindi: **primo frame/immagine, movimento e montaggio, testo a schermo, scelta e attacco della musica, prima riga della caption, copertina**.
- Filoni: paesaggi e stagioni (luce, nebbia, colori, meteo) · persone e attività nel bosco · dettagli e natura ravvicinata (fauna, piante, acqua).
- Durata Reel: **15-30 secondi.**
- Obiettivo di oggi: **engagement per far conoscere il bosco** (condivisioni, salvataggi, commenti, follow, visite).
- Obiettivo futuro: usare Instagram come **mezzo pubblicitario** (Reel promossi/inserzioni). La guida deve indicare cosa cambia per gli hook nei Reel usati come ads.

Il tono del bosco è lento e contemplativo; l'hook deve fermare lo scroll **senza voce e senza tradire quell'atmosfera**.
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
5. Nei contenuti natura senza voce i primi secondi funzionano meglio con **movimento o rivelazione visiva** (animale, cambio di luce, prima/dopo, persona che entra in scena) che con un'inquadratura statica. Verificalo sugli esempi C.
6. Gli account aziendali hanno una libreria musicale limitata (es. Meta Sound Collection) e i Reel promossi richiedono musica con licenza commerciale; gli audio di tendenza possono non essere utilizzabili. Verifica le regole attuali.
7. I Reel sotto i 30 secondi beneficiano di loop e rewatch (il finale che si ricollega all'inizio aumenta il tempo di visione).

## Domande di ricerca

1. Cosa dice Instagram **oggi** sui primi secondi e sulla retention (fonte A)?
2. Senza voce, quali hook mostrano dati migliori: visivo/primo frame, testo a schermo, attacco musicale, combinazioni? Con quali numeri?
3. Come aprono i Reel **senza parlato** i creator e i luoghi natura/outdoor che crescono adesso (paesaggi, cinematic nature, rifugi, parchi, agriturismi, esperienze nel bosco)? Raccogli **10-15 hook reali** con primo frame, testo a schermo, musica e durata.
4. Come si concilia l'atmosfera rilassante con lo stop dello scroll? Ritmo dei tagli nei primi 3 secondi, attacco della musica sul primo frame, suono ambiente vs musica.
5. Quali testi a schermo funzionano per un luogo da far conoscere (es. "Questo bosco è a 40 minuti da <città>", "POV: ...", domanda, stagionalità "il bosco a novembre")? Lunghezza, posizione, durata a schermo.
6. Come costruire un Reel di 15-30 secondi che si guarda fino alla fine e in loop, e che spinge a **condividere** ("mandalo a chi ci verrebbe con te"), salvare e venire a visitare?
7. Prima riga della caption, copertina e posizione taggata: quanto contano per scoperta e engagement di un luogo?
8. Hook per Reel usati come **inserzioni**: cosa cambia (primi secondi, testo, call to action, musica con licenza, regole Meta Ads)?
9. Quali formule sono saturate o penalizzate (clickbait, promessa non mantenuta) e cosa è **rischioso nel bosco** (disturbare animali, mostrare attività pericolose o non consentite, suggerire raccolta di funghi o piante)?
10. Come girare il primo frame nel bosco: luce bassa, inquadratura verticale e safe zone, stabilizzazione, testo leggibile su sfondi verdi e complessi.
11. Come misurare e testare un hook con gli strumenti nativi (nomi esatti delle metriche e dove si trovano)?

## Metodo (ottimizzato per i token)

1. **Ricerca a tre binari in parallelo.** Se puoi lanciare subagent, avviane 3 (va bene un modello economico), uno per binario:
   fonti A · studi B · nicchia natura/bosco C. Ognuno restituisce **massimo 350 parole** in punti elenco,
   ogni punto con `[n]` e una riga fonte (titolo · editore · data · URL · livello A/B/C). Niente testo copiato lungo.
   Senza subagent, fai i tre binari in sequenza con le stesse regole.
2. **Prima ricerche mirate, poi apri solo le pagine migliori.** Usa la ricerca web in modalità standard; passa a "extended" solo se i risultati sono scarsi o datati.
   Query di partenza (adattale, aggiungi l'anno corrente):
   - A: `Adam Mosseri Reels ranking signals <anno>` · `Instagram "skip rate" Reels insights` · `Instagram Trial Reels how it works`
   - B: `Instagram Reels first 3 seconds retention study <anno>` · `Instagram Reels benchmark report <anno>`
   - B: `Instagram business account music licensing Reels` · `Meta Reels ads best practices first seconds`
   - C: `cinematic nature Reels no talking hook` · `faceless nature reels` · `travel destination Reels hook examples` ·
     `outdoor experience Instagram reels` · `reel bosco <anno>` · `promuovere un luogo con i Reel`
3. **Leggi con estrazione mirata.** Quando apri una pagina, estrai solo i passaggi su hook, retention, primi secondi, metriche e riprese in natura; non riassumere tutta la pagina.
   Limite: **massimo 14 fonti lette** in tutto, almeno 3 di livello A e almeno 4 di livello C della nicchia.
4. **"Scarica" in forma leggera.** Per ogni fonte usata salva `knowledge/instagram-hooks/fonti/NN-slug.md` con:
   URL, titolo, editore, data di pubblicazione, data di accesso, livello e **solo gli estratti rilevanti** (citazioni brevi e tue note).
   Non salvare pagine intere (diritti d'autore e token).
5. **Verifica incrociata.** Ogni affermazione numerica o sull'algoritmo deve avere una fonte A o B. Se due fonti si contraddicono, riportalo nella sezione apposita invece di scegliere a caso.
   Se un dato non è verificabile, scrivi "non verificato".
6. **Scrivi la guida** nel formato qui sotto. Poi rileggila da scettico: elimina tutto ciò che non cambia come FlowForest scrive o gira un hook.

## Formato output: `knowledge/instagram-hooks/guida.md`

Massimo ~2000 parole. In testa: `Aggiornata al: <data>` e `Prossima revisione: <data + 4 mesi>`. Sezioni con questi titoli esatti:

1. `## Sintesi` — 8-10 regole operative per FlowForest, una riga ciascuna.
2. `## Come Instagram valuta i primi secondi` — solo fonti A, con `[n]`.
3. `## Tipi di hook e formule` — tabella: tipo · quando usarlo · formula template in italiano · esempio FlowForest · evidenza `[n]`.
   Solo hook **senza voce**: primo frame/visivo (rivelazione, movimento, prima/dopo, persona che entra in scena), testo a schermo, attacco musicale e le combinazioni.
4. `## Hook per filone` — per ogni filone FlowForest: 2 formule pronte (primo frame + testo a schermo + tipo di musica).
5. `## Struttura 15-30 secondi` — scaletta tipo secondo per secondo (hook, sviluppo, payoff, loop) e dove mettere la call to action.
6. `## Girare il primo frame nel bosco` — checklist tecnica breve (luce, inquadratura, stabilizzazione, testo leggibile, copertina).
7. `## Musica` — come sceglierla e farla attaccare sul primo frame, cosa si può usare con un account aziendale e nelle inserzioni.
8. `## Dai Reel organici alle inserzioni` — cosa cambia per gli hook quando un Reel diventa pubblicità.
9. `## Cosa evitare` — errori, formule saturate o penalizzate e rischi specifici del bosco, con motivo.
10. `## Rubrica` — tabella di 5-7 criteri, punteggio 0-2 ciascuno, con cosa vale 0/1/2.
    Tra i criteri includi: comprensibile senza audio, coerenza con l'atmosfera FlowForest, promessa mantenuta, voglia di condividere/visitare. Sarà usata per dare un voto a ogni hook.
11. `## Test e misurazione` — quali metriche guardare (nome esatto negli Insights), dopo quanto tempo, soglie indicative se esistono dati, come usare i Trial Reels per l'A/B.
12. `## Incertezze e contraddizioni`
13. `## Fonti` — tabella: n · titolo · editore/autore · data · livello · URL.

## Integrazione e chiusura

1. Aggiorna `knowledge/instagram-hooks/registro-hook.csv` solo se servono colonne nuove per metriche emerse dalla ricerca; non cancellare righe esistenti.
2. Se il registro ha già almeno 5 video con metriche, aggiungi alla guida la sezione `## Cosa funziona su FlowForest` confrontando i tipi di hook: i dati della pagina hanno la precedenza su quelli generici.
3. Fai commit con messaggio chiaro e push sul branch di lavoro.
4. Rispondimi in **massimo 10 righe**: le 3 scoperte più importanti per FlowForest, cosa è cambiato rispetto alle ipotesi e i punti non verificati.
