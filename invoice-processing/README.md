<img width="1721" height="501" alt="Screenshot 2026-04-09 215904" src="https://github.com/user-attachments/assets/41f9e1a2-dba0-47b9-9342-fb4461da5f50" />

# 🧾 Rechnungsverarbeitung – Outlook & Google Drive

Automatisierte Extraktion von Rechnungsdaten aus Outlook-Mails per KI – strukturiert aufbereitet und direkt in Google Drive gespeichert.

## 📋 Übersicht

Dieser Workflow liest automatisch Rechnungs-E-Mails aus Outlook, extrahiert per Claude AI die relevanten Daten (Betrag & Produktart) und speichert das Ergebnis als strukturierte Datei in Google Drive – ohne manuelles Öffnen oder Abtippen.

## 💼 Business Value

- **Kein manuelles Durchsuchen** von Rechnungsmails – der Workflow erledigt das vollständig
- **Automatische Dateiablage** direkt in Google Drive, sortiert und strukturiert
- **KI-gestützte Extraktion** erkennt Beträge und Produktarten zuverlässig aus Freitextmails
- **Skalierbar** – funktioniert für beliebig viele Mails pro Durchlauf

## 🔄 Workflow

**Manueller Trigger → Outlook → Filter → Google Drive Upload + KI-Extraktion → Tabelle → Google Drive Export**

- Manuell gestartet über den „Execute Workflow"-Button in n8n
- Alle E-Mails aus dem Outlook-Postfach werden abgerufen (646 Items im Test)
- Ein Filter selektiert nur relevante Rechnungsmails (~2 % der Gesamtmenge, 14 Items)
- Anhänge werden direkt in Google Drive hochgeladen
- JavaScript bereitet die E-Mail-Daten für die KI-Übergabe auf
- Claude AI extrahiert aus dem E-Mail-Text Betrag und Produktart
- Die Ergebnisse werden in eine strukturierte Tabelle überführt
- Eine finale Datei wird automatisch in Google Drive gespeichert

## 🛠️ Tech Stack

| Tool | Verwendung |
|------|-----------|
| n8n | Workflow-Automatisierung |
| Microsoft Outlook | E-Mail-Quelle (via Microsoft 365 API) |
| Claude AI | Extraktion von Betrag & Produktart |
| Google Drive | Ablage von Anhängen & Ergebnisdatei |
| JavaScript | Datentransformation & Aufbereitung |

## 💡 Erweiterungsmöglichkeiten

- Automatischer Trigger per Schedule (z.B. täglich) statt manuell
- Kategorisierung nach Lieferant oder Kostenstelle
- Weiterleitung der Tabelle direkt an ein Buchhaltungstool (z.B. DATEV, Lexoffice)
- E-Mail-Benachrichtigung nach Abschluss mit Zusammenfassung
