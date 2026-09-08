# oka documentation

Public documentation for [oka](https://oka.finance), built on [Mintlify](https://mintlify.com) and served at
`oka.finance/docs` through an nginx reverse proxy — the site itself is hosted by Mintlify.

## Working on it

```bash
npm i -g mint   # once
mint dev        # http://localhost:3000
```

`mint broken-links` checks every internal link. Run it before pushing.

## Layout

| Path | What lives there |
|---|---|
| `docs.json` | Navigation, theme, colours, navbar and footer |
| `index.mdx`, `quickstart.mdx` | Entry points |
| `guides/` | Task pages: deposit, buy, sell, withdraw |
| `concepts/` | How it works: what you own, routing, wallets and keys |
| `reference/` | Costs, chains and issuers, glossary, FAQ |
| `logo/`, `favicon.ico` | Brand assets, mirrored from the product repository |

## Publishing

Pushing to `main` deploys. There is no build step to run and no artefact to commit.

## A note on accuracy

Figures on this site — fees, minimums, chain and issuer lists — come from `8digitsLabs/oka-finance`, mostly
from `packages/config/src`. They are not to be written from memory, and the invented numbers in the product's
mock data are not product facts. `AGENTS.md` has the details.
