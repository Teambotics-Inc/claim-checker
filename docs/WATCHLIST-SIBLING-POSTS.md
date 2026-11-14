# Feature: Watchlist + Sibling Posts

*Proposed by Nik, 2026-10-22. Status: spec, not yet built. Dogfood instance already running by hand: the Boardy weekly tracker.*

## The idea in one line

Claim Checker does not only audit a company once. Agents keep a standing weekly watch on tracked sources, research every new hype claim they publish, and issue a **sibling post** — a dated, cited audit that lives permanently beside the claim it examines.

## Why "sibling"

The original claim is never edited, answered in place, or argued with on the claimant's turf. The sibling post is a separate, linked record with its own URL:

- **Parent** = the claim as published (quoted verbatim, with source URL and capture date).
- **Sibling** = the research: what could be verified, what could not, the sources grouped by independence, the verdict, and the delta since the last observation.

A reader who finds the hype finds the sibling one link away. A reader who finds the sibling can always reach the original wording — nothing is paraphrased into a strawman.

## The weekly loop

1. **Watch.** Each tracked entity has a watchlist of sources: its own site (including live counters), its LinkedIn company page, named principals' public posts, and coverage in tracked publications.
2. **Capture.** Once a week, an agent records new claims verbatim with URL and timestamp, plus the current value of every standing metric (counters, follower counts, headline figures). Captures are snapshots; snapshots are never overwritten.
3. **Diff.** New snapshot vs. previous: new claims, changed numbers, quietly edited or deleted claims. Drift is itself a finding and is reported as a delta, not folded silently into a revised history.
4. **Research.** Each new claim goes through the STANDARD.md battery: atomic claim, provenance, independence-grouped sources, the contradiction pass, and one of the five verdicts (confirmed / partially corroborated / self-reported only / unverifiable by design / contradicted).
5. **Draft.** The agent drafts the sibling post. Drafting is the agent's job; publishing is not (see Gates).
6. **Publish.** A human reviews and publishes. The sibling post ships with its citations attached and a "Challenge this audit" link, same as every other Claim Checker audit.

## Sibling post anatomy

- The claim, quoted verbatim, with source and capture date.
- What the claim would need to be true (the checkable form).
- The research: sources consulted, grouped by `independence_group` — fourteen outlets rewriting one press release count as one source.
- Verdict, in the standard five, with the evidence for it.
- The delta: how this claim or metric differs from the last weekly capture.
- Stated limits: what was not checked, what sits behind a paywall, what remains unknown.
- Challenge link (prefilled with the audit ID).

## Gates and conduct

- **Human publish gate, always.** Agents draft; a named human publishes. This follows the house grammar for consequential acts: draft → human review → publish are separate acts, and the published post carries a receipt of who approved it.
- **Read-only everywhere.** No likes, reactions, comments, follows, connection requests, messages, or shares on any watched platform. The watch observes; it never engages, and it never announces itself to the watched entity.
- **Human scale.** One pass per source per week. No bulk scraping. If a platform presents a login checkpoint or challenge, that source is skipped for the week and the skip is reported — the watch never defeats a checkpoint.
- **No silent edits.** A published sibling post can gain a dated erratum; it is never rewritten. If a claimant corrects a claim, the correction is captured as next week's delta — which is the outcome the feature exists to produce.

## What gets watched

- **Companies** (the audit subjects): site claims and counters, company pages, principal posts, press coverage.
- **Publications** (the carriers): when a tracked outlet publishes a claim about a tracked company, the coverage itself becomes a claim atom — who carried it, in what form (feature, brief, sponsored label present or absent), and whether any verification step is visible in the piece. The watch treats distribution as part of the claim's life, not as neutral weather around it.

## Dogfood

The Boardy weekly tracker (baseline frozen Oct 20–21, 2026; first scheduled run Oct 28, 2026) is this feature run by hand: weekly captures of boardy.ai counters, LinkedIn claims, Reddit sentiment and press, diffed against baseline with a one-line verdict. Claim Checker's build generalises it: any tracked entity, the same loop, sibling posts as the published output instead of a chat report.

## Out of scope for v1

- Real-time monitoring. Weekly is the design: hype is a longitudinal phenomenon, and drift only shows on a weekly grain.
- Automated publishing. Not planned at any version; the gate is the product's credibility.
- Scores. The five verdicts and the drift record are the output. No universal hype score, per STANDARD.md.
