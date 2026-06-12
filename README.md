### Orionix — production-readiness audits

I read code I find on GitHub and surface the bugs that would actually break production — the ones that cost real money and downtime when they slip into a live system. Free during this build phase. 48h turnaround.

For a full deep audit of an entire codebase — security, reliability, performance, deployment — that's available on request.

#### Credentials

★ **Anthropic Cyber Verification Program approved researcher** (June 2026). Anthropic directly adjusted safeguards on my account for vulnerability research workflows after reviewing my track record. About the CVP / Mythos-class safeguards: [anthropic.com/news/claude-fable-5-mythos-5](https://www.anthropic.com/news/claude-fable-5-mythos-5).

#### Recent reads

- **[hatchet-dev/hatchet #4131](https://github.com/hatchet-dev/hatchet/issues/4131)** — `failTasksTx` attaches the wrong error message after dedup/reorder (positional indexing instead of `taskId`). Accepted by maintainer; fixed in [PR #4137](https://github.com/hatchet-dev/hatchet/pull/4137) (approved by @Gregfurman, collaborator). Same audit pass: [#4128](https://github.com/hatchet-dev/hatchet/issues/4128), [#4129](https://github.com/hatchet-dev/hatchet/issues/4129), [#4130](https://github.com/hatchet-dev/hatchet/issues/4130) — all labelled `accepted`.
- **[BigBodyCobain/Shadowbroker #375](https://github.com/BigBodyCobain/Shadowbroker/issues/375)** — dev-mode bind, `/api/live-data` lock contention, shared-pool 120s timeout. Maintainer shipped fixes in 34 minutes ([commit 9a0a9a1](https://github.com/BigBodyCobain/Shadowbroker/commit/9a0a9a1)).
- **[BerriAI/litellm GHSA-wr37-fm8c-4vvq](https://github.com/BerriAI/litellm/security/advisories/GHSA-wr37-fm8c-4vvq)** — JWT auth: audience and issuer verification disabled by default leaves shared-IdP deployments open to cross-application token substitution. Reporter credit (advisory closed as duplicate by maintainer @jaydns, tracked internally).
- **[pirona/ghost-poster #1](https://github.com/pirona/ghost-poster/issues/1)** — Android Keystore hardening: debug keystore in git, `signingConfigs.release` on CI, `keyAlias` rotation. Maintainer applied and closed.
- **[mvanhorn/last30days-skill #506](https://github.com/mvanhorn/last30days-skill/issues/506)** — `check-config.sh` SessionStart hook crash on unbalanced quote in `.env` + `parse_date` numeric-first epoch trap.
- **[honojs/hono #5010](https://github.com/honojs/hono/issues/5010)** — method-override `duplex: 'half'` missing, `compress()` corrupting 206 Partial Content, aws-lambda adapter missing `globalThis.crypto` polyfill.
- **HackerOne Vercel OSS** — 3 reports on `vercel/ai`. Triager feedback verbatim: *"excellent documentation quality with detailed code references."* 1 still in review.
- **`getsentry/relay`** — disclosure sent to `security@sentry.io` (June 2026): AI token cost double-counting in `relay-event-normalization/src/normalize/span/ai.rs` causing billing inflation (CWE-682). Under triage.
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
