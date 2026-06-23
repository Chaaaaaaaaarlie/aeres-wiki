---
type: meta
title: "Vorgangs-Protokoll"
created: 2026-05-12
updated: 2026-05-12
tags:
  - meta/log
---
# Vorgangs-Protokoll

Append-only. Neue Einträge stehen **oben**. Frühere Einträge nicht editieren.

Format:
```
## [JJJJ-MM-TT] Vorgang | Titel
- Quelle: …
- Zusammenfassung: [[Seite]]
- Erstellte Seiten: [[…]]
- Aktualisierte Seiten: [[…]]
- Kernerkenntnis: ein Satz
```

---

## [2026-06-23] recap | Session 13 – Piratenabwehr

- Quelle: `craig-suXgNX0kaw11-4hqp3Byds0u9flq.flac.zip` (Transkription: whisperx large-v3, 3342 Segmente, 3h 11min)
- Zusammenfassung: [[Session 13 - 23.06.2026]]
- Erstellte Seiten: [[Session 13 - 23.06.2026]], [[Transcript - Session 13 - 23.06.2026]]
- Aktualisierte Seiten: `hot.md`, `log.md`, `Willkommen.md`, `index.md`, `sessions/_index.md`
- Kernerkenntnis: Piratenangriff abgewehrt — Entscheidender Moment: Viris Suggestion charmt die Piraten-Anführerin und löst den Rückzug aus; Zestus-Crew betrachtet Gruppe fortan mit Ehrfurcht

---

## [2026-06-17] recap | Session 12 – Landratten und Piraten

- Quelle: `craig-zH1qP3suFZDO-sXIdxC4AiiKa0HM.flac.zip` (Transkription: whisperx large-v3, 2878 Segmente)
- Zusammenfassung: [[Session 12 - 17.06.2026]]
- Erstellte Seiten: [[Session 12 - 17.06.2026]], [[Mirene Calath]]
- Aktualisierte Seiten: [[Zarat]], [[Zestus]]
- Kernerkenntnis: Zarat ist eine Lepra-Seucheninsel (Leitwacht, Calderion Yolob, Halo-Zauber); Seeschlacht gegen Piraten läuft als Cliffhanger

---

## [2026-06-04] fix | Bild-Pfad für Static-Site korrigiert

- Problem: Bilder auf der publizierten Site (GitHub Pages) 404 — der Export-Root ist `wiki/`, das vault-root `_attachments/` liegt **außerhalb** und wird nicht mitpubliziert (Generator erzeugte Fallback-Link `![](../code_mended.png)`)
- Fix: `code_mended.png` + `code_papier.png` von `_attachments/` nach **`wiki/bilder/`** verschoben (im Content-Baum, ohne Unterstrich → auch Jekyll-sicher)
- Embeds bleiben unverändert Bare-`![[…]]` (Obsidian + Export lösen per Dateiname auf)
- Hinweis: künftige Wiki-Bilder gehören nach `wiki/bilder/`, nicht ins vault-root `_attachments/`

---

## [2026-06-04] assets | Codierpergament + verschlüsselter Brief eingebunden

- Quelle: `code_mended.png` (Chiffre-Schlüssel) + `code_papier.png` (verschlüsselter Brief) — vom Nutzer geliefert
- Bilder nach `_attachments/` verschoben und per `![[…]]` eingebettet
- Erstellte Seiten: [[Codierpergament]] (Schlüssel + Brief + dekodierter Text)
- Aktualisierte Seiten: [[Session 11 - 03.06.2026]] (Szene 5), [[Wo versteckt sich der Assassine]], `fäden/_index.md`, `index.md`
- Kernerkenntnis: Chiffre-Schlüssel der Assassinen-Helfer ist gesichert → künftige Nachrichten in derselben Chiffre lesbar.

---

## [2026-06-04] recap | Session 11 eingepflegt + Transkript bereinigt

- Quelle: `Session_11_Aeres_03.06.2026.txt` (WhisperX-Transkript der Session vom 2026-06-03)
- Transkript-Fix: 93 ASR-Eigennamenfehler am Vault-Kanon korrigiert (z. B. Sion→Zion, Harkers/HKSK→Harkas, Rugia/Roger→Rugir, Jolda/Joel→Hjolda, Doro→Chloro, Zerrat/Zatar→Zarat, Rusion→Rhusion). Bewusst behalten: „Patrizia" (Deckname für den Prinzeps), „Lyssa" (Spitzname Elysias). Backup: `Session_11_Aeres_03.06.2026.original.txt`
- Zusammenfassung: [[Session 11 - 03.06.2026]]
- Erstellte Seiten: [[Session 11 - 03.06.2026]], [[Zarat]], [[Sir Aschefall]], [[Kapitänin der Zestus]]
- Aktualisierte Seiten: [[Harkas]], [[Unbekannte Frau]], [[Die Boss hinter den Helfern]], [[Ritual der 13 Stiche]], [[Schwarzer Seidenstoff]], [[Eingeritzte Zeichen]], [[Aspasia Cortiso]], [[Hjolda]], [[Chloro Verde]], [[Doruk Val]], [[Princeps Orpheon von Lutaxa]], [[Kurkan Akrava]], [[Krokodil-Versteck]], [[Bernsteinauge]], [[Zestus]], [[Wo versteckt sich der Assassine]], [[Rakshasa-Assassine]], [[Zion]], [[Viri]], [[Elysia]], [[Rugir]]; Infrastruktur: `index.md`, `hot.md`, `Willkommen.md`, alle betroffenen `_index.md`
- Kernerkenntnis: Krokodil-Versteck geräumt, „Boss" (= Unbekannte Frau) tot durch Selbstvergiftung samt 13-Stiche-Mal → Spur führt zur Insel Zarat; Hjolda verlässt die Gruppe (Aspasias Leibwache); Ork-Belagerung Rhusions beginnt, während die Gruppe ausläuft. Level-Up.

---

## [2026-05-12] sprachwechsel | Wiki-Ordnernamen ins Deutsche umbenannt

- Vorgang: 10 wiki-Unterordner auf deutsche Namen umbenannt (per `git mv`, Historie bleibt erhalten)
- Mapping: characters→figuren, locations→orte, factions→fraktionen, creatures→kreaturen, deities→gottheiten, threads→fäden, sources→quellen, concepts→konzepte, comparisons→vergleiche, questions→fragen
- Unverändert: `lore/`, `sessions/`, `meta/`, `.raw/` (deutsch identisch oder rein technisch)
- Pfad-Sweep: 39 Verweise in 15 Markdown-Dateien angepasst — Wikilinks der Form `[[characters/_index|…]]`, Dataview-`FROM`-Klauseln, Pfade in Prosa/Struktur-Diagrammen
- CSS aktualisiert: 10 Selektoren in `.obsidian/snippets/vault-colors.css` (jetzt `data-path^="wiki/figuren"` etc.); zugehörige CSS-Variablen ebenfalls auf deutsche Namen vereinheitlicht
- Kernerkenntnis: Vault-Ordner sind jetzt vollständig deutsch. Frontmatter-Keys und `WIKI.md` bleiben weiterhin englisch (technische Bezeichner bzw. Schema-Referenz).

---

## [2026-05-12] sprachwechsel | Hauptsprache auf Deutsch umgestellt

- Vorgang: alle Infrastruktur-Seiten, die ich beim Scaffold in Englisch angelegt hatte, ins Deutsche übersetzt
- Übersetzt: `CLAUDE.md`, `wiki/index.md`, `wiki/overview.md`, `wiki/log.md`, `wiki/hot.md`, `wiki/meta/dashboard.md`, alle 12 `_index.md`-Übersichten in den Wiki-Unterordnern, die Templates `_templates/source.md` und `_templates/question.md`
- Nicht geändert: `WIKI.md` (Schema-Referenz, bleibt englisch), bestehende Kampagnen-Inhalte (waren bereits deutsch), Ordnernamen (`figuren/`, `orte/` etc. — Umbenennung wäre eigene Aktion mit CSS- und Wikilink-Anpassung), Frontmatter-Keys (`type`, `title` etc. bleiben technisch)
- Wikilinks zu `_index.md`-Seiten auf pfadbasierte Form mit deutschem Alias umgestellt, z. B. `[[figuren/_index|Figuren-Übersicht]]` (die alten Links der Form `[[Characters Index]]` hatten kein Ziel, da die Datei `_index.md` heißt — sie waren schon vor dem Sprachwechsel kaputt)
- Kernerkenntnis: aktive Kampagnen-Inhalte und neue Antworten jetzt durchgehend deutsch; Schema-Referenz bleibt englisch verfügbar

---

## [2026-05-12] lint | Widerspruchs-Sweep + Datenqualitäts-Fixes

- Vorgang: drei Widersprüche auflösen und Datenqualitäts-Probleme aus dem ersten Scan bereinigen
- Seite umbenannt: `Tabaxi-Assassine.md` → [[Rakshasa-Assassine]] (Enthüllung Session 10). 27 Wikilinks in 22 Dateien neu geschrieben. In Session-Seiten Alias erhalten (`[[Rakshasa-Assassine|Tabaxi-Assassine]]`), um die historische In-Fiction-Bezeichnung zu wahren; in aktuellen Seiten bare Link
- Neu geschriebene Seiten: [[Rakshasa-Assassine]] (komplett überarbeitet, Tags entfernt, Mojibake gefixt, chronologische Einordnung ergänzt), [[Magische Mordwaffe]] (Schlussfolgerungen neu gefasst — Klinge nicht magisch, Illusionsmagie vom Träger; `status: aktiv` ergänzt), [[Sokar Karioka]] (neue Sektion „Verlauf des Mordes" mit koordinierter Anschlags-Theorie), [[Verdächtige]] (neu gegliedert in „Aktiv gesucht / Verhaftet / Aufgeklärt")
- Callouts ergänzt: `[!contradiction]` auf Rakshasa-Assassine + Magische Mordwaffe; `[!stale]` auf Rakshasa-Assassine (Hjoldas Sumpf-Vision); `[!gap]` × 2 auf Sokar Karioka (koordinierter vs. paralleler Anschlag)
- Mojibake behoben: 🔴-Emoji und ≥-Symbol in Rakshasa-Assassine, Session 10, Wo versteckt sich der Assassine
- Kaputte Wikilinks gefixt: 7 Stellen mit dreifachem `]` und fehlendem Leerzeichen nach `-` in [[Chloro Verde]], [[Zion]], [[Rakshasa]], Session 9, Session 10, Rakshasa-Assassine
- Duplikat entfernt: [[Tabulei]] in [[Offene Fäden]] (war doppelt aufgeführt)
- Kernerkenntnis: jeder Widerspruch hat jetzt einen Callout auf beiden Seiten. Die Tabaxi→Rakshasa-Umbenennung wahrt die In-Fiction-Chronologie durch Aliasse in Session-Seiten — alte Recaps lesen sich weiter mit „Tabaxi-Assassine", der Link führt aber zur kanonischen [[Rakshasa-Assassine]]

---

## [2026-05-12] scaffold | Initiale WIKI.md-Migration

- Vorgang: vollständige Vault-Migration auf das WIKI.md-Schema
- Pre-Migration-Snapshot: Git-Commit `2d7c344`
- Verschobene Seiten: 87 (NPC/, Spieler/, Orte/, Sessions/, Kreaturen/, Lore/* → wiki/*)
- Gemergte Seiten: [[Ritual der 13 Stiche]] (3 Duplikate zur kanonischen Hinweise-Version zusammengeführt)
- Gelöschte Seiten: `Orte.md` (Root, durch [[orte/_index|Orte-Übersicht]] ersetzt)
- Wikilinks neu geschrieben: 166 pfad-präfixierte Links → Bare-Filename-Form über 53 Dateien hinweg
- Frontmatter: Pflichtfelder (`type`, `title`, `created`, `updated`) in allen 87 migrierten Dateien ergänzt; vorhandene Felder erhalten
- Infrastruktur angelegt: `wiki/index.md`, `wiki/overview.md`, `wiki/log.md`, `wiki/hot.md`, `wiki/meta/dashboard.md`, alle 13 `_index.md`-Sub-Übersichten, Vault-`CLAUDE.md`, `_templates/`, `.obsidian/snippets/vault-colors.css`, `.gitignore`
- Bestehende Landing-Seite [[Willkommen]] im Vault-Root behalten, Links umgeschrieben
- Kernerkenntnis: Vault ist jetzt WIKI.md-konform. Deutsche Inhalte unangetastet. Dateinamen erhalten, damit Wikilinks auflösen.
