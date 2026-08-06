# ada_loom — site vitrine + book

Page vitrine de Laurent Marissal (studio ada_loom) avec le book PDF hébergé.

## Contenu

- `index.html` — la page vitrine (autonome, aucune dépendance à installer)
- `book-web.pdf` — le book, 21 planches, allégé pour le web (3,4 Mo)
- `cover.png` — image de couverture utilisée par la vitrine

## Mettre en ligne sur GitHub Pages (5 min)

### Option A — en ligne de commande (Claude Code / terminal)

```bash
# depuis le dossier qui contient index.html, book-web.pdf, cover.png
git init
git add .
git commit -m "site ada_loom + book"
git branch -M main
# crée d'abord un repo vide sur github.com (ex: nommé "book" ou "ada-loom")
git remote add origin https://github.com/TON-COMPTE/NOM-DU-REPO.git
git push -u origin main
```

Puis sur GitHub : **Settings → Pages → Source : Deploy from a branch → Branch : main / (root) → Save**.
Le site est en ligne ~1 min plus tard à :
`https://TON-COMPTE.github.io/NOM-DU-REPO/`

### Option B — sans terminal

1. Sur github.com : **New repository** (nom au choix, ex. `ada-loom`), coche « Public », crée-le.
2. **Add file → Upload files** : glisse `index.html`, `book-web.pdf`, `cover.png`. Commit.
3. **Settings → Pages → Source : main / (root) → Save**.
4. Adresse : `https://TON-COMPTE.github.io/ada-loom/`

## Astuce — URL propre à ton nom

Si tu nommes le repo **`TON-COMPTE.github.io`**, l'adresse devient directement
`https://TON-COMPTE.github.io/` (sans sous-dossier).

Pour un vrai domaine (ex. `adaloom.fr`) : achète-le, puis **Settings → Pages → Custom domain**.

## Faire évoluer vers un vrai site

C'est déjà un site. Pour ajouter des pages (ex. une page projet détaillée par
travail), il suffit de créer d'autres fichiers `.html` et de les lier depuis
`index.html`. Modifiable via Claude Code à tout moment.

## Régénérer le book allégé (si tu modifies le PDF source)

```bash
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.5 -dPDFSETTINGS=/ebook \
   -dColorImageResolution=150 -dGrayImageResolution=150 -dMonoImageResolution=300 \
   -dDownsampleColorImages=true -dDownsampleGrayImages=true \
   -dNOPAUSE -dQUIET -dBATCH \
   -sOutputFile=book-web.pdf book_graphiste_def.pdf
```
