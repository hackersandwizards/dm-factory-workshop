# 00 — Planning Skill

Track: beide
Zeit: 30-35 Minuten

## Ziel

Baue einen Skill, der ein dauerhaftes Planungs-Artefakt erzeugt.

Das ist die Brücke von „Skill als Helfer" zu „Skill als Factory-Station".

## Übung

Erzeuge:

```text
exercise/.claude/skills/planner/SKILL.md
```

Minimales Frontmatter:

```yaml
---
name: planner
description: Use when the user wants to plan a non-trivial change before writing code. Produces a written plan file, not implementation.
---
```

Erforderlicher Workflow:

1. Projektkontext erkunden, bevor du Fragen stellst.
2. Eine Frage pro Nachricht, falls Klärung nötig ist.
3. 2-3 Ansätze mit Trade-offs präsentieren.
4. Stoppen und auf die explizite Ansatz-Wahl der Person warten.
5. Self-Review vor dem Schreiben.
6. Den Plan in `.plans/<task>.md` schreiben.

Erforderliche Plan-Sections:

```markdown
# <Task-Titel>

## Problem

## Constraints

## Non-Goals

## Chosen Approach

## Steps

## Verification
```

## Fortgeschrittene Variante

Wenn du Skills bereits kennst, mache den Planner strikter:

- harter Approach-Gate
- keine Implementierung, bis ausdrücklich verlangt
- strengeres Self-Review
- stabiles Schema
- klare Hand-off-Aussage

## Brücke zum Nachmittag

Am Nachmittag schreibt der Planner einen [Bean](https://github.com/hmans/beans) statt `.plans/<task>.md`.

Die Idee ist die gleiche:

```text
Skill -> dauerhaftes Artefakt -> nächste Factory-Station
```

Referenzlösung:

```text
solution/.claude/skills/planner/SKILL.md
```
