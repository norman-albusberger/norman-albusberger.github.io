# Migration auf al-folio – Dev- & Deploy-Anleitung

Dieses Portfolio wurde vom alten `ryancv`-Theme auf **al-folio** migriert.
Die Arbeit liegt auf dem Branch **`al-folio-migration`**; `main` blieb bis zum
Umschalten unverändert live.

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
aus dem Git-Index wieder her. Nach Änderungen an Dateien daher `git add -A`
gestaged halten, damit die richtige (al-folio-)`Gemfile.lock` verwendet wird.
Änderungen an `_config.yml` erfordern einen Container-Neustart. Bei hartnäckigem
Stale-State hilft `down` + `up` (frischer `_site`-Build).

## Inhalte pflegen

| Was              | Datei(en)                                  |
|------------------|--------------------------------------------|
| Startseite/Bio   | `_pages/about.md`                          |
| Leistungen       | `_pages/about.md` (Abschnitt „Leistungen") |
| Projekte         | `_projects/*.md`, Bilder in `assets/img/projects/` |
| Lebenslauf       | `_data/cv.yml` + CV-PDF in `assets/pdf/`   |
| Blog             | `_posts/*.md`                              |
| Navigation/Social| `_config.yml`, `_data/socials.yml`         |
| Profilfoto       | `assets/img/prof_pic.jpg`                  |

Deutsche CV-Überschriften/Labels und das „Neueste Beiträge"-Label kommen aus
lokalen Template-Overrides in `_includes/cv/` bzw. `_layouts/about.liquid`.

## Deployment (GitHub Pages)

`.github/workflows/deploy.yml` baut bei jedem Push auf `main` die Seite und
pusht das Ergebnis in den Branch **`gh-pages`**.

Schritte für den ersten Go-Live:
1. Branch `al-folio-migration` committen und nach `main` mergen (oder pushen).
2. Der Deploy-Workflow läuft automatisch und erzeugt den `gh-pages`-Branch.
3. In den Repo-Settings unter **Settings → Pages** die Quelle auf
   **„Deploy from a branch" → `gh-pages` / `(root)`** stellen.
4. Prüfen, ob das Git-Remote korrekt ist (aktuell `norman-albusgerger` –
   möglicher Tippfehler statt `norman-albusberger`).
