# Tag 1 Nachmittag — Gemeinsame Factory-Spine

Die Nachmittagsübungen funktionieren auch dann, wenn du die fortgeschrittenen Vormittagsübungen nicht abgeschlossen hast.

Wir starten von einer gemeinsamen Baseline:

- bereitgestellter Planner
- bereitgestelltes Refine
- bereitgestelltes Implement
- vorbereitete Beans

Du kannst bereitgestellte Teile durch deine eigenen ersetzen, wenn sie fertig sind.

**Wir arbeiten im bereitgestellten `sandbox`-Ordner!**


## Vor dem Start

Falls du am Vormittag keinen Planning-Skill gebaut hast — [00 Planner](00-planning-skill/README.md) (30-35 Min) als Aufwärmer. Etabliert das Muster „Skill → dauerhaftes Artefakt", auf dem die Nachmittags-Factory aufbaut. Optional, aber empfohlen für Level 2.

## Factory-Contract

```text
/planner <idee>
  -> Bean mit ## High-Level Plan

/refine <bean-id>
  -> selber Bean mit ## Refined Plan

/implement <bean-id>
  -> Branch, Commits, Implementation Log
```

Der Klebstoff ist keine Magie. Es ist der Contract:

- Bean-ID wird zwischen Stationen weitergereicht.
- `/planner` schreibt exakt die Überschrift `## High-Level Plan`.
- `/refine` liest exakt die Überschrift `## High-Level Plan`.
- `/refine` schreibt exakt die Überschrift `## Refined Plan`.
- `/implement` liest exakt die Überschrift `## Refined Plan`.

## Empfohlener Zeitplan

| Segment | Zeit | Aktivität |
| --- | ---: | --- |
| (Optional) Aufwärmer | 30-35 Min | 00 Planning-Skill für Nachzügler vom Vormittag |
| Gemeinsame Erklärung | 15 Min | Factory-Contract erklären |
| Wahl der Übung | 50-60 Min | Level 1, 2 oder 3 wählen |
| Implement-Demo | 15-20 Min | Trainer führt bereitgestelltes `/implement` aus |
| Debrief | 10 Min | Was hat die Factory zusammengehalten? |

## Übungs-Level

### Level 1 — Bereitgestellte Factory ausführen

Nutze bereitgestelltes `/planner`, `/refine` und `/implement`.

```
cp -R supplied/planner/.claude/.    sandbox/.claude/
cp -R supplied/refine/.claude/.     sandbox/.claude/
cp -R supplied/implement/.claude/.  sandbox/.claude/
```

Inspiziere den Bean nach jedem Schritt.

Am besten für Teilnehmende, die den Vormittag mit Anfänger-Übungen oder Tooling verbracht haben.

### Level 2 — Planner ersetzen

Passe deinen Vormittags-Planning-Skill so an, dass `/planner` einen Bean mit `## High-Level Plan` erzeugt.

Am besten für Teilnehmende, die den Planning-Skill abgeschlossen haben.

### Level 3 — Refine verbessern

Verbessere `/refine` mit einem read-only Subagent, strikterer Validierung und besserer Planung auf Dateiebene.

Am besten für fortgeschrittene Teilnehmende.

## Übungen

**Aufwärmer (optional, Vormittags-Carry-over):**
- [00 Planner](00-planning-skill/README.md) — Skill schreibt `.plans/<task>.md`

**Nachmittag — Factory-Pipeline:**
1. [01 Factory-Contract](01-factory-contract/README.md) — Theorie + Bean inspizieren
2. [02 Planner zum Bean](02-planner-to-bean/README.md) — Level 2
3. [03 Refine-Bean](03-refine-bean/README.md) — Level 3

## Bereitgestellte Fallbacks

```text
../supplied/planner/
../supplied/refine/
../supplied/implement/
../supplied/seeded-beans/
```

Schau in die Lösungen, falls du nicht weiterkommst.
