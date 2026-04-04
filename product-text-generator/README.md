<img width="1466" height="627" alt="Screenshot 2026-04-04 172946" src="https://github.com/user-attachments/assets/3ca512e8-f75a-476d-bb5b-f42b645411a4" />

# 🛒 Produkttextgenerator – Lilyversell

Automatisierter Produkttextgenerator für den Lilyversell WooCommerce-Shop, gebaut mit n8n und Claude AI.

## 📋 Übersicht

Dieses System generiert vollständige Produkteinträge auf Basis weniger Eingaben – und legt sie automatisch als Entwurf in WooCommerce an. Was früher manuell geschrieben, formatiert und eingetragen werden musste, passiert jetzt per Formular in Sekunden.

Gebaut für Lilyversell – meinen eigenen Handmade-Shop – und direkt übertragbar auf jeden WooCommerce-basierten E-Commerce-Shop.

<img width="519" height="527" alt="Screenshot 2026-04-04 173304" src="https://github.com/user-attachments/assets/09e98bf4-1bf9-4865-8686-02ff2797bf0a" />


## 💼 Business Value

- **Stundenlange Arbeit auf Sekunden reduziert** – kein manuelles Schreiben von Produkttexten mehr
- **Skaliert mit dem Shop** – besonders wertvoll bei großen Produktkatalogen: der Workflow ist die Basis für eine spätere Batch-Verarbeitung, bei der eine Excel-Liste mit hunderten Produkten auf einmal verarbeitet werden kann
- **Konsistente Qualität** – alle Texte folgen demselben professionellen Standard
- **Direkt in WooCommerce** – Produkt landet als Entwurf mit allen relevanten Feldern
- **SEO-ready** – SEO-Titel, Meta-Description und Kurzbeschreibung werden automatisch generiert
- **Skalierbar** – ideal für Shops mit vielen Produkten oder häufigen Neuzugängen

## 🔄 Workflow

**Formular → Claude AI → Code Node → Google Sheets + WooCommerce (parallel)**

1. Formular ausfüllen mit Produktdaten (Motiv, Farbe, Material, Maße, Durchlass, Besonderheiten, Kategorie, Preis, Bestand)
2. Claude AI generiert automatisch alle Texte als strukturiertes JSON
3. Code Node parsed das JSON und ordnet die Kategorien zu
4. **Parallel:**
   - Google Sheets speichert alle Texte zur Dokumentation
   - Switch Node leitet an den richtigen WooCommerce Node weiter (je nach Kategorie)
5. WooCommerce legt das Produkt als Entwurf an – mit Name, Beschreibung, Kurzbeschreibung, SKU, Preis, Bestand, Kategorien und Yoast Meta-Description

## 📝 Generierte Inhalte

Pro Produkt werden automatisch erstellt:

- **SEO-Titel** – Windows-kompatibel, einheitliches Format
- **Artikelnummer / SKU** – einheitliches Schema
- **Langer Produkttext** – emotional, sachlich, mit HTML-Tabelle und GPSR-Pflichtangaben
- **Kurzbeschreibung** – max. 160 Zeichen
- **Meta-Description** – SEO-optimiert, max. 160 Zeichen

## 🛠️ Tech Stack

| Tool | Verwendung |
|------|-----------|
| n8n | Workflow-Automatisierung |
| Claude AI (Haiku) | Produkttextgenerierung |
| Google Sheets | Dokumentation aller generierten Texte |
| WooCommerce REST API | Automatische Produktanlage als Entwurf |
| Yoast SEO | Meta-Description via Post Meta |

## 💡 Erweiterungsmöglichkeiten

- Automatischer Bild-Upload via WooCommerce API
- Batch-Verarbeitung: Excel-Liste hochladen → alle Produkte auf einmal generieren
- Weitere Produktkategorien (aktuell: Anhänger, Verbinder, Perlen)
- Varianten-Produkte mit automatischer Variantengenerierung
