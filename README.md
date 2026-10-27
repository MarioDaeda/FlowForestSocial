# FlowForestSocial

## Hook Instagram: workflow

1. **Ricerca (ogni 3-6 mesi):** compila "Contesto canale" in `prompts/ricerca-hook-instagram.md`
   e lancialo in una sessione Claude Code. Produce `knowledge/instagram-hooks/guida.md`
   (guida breve con fonti) e gli estratti in `knowledge/instagram-hooks/fonti/`.
2. **Ogni nuovo video:** chiedi a Claude l'hook (o usa `/hook-instagram`) con argomento o script.
   La skill legge la guida, propone 5 hook, li valuta con la rubrica e ne sceglie 2 da testare.
3. **Dopo la pubblicazione:** incolla le metriche degli Insights; finiscono in
   `knowledge/instagram-hooks/registro-hook.csv`. Dopo 5+ video i dati del canale
   guidano le scelte più della guida generica.
