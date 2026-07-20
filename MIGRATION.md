# al-folio Portfolio – Dev- & Deploy-Anleitung

Dieses Portfolio läuft auf **al-folio** (v1.x). Es löste das alte
`ryancv`-Theme ab.

## Lokal entwickeln (Docker)

Das System-Ruby (2.6) ist zu alt – wir nutzen Docker. Das Image wird einmalig
aus dem mitgelieferten `Dockerfile` gebaut (passt exakt zur `Gemfile.lock`):

```bash
docker compose -f docker-compose.yml build      # einmalig (dauert ein paar Min.)
docker compose -f docker-compose.yml up -d       # Server starten
# -> http://localhost:8080/   (Livereload aktiv, Änderungen erscheinen automatisch)
docker compose -f docker-compose.yml down        # Server stoppen
```

**Wichtig:** `bin/entry_point.sh` stellt beim Start die getrackte `Gemfile.lock`
aus dem Git-Index wieder her. Nach Änderungen daher `git add -A` gestaged
halten. Änderungen an `_config.yml` erfordern einen Container-Neustart. Bei
hartnäckigem Stale-State hilft `down` + `up` (frischer `_site`-Build).

## Inhalte pflegen

| Was              | Datei(en)                                          |
|------------------|----------------------------------------------------|
| Startseite       | `_pages/about.md`                                  |
| Projekte         | `_projects/*.md`, Karten in `assets/img/projects/` |
| Lebenslauf       | `_data/cv.yml` + CV-PDF in `assets/pdf/`           |
| Blog             | `_posts/*.md`                                      |
| Navigation/Social| `_config.yml`, `_data/socials.yml`                 |
| Profilfoto       | `assets/img/prof_pic.jpg`                          |
| Rechtstexte      | `_pages/impressum.md`, `_pages/datenschutz.md`     |

Deutsche CV-Überschriften, das „Neueste Beiträge“-Label und der Dark-Mode-
Standard kommen aus lokalen Template-Overrides in `_includes/` bzw.
`_layouts/`. Diese sind in `.al-folio-overrides.yml` dokumentiert; nach
Änderungen an ihnen `bundle exec al-folio upgrade overrides audit` ausführen.

## Datenschutz: keine Fremd-Server

Die Seite lädt **keine Ressourcen von Dritt-Servern**. Das ist eine Zusage in
der Datenschutzerklärung und muss so bleiben:

- `third_party_libraries.download: true` lädt Bibliotheken beim Build herunter
  und liefert sie aus `assets/libs/` aus (gitignored, entsteht beim Build).
  Die Google-Fonts-CSS wird dabei auf lokale `woff2`-Dateien umgeschrieben.
- **FontAwesome liegt fest im Repo** unter `assets/fontawesome/` (CSS +
  Webfonts). Grund: Der Download-Mechanismus lädt nur das CSS, nicht die darin
  referenzierten Webfonts – die Icons blieben sonst leer.
- Deaktiviert, weil nicht lokalisierbar bzw. unnötig: `enable_medium_zoom`,
  Altmetric-/Dimensions-Badges, Academicons, Scholar-Icons.

**Vor jedem Go-Live prüfen:**

```bash
docker compose -f docker-compose.yml exec -T jekyll bash -c \
  'cd /srv/jekyll && JEKYLL_ENV=production bundle exec jekyll build --destination /tmp/_p >/dev/null 2>&1
   cd /tmp/_p && grep -rhoE "<(script|link|img|iframe)[^>]*(src|href)=\"https?://[^\"]+\"" --include=*.html . \
   | grep -oE "https?://[^\"]+" | grep -viE "norman-albusberger" | sort -u'
```

Die Ausgabe muss **leer** sein.

## Deployment

`.github/workflows/deploy.yml` baut bei jedem Push auf `main` und
veröffentlicht das Ergebnis im Branch **`gh-pages`**. GitHub Pages liefert von
dort aus (Quelle: `gh-pages` / root).

Normaler Ablauf: Änderung committen, nach `main` pushen, fertig. Der Workflow
erledigt den Rest; der Fortschritt ist unter „Actions“ sichtbar.

Falls die Seite je manuell veröffentlicht werden muss (z. B. bei defektem
Workflow): lokal mit `JEKYLL_ENV=production` bauen und den Inhalt von `_site`
als `gh-pages` pushen – inklusive `.nojekyll`, damit GitHub das Ergebnis nicht
noch einmal durch Jekyll schickt.
