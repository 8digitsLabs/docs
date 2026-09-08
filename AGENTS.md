# Documentation project instructions

## About this project

- Public documentation for oka, built on [Mintlify](https://mintlify.com). Served at `oka.finance/docs`.
- Pages are MDX with YAML frontmatter. Configuration lives in `docs.json`.
- The product itself lives in a separate repository, `8digitsLabs/oka-finance`. This repo holds prose only.

## Facts come from the code, not from memory

Every number on this site — fees, minimums, chain lists, issuer names — must be traceable to the product
repository. When you cannot verify a claim there, leave it out and say so, rather than approximating it.

Two traps have already produced wrong public pages:

- **Mock data.** `apps/web/src/data/mock/` in the product repo contains invented figures for demo purposes,
  and they are explicitly flagged as invented in the file headers. They are not product facts. This applies
  in particular to everything about the OKA and IOKA tokens.
- **Stale prose.** Earlier documentation claimed "8+ chains" and "seven EVM chains" when the catalog had six
  chains, five of them EVM. Prose copied from prose inherits its errors. Go back to `packages/config/src`.

Legal and eligibility claims are out of scope. Do not write about who may or may not use the service, in
which jurisdiction, on your own initiative; link to `oka.finance/terms` instead.

## Terminology

Keep these apart. They are the vocabulary the product is built on, and collapsing any two of them makes a
page unreadable:

- **Underlying** — the real security, AAPL. Never held on oka.
- **Wrapper** — a token an issuer mints to track an underlying, AAPLx. A claim on the issuer.
- **Listing** — one wrapper on one chain. The unit that is actually traded and ranked.
- **Exposure** — what a user holds after a fill.
- **Cash** — unspent stables in the execution wallet.
- **Fill** / **Exit** — a buy / a sale. Not "order" when you mean one of them specifically.
- **Take** — oka's fee. **Gas take** — the stablecoin charge covering native gas. Distinct things.
- **Execution wallet** — the EVM smart account plus Solana keypair created at sign-in, presented as one.

Say "stables", not "stablecoins", in body copy. Say "chain", not "network".

## Style

- Second person, active voice, present tense.
- One idea per sentence. Prefer a short declarative sentence to a qualified one.
- Explain *why* a constraint exists whenever it looks arbitrary — minimums, all-or-nothing fills, the venue
  not being user-selectable. A rule without its reason reads as an excuse.
- Sentence case for headings. Bold for UI elements. Code formatting for tokens, paths and commands.
- No marketing register: no "seamless", "powerful", "revolutionary", no exclamation marks.
- Numbers in tables, not in prose, when there are more than three of them.

## Before pushing

Run `mint broken-links`. Pushing to `main` publishes.
