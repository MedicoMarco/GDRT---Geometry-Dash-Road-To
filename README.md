# GDRT — Geometry Dash Road To

Die Website liegt vollständig in `dist/index.html` und funktioniert auch als lokal gespeicherte HTML-Datei. Der Katalog ist fest eingebettet; Besucher müssen keine Leveldaten importieren.

## Daten

- 11.465 eindeutige Geometry-Dash-Level, zusammengeführt über ihre Level-ID.
- GDDL: `gddl (2).json` und `gddl (3).json`; bei Überschneidungen wird Version 3 verwendet.
- Demonlist: 1.844 Datensätze aus `demonlist.json`.
- GDDP: 1.054 Datensätze aus `main-list.json`, davon 385 mit Skill-XP und 542 mit gültiger Startpos-ID.
- GDDP-XP bleiben unverändert 0, 1, 2 oder 3. Skillsets ohne XP sind ausschließlich Tags. Es werden keine Werte geschätzt.
- `dist/catalog.json` ist derselbe zusammengeführte Katalog in maschinenlesbarer Form. Die Anwendung legt automatisch eine Kopie in IndexedDB an.

## Progression und Training

Jeder erstmalige Levelabschluss vergibt die dokumentierten Skill-XP einmal. Der Aufstieg von Skilllevel n kostet 5 × n XP. Entfernen und erneutes Eintragen eines Abschlusses erzeugt keine weiteren XP. Road und Quests berücksichtigen die daraus entstehenden Skilllevel. Der Vergleichsgraph zeigt gesammelte XP, keine geschätzte Fähigkeit.

Quests schalten sich ab einem eingetragenen Hardest mit GDDL-Tier 10 frei. Daily-Tier = floor(Hardest-Tier / 10), Weekly-Tier = floor(Hardest-Tier / 5). Bei fehlenden Kandidaten wird niemals ein schwierigeres Level eingesetzt. Zusatzbedingungen erscheinen zufällig bei einem Teil der Quests.

Learning: Ziele maximal 25 %, standardmäßig 20 %-Abschnitte. Consistency: zehn Ziele über 40–100 %, jeweils fünf bis sechs Erfolge. Startpos-Kopien sind direkt im Trainer und über Quests verfügbar, sofern die Quelle eine gültige ID enthält.

## Speicherung

Profile und Trainingsfortschritte bleiben im Browser des Besuchers. Die Einstellungen enthalten Profil-Export, Import und Backup. Es gibt keine geräteübergreifende Synchronisierung. Der integrierte Levelkatalog ist für alle Besucher identisch.

## Prüfumfang

Funktionstests: native XP, ungültige XP, doppelte Abschlüsse, Levelschwellen, Profil-Backup, Trainingslängen, Questformeln und Freischaltung. Integrationstests mit den echten Quelldaten: eindeutige IDs, Original-XP und Startpos, Quest-Grenzen, Road-Generierung und Ansichten. Browserprüfung: Levelsuche, Road, Trainer mit Startpos, Quest-Sperre, Profilgraph sowie Layout bei 390 px Breite.
