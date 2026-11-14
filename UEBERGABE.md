# UEBERGABE — Experience Usambara Mountains Tours

Stand: 14.11.2026

## Was ist gebaut
Single-Page-Website (statisch: HTML + CSS + ~30 Zeilen JS), 5 Sektionen:
Hero (hero-cliff.jpg), About (Kibwana + St Eugene Lodge, Chameleon-Foto),
Tours (4 Karten: Rainforest Hikes, Multi-Day Treks, Wildlife Walks, Driving & Culture),
Galerie (alle 6 Fotos), Kontakt.

## Kontakt auf der Seite (direkt, kein wa.me)
- tel:+255653106997 (4x: Hero-Button, Nav-Pill, Kontakt, Footer)
- Tour-Karten zeigen "Contact" mit Link auf #contact statt der wiederholten Nummer
- mailto:kibwanangoda@gmail.com
- https://www.facebook.com/kibwana.ngogda
- Adresse: P.O. Box 268, Lushoto, Tanzania

## Font
Ludicrous + Ludicrous Stencil von Missy Meyer, selbst gehostet in assets/fonts/,
Lizenz-PDF liegt bei (Desktop-Lizenz, kommerzielle Nutzung laut Autor erlaubt).

## Bilder
Die 6 geschickten Fotos, optimiert (JPEG q82, progressive, max 2000px, lazy unterhalb Hero).
FB-Account-Bilder: nicht ladbar, FB meldet HTTP 400 ohne Login.

## Domain + Hosting
experience-usambara.com ist frei (RDAP-Check). Registrierung durch Jamie.
**Live-Demo (ausserhalb des LAN):** https://spitzelpit.github.io/experience-usambara-tours/
(GitHub Pages, kostenlos, deployt automatisch bei jedem Push auf main.)
Spaeter: eigene Domain als CNAME in den Pages-Settings, dann ist die Demo-URL obsolet.
Empfehlung fuer Produktiv: Cloudflare Pages oder Netlify, Git-Connect an dieses Repo.

## Lokale Vorschau
`python3 -m http.server 8099` im Repo-Root, dann http://127.0.0.1:8099/
(oder index.html direkt im Browser oeffnen, alle Pfade sind relativ).

## Verifikation (alles echter Tool-Output)
- HTTP 200: index, CSS, JS, 2 Fonts, 6 Bilder, Favicon
- Playwright Chromium: 0 Konsolen-Fehler; kein horizontaler Overflow (1440 + 390px)
- Fonts via document.fonts.check geladen; 12 Bilder mit Alt-Text, keine Broken Images
- 0 wa.me-Links; Screenshots in reports/
- Visueller Check per Screenshot-Analyse: Font rendert, keine Ueberlappungen, kein KI-Look

## Bewusst weggelassen (Kundenwunsch)
Google Business Profile, Blog, Preise (Touren = "on request").

## Vorfall
Fremde Hermes-Session (20260823_124310_23ce680d) schrieb 21:40 DESIGN.md in diesen
Workspace (Trigger: meine ntfy-Updates; Details + Log-Zeilen in PLAN.md).
DESIGN.md liegt UNTRACKED im Workspace, nicht im Repo. Keep/Delete: Jamie.

## Offene Punkte
- Domain registrieren + deployen
- DESIGN.md entscheiden
- Bei Bedarf: zweite Nummer, Preise, FB-Fotos nachreichen
