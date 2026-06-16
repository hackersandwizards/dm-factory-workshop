# 02 — Planner zum Bean

Zeit: 30-45 Minuten
Level: 2

## Ziel

Passe einen Planning-Skill so an, dass er einen Bean erzeugt statt einer `.plans/<task>.md`-Datei.

Teilnehmende, die nicht bereit sind, können nutzen:

```text
../../supplied/planner/.claude/skills/planner/SKILL.md
```

## Übung

Erzeuge:

```text
sandbox/.claude/skills/planner/SKILL.md
```

Frontmatter:

```yaml
---
name: planner
description: Use when starting a new feature. Creates a new Bean with a high-level plan and acceptance criteria. No code, no file paths.
argument-hint: brief feature description
allowed-tools: Read Grep Glob Bash
---
```

Erforderlicher Workflow:

1. Feature-Idee erfassen.
2. Nur klären, wenn nötig.
3. 2-3 Ansätze präsentieren.
4. Stoppen und auf die explizite Ansatz-Wahl der Person warten.
5. Self-Review auf Abstraktionsebene.
6. Bean über das `beans`-CLI erzeugen.

Erforderliche Bean-Section:

```markdown
## High-Level Plan

**Approach** — ...

**Steps**
- ...

**Acceptance Criteria**
- ...

**Non-Goals**
- ...
```

## Harte Regeln

- Kein Source-Code editieren.
- `.beans/*.md` nicht direkt editieren.
- Keine Dateipfade, Funktionsnamen, Klassennamen oder Zeilennummern.
- `beans create` benutzen.
- Die Überschrift muss exakt `## High-Level Plan` lauten.

## Test

```bash
cd sandbox
claude
> /planner Add parentheses support to the calculator
```

Inspizieren:

```bash
beans list
beans show <new-id>
```

Referenzlösung:

```text
solution/.claude/skills/planner/SKILL.md
```
