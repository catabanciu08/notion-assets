# Roadmap notion-assets

Sursă: auditul din 2026-09-17, secțiunea 8. Proiectul nu are fază alocată în programul 2026-09; totul e backlog. Majoritatea schimbărilor se fac în skill-ul `tutorial-report`, nu aici.

## Backlog

- [ ] `manifest.json` cu `videoId → { notionPageUrl, videoTitle, sourceUrl, extractedAt, frameCount }` — fără el niciun cadru nu poate fi șters vreodată în siguranță; de aici pornește orice politică de retenție.
- [ ] Compresie la ingest: `.webp` la ~80 calitate înainte de commit — 60–70 % mai mic decât JPEG pentru diagrame și slide-uri; se compune în timp. (Atenție: schema URL se schimbă din `.jpg` în `.webp` doar pentru cadrele noi.)
- [ ] Cap de cadre per video (~6–8) și deduplicare perceptuală a cadrelor consecutive aproape identice înainte de commit — mai multe foldere au cadre la secunde distanță.
- [ ] Un commit per video, cu titlul videoclipului în mesaj, în loc de un commit per cadru — istoric lizibil.
- [ ] `LICENSE`/`NOTICE` care clarifică: extrase pentru notițe personale, cu atribuire către fiecare video sursă — dacă repo-ul rămâne public.
- [ ] Reconsideră stratul de hosting: Notion API suportă upload de fișiere, ceea ce ar face repo-ul inutil; alternativ Cloudflare R2 / S3 + CloudFront elimină și expunerea publică, și fragilitatea raw GitHub.
- [ ] Dacă rămâne pe GitHub: repo privat + URL-uri semnate (sau accept explicit al riscului public, documentat).
- [ ] `.gitignore` minimal (fișiere OS, `*.tmp`).
