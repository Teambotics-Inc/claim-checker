# Product direction: a public-interest evidence desk

**Decision recorded:** 2026-10-27  
**Status:** Product direction, not shipped capability  
**Related:** [The Claim Checker Standard](STANDARD.md), [Watchlist + Sibling Posts](WATCHLIST-SIBLING-POSTS.md), [Output Contract](OUTPUT-CONTRACT.md)

## Mission

Claim Checker is intended to become a public, open-source **evidence desk** useful to investigative journalists, reporters, independent researchers, analysts, and ordinary readers. It should help people collaborate without asking each person to be a field reporter, historian, analyst, editor, and software engineer at once.

**Someone who notices a pattern should be able to contribute to the investigation; someone with field evidence should be able to benefit from analysis.** Neither is automatically more authoritative than the evidence.

Claim Checker is not a substitute for journalism, an ideological classifier, an automated publisher, a ratings agency, or a machine that asks readers to trust its authority.

## Product-defining choice: output first

The research/evidence record is shared across audiences. What changes is its **presentation**, not the facts, provenance, verdict, uncertainty, or revision history.

> **One investigation. One canonical evidence record. Many representations.**
>
> **Trust should not require expertise; trustworthiness must withstand expert examination.**

The highest-priority product work is therefore the **output contract and user experience**, not additional automated research capabilities. Readers choose a depth, and can change it at any time:

1. **Simple:** a short, plain-language account with direct source hyperlinks, main finding, material caveat or contradiction, and a clear route to the evidence.
2. **Explore:** the same finding with causal/contextual explanation, source trails, chronological context, rival interpretations, and open questions.
3. **Expert:** the evidence dossier from the outset: atomic claims, captured originals, provenance, independence-grouped sources, chronological record, contradiction/falsification work, limits, verdicts, and exports.

A reader's *depth* is independent of *format*: narrative, timeline, outline, list, and sourced relationship graph can each be offered where supported. Users self-select; do not label them permanently as "layperson" or "journalist," infer capability, or lock evidence behind a proficiency gate.

## Editorial and evidence guarantees

- Every depth uses the **same versioned canonical investigation**; the output layer cannot secretly revise findings.
- A short answer does not earn permission to omit a material challenge, qualification, or evidence gap.
- Direct, usable citations survive every depth; a hyperlink alone is not a substitute for representing the cited evidence faithfully.
- A material factual assertion must resolve to traceable evidence records; inferred links remain expressly **inferred**.
- Source independence matters: syndicated copies of one originating statement are **not** multiple independent corroborations.
- Evidence classes remain separate: witnessed/reported, primary record, interpretation, hypothesis, and unresolved question. Avoid blurring witness testimony, an agent synthesis, and verified observation.
- The current five verdicts in [STANDARD.md](STANDARD.md) remain in force until reviewed deliberately. In particular, "unverifiable by design" must never imply proof of deliberate deception merely because verification was impossible.
- Preserve original claims and dated corrections. No silent edits; clearly distinguish the time of the claim, capture, assessment, and publication.
- **Human editorial approval before publication.** Agents may gather, propose, draft, and flag; they do not self-publish.
- Protect unpublished reporting, sensitive sources, and confidential evidence; never make a private investigative record public simply to support a shareable view.
- Challenge and correction mechanisms must be visible in all published outputs. Apply the same checks regardless of subject, including to our own claims.

## Reuse before rebuilding

**Claim Checker:** owns the canonical evidence records, verdicts, contradiction tests, source independence, longitudinal deltas, and publication gate.

**StoryTeller:** provides a potential read-only *presentation* adapter. Its existing sourced graph, sourced-vs-inferred edges, narratives, outlines, timelines, lists, and deep links are promising building blocks. Claim Checker remains authoritative; StoryTeller may project its data but must not autonomously invent facts, upgrade an inference to an observation, or modify an investigation's verdict.

Related codebase: [StoryTeller](https://github.com/Teambotics-Inc/StoryTeller). See [Output Contract](OUTPUT-CONTRACT.md) for the intended interface. Other repositories should be integrated only after a capability/ownership audit, rather than by assumption.

## Public release is separate from product direction

At the time of this decision, the connected GitHub repository is **private**, although older README wording says "public." Do not change visibility until a public-release review covers licensing, sensitive information, contributor safety, source protection, documentation, and a reproducible demo. Being accessible to journalists is a product requirement; releasing existing records without review is not.

## Research and validation

Use an ordinary reader and working reporter/investigator with **the same synthetic or properly cleared evidence fixture**. Ask each to interpret the finding, identify what remains unproven, find the primary source, recognize a meaningful contradiction, and locate the correction history. Test comprehension, retrieval time, omissions, keyboard/mobile accessibility, and whether outputs create conflicting understandings.

Treat this document as a design decision, **not evidence that the workflows have been implemented or validated**.

## Launch addendum — 2026-11-13

Recorded for the public launch. The body above is the 2026-10-27 decision record and is not rewritten; where it and the current documents differ, this addendum states the current position.

- **The direction is now implemented.** The human editorial approval gate, the output contract, and the challenge and correction mechanisms described above as direction are carried into the governing documents: `STANDARD.md`, `AGENTS.md`, `FEEDBACK.md`, and `docs/OUTPUT-CONTRACT.md`.
- **StoryTeller is the default presentation output** of a Claim Checker audit, per `AGENTS.md` (Step 9). The body above describes StoryTeller as "a potential read-only *presentation* adapter"; that assessment is superseded — the presentation work for an audit is done in StoryTeller, and Claim Checker remains the authoritative evidence record.
- **The public home of Claim Checker is the TeamBotics GitHub organisation.** The note above recording that the connected repository is private states the position at the time of the decision (2026-10-27); the public-release review it called for has been completed, and the method is published under TeamBotics.
