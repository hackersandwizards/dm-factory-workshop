# calc — Workshop Sandbox

Ein minimaler TypeScript-CLI-Taschenrechner. Lexer + Recursive-Descent-Parser +
Tree-Walking-Evaluator + REPL. Wird als gemeinsame Codebasis für die Übung am
Tag 1 Nachmittag zu Factory-Pipeline-Skills (Planner -> Refine -> Implement)
verwendet.

## Build & Test

```bash
npm install
npm run build
npm test
```

Erwartet: alle Tests grün.

## REPL starten

```bash
npm run repl        # via tsx, kein Build nötig
# oder nach `npm run build`:
npm start           # führt node dist/main.js aus
```

Beispielsession:

```
calc REPL — type 'exit' or Ctrl-D to quit
> 1+2*3
7
> 10/2
5
> 5-3
2
> 20-6/2
17
> 1/0
error: division by zero
> exit
```

`exit`, `quit` oder Ctrl-D (EOF) beenden die Schleife. Parser- und Laufzeitfehler
werden abgefangen, ausgegeben, und die REPL läuft weiter.

## Grammatik (Stand heute)

```
expr   -> term   (('+' | '-') term)*
term   -> factor (('*' | '/') factor)*
factor -> NUMBER
```

Nur Ganzzahlen. Links-assoziativ für `+ -` und `* /`. Whitespace wird ignoriert.

Die Workshop-Beans erweitern diese Grammatik — Klammern, Dezimalzahlen — siehe
`.beans/`.

## Layout

```
src/
  lexer.ts        Tokenisierung: NUMBER, PLUS, MINUS, STAR, SLASH, END
  parser.ts       Recursive-Descent-Parser, AST-Knoten (Number, BinaryOp)
  evaluator.ts    läuft über den AST, gibt eine Zahl zurück
  main.ts         REPL
tests/
  lexer.test.ts
  parser.test.ts
  evaluator.test.ts
package.json      Scripts, Dependencies (Vitest), ESM
tsconfig.json     TypeScript-Konfiguration (strict mode)
.beans/           ein .md pro Workshop-Bean (siehe CLAUDE.md)
```
