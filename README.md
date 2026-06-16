# dm-factory-workshop

## Setup

Teilnehmende brauchen:

- [Claude Code](https://github.com/anthropics/claude-code)
- [`beans` CLI](https://github.com/hmans/beans)
- [`jq`](https://github.com/jqlang/jq)
- [Node.js](https://github.com/nodejs/node) >= 20
- [`npm`](https://github.com/npm/cli) für Dependencies installieren, TypeScript bauen und Tests ausführen
- [`git`](https://github.com/git/git)

Beans CLI:

```bash
brew install hmans/beans/beans
beans version
```

Sandbox bauen:

```bash
cd sandbox
npm install
npm run build
npm test
```
