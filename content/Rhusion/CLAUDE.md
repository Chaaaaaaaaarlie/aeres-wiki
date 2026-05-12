# Aeres — D&D-Kampagnen-Wiki

Modus: Kampagne (Mode-F-Variante — Figuren, Lore, Sessions, Fäden)
Zweck: Dauerhafter Wissensspeicher für die Aeres-D&D-Kampagne — NSCs, Orte, Fraktionen, Lore, Session-Recaps und laufende Handlungsfäden.
Inhaber: Peter Konietzka
Erstellt: 2026-05-12
Sprache: Deutsch (alle Inhalte und Antworten in Deutsch verfassen).

## Struktur

```
vault/
├── .raw/                   # unveränderliche Quelldokumente (read-only)
│   ├── transcripts/        # Session-Audio-Transkripte
│   ├── screenshots/        # Spiel-Screenshots, Handouts
│   ├── maps/               # Kartenbilder
│   └── assets/             # sonstiges Rohmaterial
│
├── wiki/                   # die Wissensbasis
│   ├── index.md            # Hauptübersicht
│   ├── log.md              # chronologisches Vorgangs-Protokoll (neuestes oben)
│   ├── hot.md              # ~500-Wort-Cache des aktuellen Kontexts
│   ├── overview.md         # Kampagnen-Zusammenfassung
│   ├── figuren/            # NSCs und SCs (entity_type: person)
│   ├── orte/               # Orte (entity_type: place)
│   ├── fraktionen/         # Häuser, Kabalen, politische Körper
│   ├── kreaturen/          # Bestiarium
│   ├── gottheiten/         # Götter
│   ├── lore/               # Welt-Hintergrund, Geschichte, Religion
│   ├── fäden/              # offene Handlungsfäden, Hinweise, Rätsel
│   ├── sessions/           # Session-Recaps
│   ├── quellen/            # Zusammenfassungen von Quellmaterial
│   ├── konzepte/           # abstrakte Ideen, Rituale, Mechaniken
│   ├── vergleiche/         # Gegenüberstellungen
│   ├── fragen/             # abgelegte Antworten auf Fragen
│   └── meta/               # Dashboards, Lint-Berichte
│
├── _templates/             # Templater-Vorlagen je Notiztyp
├── _attachments/           # Bilder und PDFs, auf die Wiki-Seiten verweisen
│
├── WIKI.md                 # Referenz: das Wiki-Schema (Englisch, nicht ändern)
├── Willkommen.md           # Landing-Seite (spielerseitige Kampagnenübersicht)
└── .obsidian/              # Obsidian-Konfiguration (auto-verwaltet)
```

## Konventionen

- **Sprache:** Alle Wiki-Inhalte auf Deutsch. Antworten an den Nutzer auf Deutsch. Englisch nur in `WIKI.md` (Schema-Referenz) und in technischen Bezeichnern (Frontmatter-Keys wie `type`, `title`, `created`).
- Alle Notizen verwenden YAML-Frontmatter: `type`, `title`, `created`, `updated`, `tags`, `status` (Minimum).
- Wikilinks nutzen das Format `[[Seitenname]]` — Dateinamen sind vault-weit eindeutig, keine Pfade nötig.
- Ausnahme für Ordner-Übersichten (`_index.md`): pfadbasierter Wikilink mit Alias, z. B. `[[figuren/_index|Figuren-Übersicht]]`.
- `.raw/` enthält Quelldokumente — niemals verändern.
- `wiki/index.md` ist die Hauptübersicht — bei jedem Ingest aktualisieren.
- `wiki/log.md` ist append-only — neue Einträge **oben**, frühere niemals editieren.
- `Willkommen.md` ist die spielerseitige Landing-Seite. `wiki/index.md` ist die LLM-seitige Übersicht.
- Sessions werden benannt als `Session N — Titel` oder `Session N - TT.MM.JJJJ`. Bestehende Namen beibehalten.

## Vorgänge

- **Ingest**: Quelle in `.raw/` ablegen, dann „ingest [Dateiname]". Claude liest die Datei, legt eine Zusammenfassung in `wiki/quellen/` an, aktualisiert betroffene Entitäten/Fäden und ergänzt `log.md` + `hot.md`.
- **Session-Recap**: Notizen oder Transkript in `.raw/transcripts/` ablegen, dann „recap Session N". Claude schreibt den Recap in `wiki/sessions/`, aktualisiert berührte Figuren/Orte/Fäden und passt die Listen „Letzte Sessions" und „Aktuelle Fäden" in `Willkommen.md` an.
- **Frage**: beliebige Frage stellen — Claude liest `hot.md`, dann `index.md` und vertieft in 3–5 relevante Seiten.
- **Lint**: „lint the wiki" sagen, um eine Gesundheitsprüfung durchzuführen (Waisen, tote Links, Frontmatter-Lücken).

## Hinweise für Claude

- Sessions sind die primäre Wahrheits-Quelle für das, was in der Kampagne passiert ist. Neuere Sessions überschreiben ältere bei Faktenkonflikten (die Welt bewegt sich).
- Fäden mit `status: open` oder `priorität: hoch` sind aktiv und sollten bei thematisch passenden Fragen herangezogen werden.
- Verdächtige liegen in `figuren/` mit `entity_type: suspect`, damit sie sowohl in der Figuren-Übersicht als auch im Faden-Rollup [[Verdächtige]] erscheinen.
- `Willkommen.md` ist die spoilerfreie, spielerseitige Sicht. Keine GM-Geheimnisse dort hineinschreiben.
- Antworten an den Nutzer immer auf Deutsch verfassen, sofern nicht ausdrücklich anders gewünscht.
