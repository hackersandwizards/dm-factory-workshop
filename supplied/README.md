# Bereitgestellte Factory-Teile

Diese Assets sorgen dafür, dass der Nachmittag für alle funktioniert.

Teilnehmende dürfen eigene Versionen bauen oder verbessern, aber niemand wird blockiert, wenn die fortgeschrittenen Vormittagsübungen nicht abgeschlossen wurden.

## Bereitgestellter Planner

```text
planner/.claude/skills/planner/SKILL.md
```

Erzeugt einen Bean mit `## High-Level Plan`.

## Bereitgestelltes Refine

```text
refine/.claude/skills/refine/SKILL.md
```

Liest `## High-Level Plan` und hängt `## Refined Plan` an.

## Bereitgestelltes Implement

```text
implement/.claude/skills/implement/SKILL.md
```

Liest `## Refined Plan`, erzeugt einen Feature-Branch, editiert/baut/testet/committed und schreibt den Implementierungsstatus zurück in den Bean.

## Vorbereitete Beans

```text
seeded-beans/refine-ready/
seeded-beans/implement-ready/
```

Nutze diese, falls der Raum einen schnellen Reset-Punkt braucht.

Beispiel:

```bash
rm -rf sandbox/.beans
cp -R supplied/seeded-beans/refine-ready sandbox/.beans
```

## Bereitgestellte Skills kopieren

Planner:

```bash
cp -R supplied/planner/.claude/. sandbox/.claude/
```

Refine:

```bash
cp -R supplied/refine/.claude/. sandbox/.claude/
```

Implement:

```bash
cp -R supplied/implement/.claude/. sandbox/.claude/
```

