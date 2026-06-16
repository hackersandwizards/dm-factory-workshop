# 01 — Factory-Contract

Zeit: 15 Minuten

## Ziel

Den Klebstoff zwischen den Stationen sichtbar machen, bevor Teilnehmende etwas bauen oder ausführen.

## Contract

```text
Feature-Idee
  -> /planner <idee>
  -> Bean mit ## High-Level Plan
  -> /refine <bean-id>
  -> selber Bean mit ## Refined Plan
  -> /implement <bean-id>
  -> Branch, Commits, Implementation Log
```

## Erklären

Die Factory funktioniert nicht, weil ein riesiger Prompt sich an alles erinnert.

Sie funktioniert, weil jede Station hat:

- einen Input
- einen Output
- ein dauerhaftes Artefakt
- eine Grenze
- einen Hand-off-Contract

## Bean inspizieren

Aus `sandbox/`:

```bash
beans list
beans show sandbox-exercise-olqc
```

Achte auf:

- Titel
- Status
- Body
- `## High-Level Plan`
- `## Refined Plan`, falls vorhanden

## Diskussion

Fragt:

- Auf welchen exakten Text verlässt sich die nächste Station?
- Was passiert, wenn die Überschrift umbenannt wird?
- Welche Daten gehören in den Bean?
- Welche Daten gehören nicht in den Bean?

