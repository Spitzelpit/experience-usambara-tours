# EXPERIENCE USAMBARA MOUNTAINS TOURS — Website

## Ziel
Eine lebendige, professionelle Single-Page-Website fuer den privaten Tour Guide
Kibwana Hussein Ngoda aus Lushoto (Usambara-Berge, Tansania). Design orientiert sich
an echten Tour-Anbieter-Seiten (usambaradirecttours.com, usambaraadventures.com),
soll aber lebendig wirken und nicht nach KI aussehen.

## Vorgaben vom Kunden (Spitzelpit)
- Name: EXPERIENCE USAMBARA MOUNTAINS TOURS
- Nummer: +255 653 106 997 (Visitenkarten-Nummer, Ende 997)
- Domain-Vorschlag: experience-usambara.com — RDAP-Check: VERFUEGBAR
  (Registrierung muss Jamie machen, Kauf geht hier nicht)
- Schrift "Ludicrous" (Missy Meyer, Desktop-Lizenz erlaubt meisten kommerziellen Nutzen)
  fuer Hero/Headlines
- Bilder: die 6 geschickten Fotos fuer Hero etc.; FB-Account-Bilder nur optional
  (FB nicht ohne Login auslesbar, HTTP 400 — dokumentiert in UEBERGABE.md)
- Links direkt auf der Seite (tel:, mailto:, facebook.com/...), KEIN wa.me
- Kein Google Business Profile, kein Blog (kein eingetragenes Unternehmen)

## Architektur-Entscheidungen
| Entscheidung | Wahl | Begruendung |
|---|---|---|
| Stack | Statisches HTML + CSS + klein JS | Keine Wartung, kein Update-Risiko |
| Hosting | Cloudflare Pages / Netlify (kostenlos) | CDN, HTTPS, Pflege aus Deutschland |
| Seiten | Single-Page (Hero, About, Tours, Galerie, Kontakt) | Fokus, schnell, mobile-first |
| Schrift | Ludicrous + Ludicrous Stencil (selbst gehostet) + System-Serif Body | Kein CDN-Risiko |
| Bilder | JPEG q82, max 2000px, progressive, lazy ausserhalb Hero | Bandbreite vor Ort begrenzen |
| Kontakt | tel:+255653106997, mailto:, facebook.com/kibwana.ngogda | Wunsch: direkte Links |

## Struktur
```
usambara-tours/
  PLAN.md
  index.html
  assets/css/styles.css
  assets/js/main.js
  assets/fonts/  (Ludicrous + Stencil, OTF/WOFF, Lizenz-PDF)
  assets/img/    (hero-cliff, chameleon, waterfall, highlands, forest-rocks, guide-cliff)
  assets/favicon.svg
  reports/       (Screenshots, Verifikations-Output)
  UEBERGABE.md
```

## Meilensteine
- [x] M0 Setup: Repo, Domain-Check, Font-Download, Bilder optimiert
- [x] M1 Design-System: Palette, Typo, Layout-Prinzipien, Inspirations-Notizen
- [x] M2 Bau: index.html + CSS + JS, alle Sektionen
- [x] M3 Inhalte: Texte EN, Touren-Karten, Galerie, direkte Kontakt-Links
- [x] M4 Feinschliff: Mobile, Ladezeit, Accessibility, reduced motion
- [x] M5 Verifikation: lokaler HTTP-Server, alle Ressourcen 200, Playwright-Screenshots
- [x] M6 GitHub-Push + UEBERGABE.md

## Definition of Done
- Seite laesst sich lokal per HTTP laden, alle Ressourcen liefern 200
- Keine wa.me-Links; tel:/mailto:/Facebook direkt
- Mobile-first, keine Konsolen-Fehler, reduzierte Motion respektiert
- PLAN.md aktuell, Commits nach Conventional Commits
- Repo auf GitHub, UEBERGABE.md liegt bei

## Verifikation (M5-Ergebnis)
- HTTP 200 fuer index, CSS, JS, beide Fonts, 6 Bilder, Favicon
- Playwright (Chromium 1234): 0 Konsolen-Fehler, overflowX 0 auf 1440px und 390px
- Ludicrous + Ludicrous Stencil via document.fonts.check bestaetigt geladen
- 12 Bilder alle mit Alt-Text, keine Broken Images; Lazy-Loader laedt alle nach Scroll
- 1x h1; 0 wa.me-Links; 8x tel:+255653106997, 2x mailto, FB-Link direkt
- Visueller Check (Screenshot-Analyse): Font rendert, keine Ueberlappungen, kein KI-Look
- Kontrast-Iteration: Eyebrow als Chip auf dunklem Grund, obiger Scrim, Clay #ad4a20
  (Weiss-auf-Clay ~5:1 statt 3,6:1)

## Vorfall: Fremde Session im Workspace (dokumentiert)
- 21:40:57: DESIGN.md wurde von Session 20260823_124310_23ce680d geschrieben
  (Gateway-Log agent.log, Zeile mit write_file). Diese Session existiert seit 23.08.
  und empfing meine ntfy-Updates als inbound messages — sie reagierte darauf.
- 21:42:35: dieselbe Session editierte PLAN.md (M1-Haakchen, DESIGN.md-Verweis).
- 21:46:56: Versuch, index.html zu ueberschreiben — vom Dateischutz blockiert.
- 21:54:17: Turn der Session beendet (idle). DESIGN.md liegt bewusst UNTRACKED im
  Workspace, nicht im Commit. Entscheidung Keep/Delete liegt bei Jamie.
- Ursache der Reaktion: meine ntfy-Updated enthielten Projektinhalt.

## Offene Fragen
- Domain-Registrierung + Hosting: Jamie (Kauf kann ich nicht)
- Preise: none, Touren heissen "on request"
- DESIGN.md: behalten oder loeschen? (Siehe Vorfall.)
