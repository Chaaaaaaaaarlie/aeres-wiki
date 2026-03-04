# CODEX.md

## Vault Ziel und Scope

Dieser Vault dokumentiert die DnD-Kampagne in Rhusion konsistent, referenzierbar und patchbar.

Scope:
- Session-Chronik
- Charaktere/NSCs
- Orte
- Hinweise, Verdächtige, Offene Fäden
- Politik, Fraktionen, Hintergrund
- Glossar-Anbindung

Nicht-Scope:
- Regel-Optimierung ohne In-Game-Beleg
- Spekulative Lore ohne Kennzeichnung

## Ordnerstruktur und Namenskonventionen

Basis: `Rhusion/`
- `Sessions/`: `Session X – Titel.md` oder vom Nutzer vorgegebenes Format
- `Charaktere/`: Spielercharaktere
- `NSCs/`: benannte NSCs
- `Orte/`: je Ort eine Datei
- `Hinweise/`: harte Indizien/Fakten
- `Verdächtige/`: Verdachtslage pro Entität
- `Offene Fäden/`: ungeklärte Fragen mit nächsten Schritten
- `Politik/`, `Hintergrund/`, `Aeres/`: Lore

Konventionen:
- Kanonische Schreibweise als Dateiname
- Abweichende Schreibweisen als Alias-Hinweis im Inhalt
- Keine stillen Umbenennungen ohne Freigabe

## Frontmatter Standards

### Session
- `tags: [session, session-X]`
- `datum: YYYY-MM-DD`
- `ort: ...`

### NPC
- `tags: [nsc, ...]`
- `status: aktiv|ungeklärt|verstorben|archiv`

### Ort
- `tags: [ort, ...]`
- `status: aktiv|ungeklärt|archiv`

### Fraktion
- `tags: [fraktion, ...]`
- `status: aktiv|inaktiv|ungeklärt`

### Quest/Offener Faden
- `tags: [offen, ...]`
- `priorität: hoch|mittel|niedrig`

### Item/Hinweis
- `tags: [item|hinweis, ...]`
- `status: aktiv|ungeklärt|gelöst`

## Linking Regeln

- Immer Wiki-Links `[Seitenname]`
- Erste Erwähnung eines relevanten Begriffs verlinken
- Bei Alias-Fällen: auf kanonische Seite verlinken
- Keine toten Sammellinks; lieber konkrete Seiten

## Alias Regeln

- ASR-/Transkriptvarianten als Textnotiz auf kanonischer Seite erfassen
- Beispiele: `Zion/Sion/Xion`, `Elva/Ilva/Eva`, `Zestus/Cestus`
- Keine zweite Seite nur wegen Schreibvariante

## Tagging Regeln

- Tags knapp und funktional
- Keine redundanten Synonyme
- Status immer über Frontmatter `status`, nicht nur Tag

## Glossar Regeln

Glossar-Datei: `D:\Bots\TranscribeX\glossary_prompt.txt`

Aufnahme in Glossar, wenn:
- Begriff mehrfach auftaucht
- Plot-relevant ist
- Schreibvarianten Konflikte erzeugen

Bei Konflikten:
- `kanonische Form` + `bekannte Varianten` dokumentieren

## Intake Workflow für neue Transkripte

1. Rohtranskript lesen (Sprecherlabels beachten)
2. Extrahieren:
- Szenenfolge
- harte Fakten
- Entscheidungen
- neue Entitäten (NPC, Ort, Item, Fraktion)
- offene Fäden
3. Gegen Vault vergleichen
4. Konflikte markieren (Name, Datum, Beziehung, Duplikat)
5. Change Requests priorisieren
6. Erst nach Freigabe patchen

## Consistency Checks Liste

- Namenskonsistenz (Haupt- und Aliasform)
- Session-Kette (`vorherige`/`nächste`)
- Ortsduplikate
- NSC-Duplikate
- Widersprüchliche Beziehungen
- Timeline-Reihenfolge
- Tote Links
- Fehlende Verknüpfungen bei neuen Kernbegriffen
- Frontmatter-Vollständigkeit

## Change Request Workflow

Format:
- ID
- Priorität
- Betroffene Datei(en)
- Problem
- Konkrete Änderung
- Risiko bei Nicht-Änderung

Beispiel:
- `CR-12 | hoch | Orte/Tigerauge.md`
- Problem: Duplikat zu Tigerauge + Schreibfehler
- Änderung: Als Alias/Redirect markieren, Links auf Tigerauge führen
- Risiko: Split-Brain bei Lore-Pflege

## Patch Workflow

- Ohne Freigabe keine Dateischreiboperation
- Nach Freigabe nur konkrete, reproduzierbare Änderungen
- Bei hoher Unsicherheit: Unsicherheitsmarker statt Faktbehauptung

## Unified Diff Beispiel

```diff
*** Begin Patch
*** Update File: Rhusion/Orte/Beispiel.md
@@
-Alttext
+Neutext
*** End Patch
```

## Sicherheitsregeln

- Nie ohne Freigabe schreiben/umbenennen/verschieben/löschen
- Niemals Fakten erfinden
- Unsicherheiten explizit markieren (`Unsicher`, `unbestätigt`, `vermutet`)
- Sprecherlabels nicht als Identitätsbeweis missbrauchen
- Konflikte immer als Change Request vor endgültigem Patch
