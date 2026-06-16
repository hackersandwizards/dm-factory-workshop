# Tag 1 Nachmittag — Gemeinsame Factory-Spine

Die Nachmittagsübungen funktionieren auch dann, wenn du die fortgeschrittenen Vormittagsübungen nicht abgeschlossen hast.

Wir starten von einer gemeinsamen Baseline:

- bereitgestellter Planner
- bereitgestelltes Refine
- bereitgestelltes Implement
- vorbereitete Beans

Du kannst bereitgestellte Teile durch deine eigenen ersetzen, wenn sie fertig sind.

**Wir arbeiten im bereitgestellten `sandbox`-Ordner!**


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
| Gemeinsame Erklärung | 15 Min | Factory-Contract erklären |
| Wahl der Übung | 50-60 Min | Level 1, 2 oder 3 wählen |
| Implement-Demo | 15-20 Min | Trainer führt bereitgestelltes `/implement` aus |
| Debrief | 10 Min | Was hat die Factory zusammengehalten? |

## Übungs-Level

### Level 0 — Planning-Skill-Warm-up

Baue einen eigenständigen Planning-Skill, der `.plans/<task>.md` schreibt. Vormittags-Übertrag / Pre-Exercise — etabliert das Muster „Skill erzeugt ein dauerhaftes Artefakt", auf dem die Nachmittags-Factory aufbaut. Siehe [00 Planner](00-planning-skill/README.md).

Am besten für Teilnehmende, die die Vormittags-Planungs-Übung übersprungen haben oder vor dem Einstieg in die Bean-basierte Factory eine Auffrischung wollen.

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

0. [00 Planner](00-planning-skill/README.md)
1. [01 Factory-Contract](01-factory-contract/README.md)
2. [02 Planner zum Bean](02-planner-to-bean/README.md)
3. [03 Refine-Bean](03-refine-bean/README.md)

## Bereitgestellte Fallbacks

```text
../supplied/planner/
../supplied/refine/
../supplied/implement/
../supplied/seeded-beans/
```

Schau in die Lösungen, falls du nicht weiterkommst.
