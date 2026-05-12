---
type: meta
title: "Wiki-Dashboard"
created: 2026-05-12
updated: 2026-05-12
tags:
  - meta/dashboard
---
# Wiki-Dashboard

Benötigt das **Dataview**-Community-Plugin, damit die Query-Blöcke unten gerendert werden.

## Letzte Aktivität

```dataview
TABLE type, status, updated FROM "wiki" WHERE !contains(file.name, "_index") SORT updated DESC LIMIT 20
```

## Saatseiten (Ausbau nötig)

```dataview
LIST FROM "wiki" WHERE status = "seed" SORT updated ASC
```

## Heiße Fäden

```dataview
LIST FROM "wiki/fäden" WHERE priorität = "hoch" OR status = "open" SORT file.name ASC
```

## Figuren ohne Quellen

```dataview
LIST FROM "wiki/figuren" WHERE !sources OR length(sources) = 0
```

## Seiten nach Typ

```dataview
TABLE length(rows) AS Anzahl FROM "wiki" WHERE !contains(file.name, "_index") GROUP BY type
```

## Letzte Sessions

```dataview
TABLE updated FROM "wiki/sessions" WHERE !contains(file.name, "_index") SORT file.name DESC LIMIT 5
```
