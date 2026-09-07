# telc-frontend — C1 Hörverstehen

Eine browserbasierte Übungs-App für den Prüfungsteil **TELC C1 Hörverstehen**. Gehört zusammen mit [telc-backend](https://github.com/Kutlu24/telc-backend), das die Prüfungsinhalte liefert und den Login übernimmt.

🇬🇧 English version: [README.md](README.md)

## Was die App macht

1. Anmeldung (gegen `telc-backend`).
2. Abrufen eines Prüfungstexts und der zugehörigen Fragen für einen gewählten *Teil* vom Backend.
3. Die im Browser eingebaute `SpeechSynthesisUtterance`-API liest den deutschen Text vor — so wird der Hörverstehens-Teil der Prüfung simuliert.
4. Zuordnungs-, Multiple-Choice- und Lückentext-Fragen zum Gehörten beantworten.

## Technik

Reines HTML und Vanilla-JavaScript — kein Framework, kein Build-Prozess. Nutzt die im Browser eingebaute Web-Speech-API (`SpeechSynthesisUtterance`) für die Sprachausgabe.

## Backend-Anbindung

Die App ruft derzeit eine fest im Code hinterlegte Backend-URL auf:

```
https://telc-backend-yjs9.onrender.com
```

`questions.json` und `texts.json` in diesem Repository sind lokale Beispieldaten — sie werden von der laufenden App **nicht** gelesen, stattdessen wird alles vom Live-Backend abgerufen. Beim Bearbeiten dieser Dateien also beachten, dass sich dadurch nichts sichtbar ändert.

## Bekannte Lücke

Dieses Frontend ruft `/exams` und `/questions` auf dem Backend auf, aber das aktuelle `telc-backend`-Repository implementiert nur `/register` und `/login`. Siehe die entsprechende Anmerkung im [telc-backend-README](https://github.com/Kutlu24/telc-backend#bekannte-l%C3%BCcke).
