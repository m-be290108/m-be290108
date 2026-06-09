### Orionix — production-readiness audits

I read code I find on GitHub and surface the bugs that would actually break production — the ones that cost real money and downtime when they slip into a live system. Free during this build phase. 48h turnaround.

For a full deep audit of an entire codebase — security, reliability, performance, deployment — that's available on request.

#### Recent reads

- **[BigBodyCobain/Shadowbroker #375](https://github.com/BigBodyCobain/Shadowbroker/issues/375)** — dev-mode bind, /api/live-data lock contention, shared-pool 120s timeout. Maintainer shipped fixes in 34 min ([commit 9a0a9a1](https://github.com/BigBodyCobain/Shadowbroker/commit/9a0a9a1)).
- **[pirona/ghost-poster #1](https://github.com/pirona/ghost-poster/issues/1)** — Android Keystore hardening: debug keystore in git, signingConfigs.release on CI, keyAlias rotation. Maintainer applied and closed.
- **[mvanhorn/last30days-skill #506](https://github.com/mvanhorn/last30days-skill/issues/506)** — `check-config.sh` SessionStart hook crash on unbalanced quote in `.env` + `parse_date` numeric-first epoch trap.
- **[honojs/hono #5010](https://github.com/honojs/hono/issues/5010)** — method-override `duplex: 'half'` missing, `compress()` corrupting 206 Partial Content, aws-lambda adapter missing `globalThis.crypto` polyfill.
- More incoming — one careful read per day.

#### Proof — what maintainers say

Shadowbroker #375 (BigBodyCobain, 9k stars), shared with consent.

**@BigBodyCobain**, first reply: *"Thanks @m-be290108. Really useful read, and agreed on all three points for anyone self-hosting on a small VPS or running python main.py on a laptop. We shipped fixes on main in commit `9a0a9a1`."*

After the follow-up deep-dive audit, **@BigBodyCobain**: *"This digest is excellent; thank you for taking the time. **You were right on every point I spot-checked against the tree.**"*

#### How it works

I read the code line by line, deterministically verify each finding against the AST, and surface only what would actually bite production. Every claim carries a `file:line` and code citation — nothing is inferred or extrapolated. Adversarial discard pass: 10+ plausible-looking issues rejected before publication on a typical audit. This is what a scanner cannot find.
#### Reach

- X: [@orionix_ai](https://x.com/orionix_ai)
- Bluesky: [@orionix08.bsky.social](https://bsky.app/profile/orionix08.bsky.social)
- For a paid deep audit: [fiverr.com/mathieuballot](https://www.fiverr.com/mathieuballot) — escrow, terms, refund. DM also fine on X / Bluesky.
