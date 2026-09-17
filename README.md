# notion-assets

Repo-depozit de imagini pentru rezumatele de tutoriale din Notion. **Nu conține cod** — doar JPEG-uri și acest README. Este infrastructura skill-ului `tutorial-report`: skill-ul descarcă un video YouTube, extrage cadrele-cheie (diagrame, scheme, mindmap-uri), le comite aici și le încorporează în pagina Notion prin URL-uri raw GitHub, pentru că Notion nu poate primi imagini direct din pipeline-ul local.

## Atenție: repo PUBLIC

Este singurul repo public din `catabanciu08/*`. Orice cadru comis aici e vizibil oricui, permanent (git păstrează blob-urile și după ștergere). Cadrele sunt extrase din videoclipuri terțe, fără atribuire și fără fișier de licență — nu pune aici nimic ce nu vrei public.

## Schema URL (pe care paginile Notion depind)

```
https://raw.githubusercontent.com/catabanciu08/notion-assets/main/tutorial-report/<videoId>/<frame>.jpg
```

Redenumirea repo-ului, a branch-ului `main` sau trecerea la privat rupe retroactiv toate imaginile din toate paginile Notion.

## Convenția de foldere

- `tutorial-report/<videoId>/` — un folder per video, numit cu ID-ul YouTube de 11 caractere (ex. `cKVmHAI_XY0`).
- `<frame>.jpg` — numărul cadrului extras cu ffmpeg, zero-padded la 5 cifre (ex. `00129.jpg`, `01633.jpg`).
- Stare la 2026-09-17: 43 de foldere, 287 de cadre (1–11 per video), ~3.6 MB pe disc, ~6.9 MB în `.git`.

## Ce lipsește (deocamdată)

- **Nicio politică de retenție**: repo-ul crește nelimitat, ~7 cadre per rulare, și nimic nu se șterge.
- **Niciun manifest**: nu există maparea `videoId → pagină Notion / titlu / dată`, deci un folder orfan (pagină ștearsă) nu se poate deosebi de unul viu — nimic nu poate fi șters în siguranță.
- Commit-urile sunt fragmentate și au mesaje identice („Add tutorial-report frames").

Ideile de remediere (manifest, webp, cap de cadre, hosting alternativ) sunt în [docs/ROADMAP.md](docs/ROADMAP.md); riscurile în [docs/AUDIT-2026-09-17.md](docs/AUDIT-2026-09-17.md).
