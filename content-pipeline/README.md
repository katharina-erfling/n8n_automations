<img width="798" height="788" alt="Screenshot 2026-04-05 005433" src="https://github.com/user-attachments/assets/28f3acd0-9276-4564-a7ec-7846632061f3" />

# Content Pipeline

> 🚧 Dieser Workflow befindet sich aktuell in der Entwicklung.

Eine vollautomatische Content-Pipeline die Daten aus Google Search Console, Google Analytics, Google Keyword Planner und Google Trends auswertet, daraus SEO-optimierte Blogartikel erstellt und diese automatisch für Instagram und Pinterest aufbereitet.

---

## Ziel

Statt manuell zu recherchieren, welche Themen fehlen oder welche Inhalte ein Update brauchen, übernimmt dieser Workflow die gesamte Vorarbeit – und liefert am Ende fertige Entwürfe für Blog, Instagram und Pinterest.

---

## Pipeline-Übersicht

```
Search Console + GA + Keyword Planner + Trends RSS
        ↓
  Claude: Lücken-Analyse & Themenvorschläge (Sheets)
        ↓
  [Manuelle Auswahl]
        ↓
WP-Abgleich (interne Links + Produkte)  →  Claude: Text schreiben  →  WP-Entwurf
        ↓
  [Manuelle Abnahme]
        ↓
Claude: Instagram-Caption  +  Claude: Pinterest-Pin  →  Planung / Veröffentlichung
```

---

## Workflow-Phasen

### Phase 1 – Datenanalyse & Themenrecherche
- **Google Search Console API**: Keywords mit vielen Impressions, aber niedrigem CTR
- **Google Analytics**: Traffic-Muster und erfolgreiche Inhalte
- **Google Keyword Planner API**: Suchvolumen, Keyword-Ideen, Wettbewerb, saisonale Schwankungen
- **Google Trends RSS**: Was ist gerade diese Woche trending
- Claude analysiert alle Quellen zusammen und leitet Themenvorschläge ab

> Keyword Planner = langfristiges Suchvolumen & Keyword-Ideen  
> Google Trends RSS = kurzfristige Peaks & aktuelle Relevanz

### Phase 2 – Themenplanung & Abgleich
- Claude generiert konkrete Themenvorschläge mit SEO-Fokus
- Automatischer Abgleich mit bestehenden WordPress-Beiträgen (neu / update / bereits vorhanden)
- Ergebnisse landen in Google Sheets zur manuellen Auswahl

### Phase 3 – Content-Erstellung
- Nach Auswahl eines Themas: WordPress wird nach passenden internen Links und Produkten durchsucht
- Claude schreibt den vollständigen Beitrag inkl. SEO-Keywords, internen Links und Produktempfehlungen
- Beitrag wird automatisch als Entwurf in WordPress eingestellt
- Optionale Bildauswahl aus einer getaggten Bildbibliothek (Google Drive)

### Phase 4 – Social Media Aufbereitung
- Instagram: Caption, Hashtags, passendes Bild aus Bibliothek
- Pinterest: Pin-Titel, Beschreibung, plattformspezifische Keywords
- Analyse der besten Posting-Zeiten je Plattform
- Entwürfe oder automatisch geplante Veröffentlichung

---

## Tools

| Tool | Einsatz | Kosten |
| --- | --- | --- |
| n8n | Workflow-Orchestrierung | kostenlos (self-hosted) |
| Claude AI (Anthropic) | Analyse, Texterstellung, Social-Media-Aufbereitung | API-Kosten |
| Google Search Console API | SEO-Daten, Keyword-Performance | kostenlos |
| Google Analytics | Traffic- und Verhaltensdaten | kostenlos |
| Google Keyword Planner API | Suchvolumen, Keyword-Ideen, Wettbewerb | kostenlos (Google Ads Konto nötig) |
| Google Trends RSS | Tagesaktuelle Trending Topics | kostenlos |
| Google Sheets | Themenauswahl-Interface, Beitrags- und Produktlisten | kostenlos |
| WordPress REST API | Beitrags-Abgleich, Entwurf erstellen | kostenlos |
| Google Drive | Bildbibliothek mit Tags | kostenlos |
| Instagram / Pinterest API | Social-Media-Entwürfe und Planung | kostenlos |

---

## Besonderheiten

- **Manueller Checkpoint 1**: Themenauswahl bleibt bei mir – Claude schlägt vor, ich entscheide
- **Manueller Checkpoint 2**: Abnahme des fertigen Textes vor Veröffentlichung
- **Bildbibliothek**: Getaggtes Archiv in Google Drive, aus dem passende Bilder automatisch vorgeschlagen werden
- **Modular aufgebaut**: Jede Phase ist ein eigenständiger n8n-Workflow – wartbar und erweiterbar
- **Komplett kostenlos** (bis auf Claude API-Kosten): kein bezahlter Drittanbieter nötig

---

## Status

- [x] Konzept & Pipeline-Planung
- [ ] Workflow 1: Analyse & Themenvorschläge (Search Console + GA + Keyword Planner + Trends + Claude)
- [ ] Workflow 2: Content-Erstellung (WP-Abgleich + Claude + WordPress Draft)
- [ ] Workflow 3: Social Media Aufbereitung (Instagram + Pinterest)
- [ ] Bildbibliothek-Integration
