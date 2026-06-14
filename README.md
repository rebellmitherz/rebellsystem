# Rebellsystem · Akquise-Landingpage

Statische Landingpage für **akquise.rebellsystem.com** (B2B-Akquise als Service / DfY-Termine).

## Inhalt
- `index.html` — die komplette Seite (eine Datei, keine Build-Tools nötig)
- `CNAME` — Custom-Domain für GitHub Pages (`akquise.rebellsystem.com`)
- `.nojekyll` — GitHub Pages soll die Dateien unverändert ausliefern
- `impressum.html` / `datenschutz.html` — Pflichtseiten (DE), noch zu finalisieren

## Vor dem Live-Gang offen
- [ ] `CALENDLY_LINK` in `index.html` durch echten Kalender-Link ersetzen
- [ ] Telefonnummer im Footer prüfen
- [ ] Impressum + Datenschutz mit echten Daten füllen
- [ ] Proof-Block mit echtem Ergebnis/Referenz füllen
- [ ] (Empfohlen) Google-Fonts selbst hosten (DSGVO) — siehe unten

## Deploy via GitHub Pages
1. Neues GitHub-Repo anlegen (z. B. `rebellsystem-akquise`), diesen Ordner pushen.
2. Repo → Settings → Pages → Source: `main` / root → speichern.
3. GitHub liest die `CNAME`-Datei und setzt die Custom-Domain automatisch.
4. Bei IONOS DNS (für `rebellsystem.com`):
   - Typ **CNAME**, Host/Name: `akquise`, Ziel: `<dein-github-user>.github.io`
   - (oder A-Records auf die GitHub-Pages-IPs, falls CNAME am Root kollidiert)
5. In GitHub Pages „Enforce HTTPS" aktivieren, sobald das Zertifikat steht.

**Push = live.** Erst veröffentlichen, wenn die 4 Punkte oben erledigt sind.

## Alternative: Vercel / Netlify
Ordner per Drag-and-drop hochladen → Custom Domain `akquise.rebellsystem.com`
hinzufügen → bei IONOS den von Vercel/Netlify genannten DNS-Eintrag setzen.

## Hinweis Google Fonts (DSGVO)
`index.html` lädt aktuell „Inter" von Google Fonts (externer Request → in DE
abmahnungsrelevant). Empfehlung: Font lokal hosten (Dateien in den Ordner legen,
`@font-face` statt `<link>`). Kann auf Wunsch umgestellt werden.
