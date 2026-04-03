<img width="1429" height="555" alt="Screenshot 2026-04-04 004752" src="https://github.com/user-attachments/assets/7577429b-1ea1-45ca-9475-f8f46ad3ac1c" />

# 🔍 Brand Monitoring – Lilyversell

Automatisiertes Brand Monitoring System für Lilyversell, gebaut mit n8n, Claude AI und Google Looker Studio.

Lilyversell ist mein eigenes Unternehmen – dieses System habe ich produktiv für mich selbst entwickelt und eingesetzt, nicht nur als Demo.

## 📋 Übersicht

Dieses System überwacht automatisch Erwähnungen der Marke Lilyversell im Web, analysiert das Sentiment per KI und liefert wöchentliche Reports – vollständig automatisiert, ohne manuellen Aufwand.

## 💼 Business Value

- **Kein manuelles Monitoring mehr** – das System läuft 24/7 im Hintergrund
- **Sofortige Reaktion** bei negativen Erwähnungen via Telegram-Alert
- **Wöchentliche KPI-Reports** automatisch per Mail, ohne manuellen Aufwand
- **Datenbasierte Entscheidungen** durch strukturierte Sentiment-Auswertung
- **Skalierbar** – das System lässt sich auf mehrere Marken oder Produkte erweitern

## 🔄 Workflows

### Workflow 2a – Brand Monitoring (Echtzeit)
**RSS Feed Trigger → Claude Sentiment-Analyse → Google Sheets → Telegram Alert**

- Google Alerts RSS Feed überwacht kontinuierlich neue Erwähnungen von "Lilyversell"
- Polling Interval: stündlich
- Claude AI (Haiku) analysiert das Sentiment jeder Erwähnung (positiv / neutral / negativ)
- Haiku wurde gewählt weil es für kurze Klassifizierungsaufgaben ideal ist – schnell, günstig und präzise
- Ergebnis wird automatisch in Google Sheets gespeichert (Datum, Titel, Link, Quelle, Sentiment)
- Bei negativem Sentiment wird sofort eine Telegram-Benachrichtigung mit Titel und Link ausgelöst


<img width="1486" height="469" alt="Screenshot 2026-04-04 004057" src="https://github.com/user-attachments/assets/472e07e7-473d-461e-bff1-a0e0accc5d9e" />

### Workflow 2b – Weekly Summary (Wöchentlich)
**Schedule Trigger (montags 9 Uhr) → Google Sheets → Aggregate → Claude → Gmail**

- Jeden Montag um 9 Uhr startet der Workflow automatisch
- Alle Einträge der letzten 7 Tage werden aus Google Sheets geladen und aggregiert
- Claude AI (Haiku) erstellt eine strukturierte HTML-Zusammenfassung mit:
  - Gesamterwähnungen
  - Aufschlüsselung nach Sentiment (positiv / neutral / negativ)
  - Fazit und konkreter Handlungsempfehlung
- Der Report wird automatisch als formatierte HTML-Mail per Gmail verschickt



<img width="883" height="661" alt="Screenshot 2026-04-04 004945" src="https://github.com/user-attachments/assets/1f7dea31-4c8a-476e-8b61-b1d0bf81825c" />

## 📊 Dashboard

Die gesammelten Daten werden live in einem Google Looker Studio Dashboard visualisiert. Das Dashboard aktualisiert sich automatisch sobald n8n neue Daten ins Google Sheet schreibt – kein manueller Export nötig.

**Enthält:**
- Kreisdiagramm: Sentiment-Verteilung (positiv / neutral / negativ)
- Zeitreihe: Sentiment-Verlauf über Zeit
- Tabelle: Alle Erwähnungen mit Datum, Titel und Sentiment, sortiert nach Datum
- KPI-Übersicht: Gesamterwähnungen und Aufschlüsselung nach Sentiment

## 🛠️ Tech Stack

| Tool | Verwendung |
|------|-----------|
| n8n | Workflow-Automatisierung |
| Claude AI (Haiku) | Sentiment-Analyse & Report-Generierung |
| Google Alerts | Brand Monitoring via RSS Feed |
| Google Sheets | Datenspeicherung & Datenbasis |
| Google Looker Studio | Live-Dashboard & Visualisierung |
| Telegram | Echtzeit-Alerts bei negativem Sentiment |
| Gmail | Wöchentlicher HTML-Report |

## 💡 Erweiterungsmöglichkeiten

- Direktes Bewertungsmonitoring via Trustpilot wäre über die kostenpflichtige Trustpilot Business API möglich
- Mehrere Marken gleichzeitig überwachen
- Sentiment-Trend-Analyse über längere Zeiträume
- Monatliche Zusammenfassung zusätzlich zur wöchentlichen
- Automatische Antwort-Vorschläge bei negativen Erwähnungen per KI
