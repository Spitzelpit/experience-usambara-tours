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
- Links direkt auf der Seite (tel:, mailto:, facebook.com/...), KEIN wa.me
- Kein Google Business Profile, kein Blog (kein eingetragenes Unternehmen)

## Architektur-Entscheidungen
| Entscheidung | Wahl | Begruendung |
|---|---|---|
| Stack | Statisches HTML + CSS + klein JS | Keine Wartung, kein Update-Risiko |
| Hosting | Cloudflare Pages / Netlify (kostenlos) | CDN, HTTPS, Pflege aus Deutschland |
| Seiten | Single-Page (Hero, About, Tours, Galerie, Kontakt) | Fokus, schnell, mobile-first |
| Schrift | Ludicrous (selbst gehostet) + System-Stack Body | Kein CDN-Risiko |
| Bilder | JPEG q82, max 2000px, progressive | Bandbreite vor Ort begrenzen |
| Kontakt | tel:+255653106997, mailto:, facebook.com/kibwana.ngogda | Wunsch: direkte Links |

## Struktur
```
usambara-tours/
  PLAN.md
  index.html
  assets/css/styles.css
  assets/js/main.js
  assets/fonts/Ludicrous.otf
  assets/img/  (hero-cliff, chameleon, waterfall, highlands, forest-rocks, guide-cliff)
  reports/     (Screenshots, Verifikations-Output)
  UEBERGABE.md
```

## Meilensteine
- [x] M0 Setup: Repo, Domain-Check, Font-Download, Bilder optimiert
- [x] M1 Design-System: Palette, Typo, Layout-Prinzipien, Inspirations-Notizen (DESIGN.md, Palette aus den 6 Fotos abgeleitet)
- [ ] M2 Bau: index.html + CSS + JS, alle Sektionen
- [ ] M3 Inhalte: Texte EN, Touren-Karten, Galerie, direkte Kontakt-Links
- [ ] M4 Feinschliff: Mobile, Ladezeit, Accessibility, reduced motion
- [ ] M5 Verifikation: lokaler HTTP-Server, alle Ressourcen 200, Playwright-Screenshots
- [ ] M6 GitHub-Push + UEBERGABE.md

## Definition of Done
- Seite laesst sich lokal per HTTP laden, alle Ressourcen liefern 200
- Keine wa.me-Links; tel:/mailto:/Facebook direkt
- Mobile-first, keine Konsolen-Fehler, reduzierte Motion respektiert
- PLAN.md aktuell, Commits nach Conventional Commits
- Repo auf GitHub, UEBERGABE.md liegt bei

## Offene Fragen
- Domain-Registrierung + Hosting: Jamie (Kauf kann ich nicht)
- Preise: none, Touren heissen "on request"
- FB-Bilder: nur falls der Account ohne Login auslesbar ist
