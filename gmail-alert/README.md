<img width="1202" height="444" alt="Screenshot 2026-04-03 132402" src="https://github.com/user-attachments/assets/faa223e5-3739-4556-912c-7dfa3f2330e3" />

# Gmail Alert – Dringende Mails per Telegram
Dieser Workflow überwacht Gmail und schickt eine Telegram-Benachrichtigung wenn eine dringende Mail von bestimmten Absendern eingeht.

## Was er macht

1. **Gmail Trigger** – prüft jede Minute auf neue Mails
2. **Filter 1** – lässt nur Mails von definierten Absendern durch
3. **Filter 2** – prüft ob "eil" im Betreff steht (trifft "eilt", "eilig", "Eile" etc.)
4. **Telegram** – schickt eine Benachrichtigung mit Betreff der Mail

<img width="354" height="102" alt="Screenshot 2026-04-03 203156" src="https://github.com/user-attachments/assets/a36e8e3f-9322-4227-b952-28d130b5684b" />


## Anwendungsfall

Wichtige Mails von Vorgesetzten oder Kollegen gehen im Postfach unter. Dieser Workflow stellt sicher dass dringende Mails sofort als Telegram-Nachricht auf dem Handy ankommen – unabhängig davon ob du gerade im Postfach bist.


## Learnings

- Gmail OAuth2 Einrichtung via Google Cloud Console
- Verkettung von Filter-Nodes für AND-Logik
- "contains" statt "is equal to" für flexible E-Mail-Matching
