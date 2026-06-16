# 03 — Refine-Bean

Zeit: 45-60 Minuten
Level: 3

## Ziel

Baue oder verbessere `/refine`: liest einen Bean mit `## High-Level Plan`, exploriert die Codebase über genau einen read-only Subagent und hängt `## Refined Plan` an.

Teilnehmende, die nicht bereit sind, können nutzen:

```text
../../supplied/refine/.claude/skills/refine/SKILL.md
```

## Übung

Erzeuge:

```text
sandbox/.claude/skills/refine/SKILL.md
```

Frontmatter:

```yaml
---
name: refine
description: Use after /planner. Takes a Bean with ## High-Level Plan, explores the codebase through a read-only subagent, and appends ## Refined Plan.
argument-hint: <bean-id>
allowed-tools: Read, Grep, Glob, Bash, Task
---
```

Erforderlicher Workflow:

1. Bean lesen mit `beans show <bean-id> --json`.
2. `.body` parsen.
3. Die literale `## High-Level Plan`-Section extrahieren.
4. Abbrechen, falls die Section fehlt.
5. Status auf `in-progress` setzen.
6. Genau einen read-only Subagent zur Codebase-Exploration dispatchen.
7. `## Refined Plan` komponieren und anhängen.
8. Jeden referenzierten existierenden Pfad verifizieren.

Erforderliches Schema:

```markdown
## Refined Plan

### Files to change
- path:line — what changes
- path:NEW — why a new file is needed

### New signatures
- ReturnType function_name(Args) — purpose

### Test sketch
- test_name — Input -> Expected
```

## Harte Regeln

- Kein Source-Code editieren.
- `.beans/*.md` nicht direkt editieren.
- Genau ein Subagent-Dispatch.
- Subagent ist read-only: keine Edits, keine Builds, keine Tests.
- Jeder existierende Pfad im Refined Plan muss verifiziert sein.
- Die Überschrift muss exakt `## Refined Plan` lauten.

## Test

Nutze einen Bean, der von `/planner` erzeugt wurde, oder kopiere einen aus:

```text
../../supplied/seeded-beans/refine-ready/
```

Dann ausführen:

```bash
cd sandbox
claude
> /refine <bean-id>
```

Referenzlösung:

```text
solution/.claude/skills/refine/SKILL.md
```
