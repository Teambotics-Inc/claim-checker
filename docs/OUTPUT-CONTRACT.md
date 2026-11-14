# Output Contract v0.1 — evidence invariant, presentation adaptive

**Date:** 2026-10-27  
**Status:** Governing contract for desk-published outputs as of the public launch, 2026-11-13 (originally proposed 2026-10-27; see the launch note below)  
**Owner:** Claim Checker (canonical evidence and editorial rules)  
**Consumer:** StoryTeller adapter and future output clients  
**Context:** [Journalism direction](JOURNALISM-DIRECTION.md), [Claim Checker Standard](STANDARD.md)

**Launch note (2026-11-13):** As of the public launch this contract **governs the outputs the Claim Checker desk publishes**: every desk-published representation must satisfy the invariant and the minimum display contract below, and STANDARD.md's *Presentation* section points here for the governing output rules. Sections that describe machinery — the canonical input format, the StoryTeller adapter, the implementation order — record implementation status, not the contract's authority: where they describe work as unbuilt, that is a statement about the build, not a disclaimer of the rules.

## Non-negotiable invariant

> Given the same investigation version, every output depth must preserve **the same material claims, findings, evidentiary status, material counterevidence, limitations, provenance, correction state, and time scope**.

Do not confuse "same research data" with identical display density. It is fine for a short view to summarize detail and expose it on demand. It is **not** fine for its omission, tone, metaphor, headline, or chart to change what the finding means.

Two independent dimensions:
- **Depth:** simple / explore / expert, chosen by the reader and switchable at any time.
- **Representation:** read / timeline / graph / outline / list (and structured export), offered only where the evidence supports it.

No role-based gate, automated sophistication profiling, or hidden professional-only source set.

## Canonical input (proposal, not an existing file format)

The output engine consumes a **versioned, read-only snapshot or reference** to Claim Checker's research record. These conceptual fields must map onto the existing audit ledger rather than replace it without review:

| Field | Required meaning |
| --- | --- |
| investigation_id, record_version, snapshot_hash | Identical across views for a given record; enables reproduction |
| subject, scope, time_window, captured_at, assessed_at | What was checked, and when |
| claims[] | Stable atom IDs, **verbatim** original text, claimant, published date, original/archive links |
| evidence[] | Stable ID, source URL/capture, type, independence group, access limits, what it actually supports |
| assessments[] | Per-claim verdict from STANDARD.md, rationale, citing evidence IDs, material contrary IDs, open questions |
| relations[] | Explicit versus inferred relationship, with specific support and limits |
| limitations[] | Scope limits, missing or inaccessible sources, unresolved conflicts, methodology assumptions |
| contradiction_pass | Search performed for evidence against each material thesis; outcome including null findings |
| revision_log[] | Prior versions, dated errata, withdrawals and reasons; append-only semantics |
| editorial_gate | Draft/review/approved/published state and human approval provenance |
| source_sensitivity | Safe-to-publish flags and redaction rules, applied **before** export or renderer access |

A renderer may receive **only a publication-safe projection** after appropriate review. It must not see credentials, private witness identities, unapproved excerpts, or restricted source data. Do not interpret absence of a restricted source as lack of evidence; explain the publication limitation accurately.

Every presentation includes a visible provenance pointer: record version, last assessment date, link to the authoritative record (where publishable), and method/corrections access.

## Minimum display contract for every depth

All depths communicate:
1. **What was claimed** — exact or clearly linked full wording with scope/time; never rewrite into a stronger claim.
2. **What the evidence supports** — not a stronger headline than the underlying verdict.
3. **Why** — relevant source links attached to the factual statements they support.
4. **What argues against or limits it** — material contradictory evidence and unresolved gaps, not hidden only in expert mode.
5. **When and by whom it was reviewed** — dates and editorial status; no draft framed as an approved finding.
6. **How to challenge or go deeper** — stable anchors/links to claims, original sources, methods, and dated corrections.

If key evidence is unavailable or cannot be safely disclosed, say so. If sources cannot be fetched, show the archived/snapshot status; do not substitute fabricated links.

### View behaviors

**Simple:** short summary, accessible wording, sources inline, material caveat visible, progressive disclosure to underlying claim/evidence. Never claim more certainty than expert.

**Explore:** summary plus structured how/why, timeline/context as available, source independence, alternatives and questions, linked navigation.

**Expert:** detailed atom table, unedited claim wording, citations and capture metadata, source-group graph, verdict rationale, counterevidence, falsification log, limitations, deltas, reproducible export.

**Representation** is independent of depth. Avoid diagrams when data does not justify them; avoid visuals that exaggerate apparent causal relationships. No inferred edge should be styled as an explicitly sourced relationship.

### Language and editorial constraints

- Output may simplify vocabulary; it may **not** simplify away uncertainty.
- Label fact, testimony, inference, hypothesis, and unknown consistently.
- Use neutral, non-persuasive language: do not tailor conclusions to a reader's presumed politics or beliefs.
- If a standard verdict is pending, show **not yet assessed**, not an improvised "likely true" score.
- "Self-reported only" is an evidence-source state, not proof a claimant lied.
- "Unverifiable by design" is not an automatic finding of intent to deceive.
- Avoid false precision, unearned likelihood estimates, and decorative confidence bars.
- AI-written explanations and StoryTeller-guided paths are **presentation**, never additional evidence.

## Output manifest and auditability

Each view/export should carry:
- source investigation ID/version/hash;
- depth and representation;
- renderer/adapter version;
- referenced claim IDs and evidence IDs;
- factual statements and their evidence bindings;
- which details were condensed and where to retrieve them;
- gate status, publication timestamp, public-safe omissions/redactions;
- correction-record URL and challenge route.

The adapter should report an error rather than silently emit a degraded representation. Deliberate, clearly labelled partial output may be acceptable only with an explanation of what is missing.

## StoryTeller integration boundary

Claim Checker -> approved public-safe evidence projection -> **read-only adapter** -> StoryTeller story schema -> renderer.

StoryTeller's existing cited nodes and explicit/inferred edges are promising, but the schema is **not yet a complete match** for verdicts, contradictory evidence, editorial state, source independence groups, redactions, or amendment history. Preserve these in a lossless contract (schema extension or companion manifest), never drop them in conversion. StoryTeller's guided narratives cannot advocate beyond the evidence-supported finding.

Do not change Claim Checker's authoritative findings to accommodate StoryTeller's schema or aesthetics.

## Acceptance / test matrix

Build one fully synthetic fixture (clearly marked synthetic) with an unverified numerical claim, two derivative articles copied from one source, one primary contradiction, uncertainty, and a dated correction.

- **Identity:** every view/export points to the same investigation version/hash.
- **Consistency:** findings, scope, and evidentiary status agree across all depth + representation combinations.
- **Counterevidence:** contrary source and material caveat remain visible in simple mode.
- **Citation integrity:** each material assertion opens a correct fixture source; no invented URLs; every claim/evidence ID resolves.
- **Independence:** derivative articles never become multiple corroborations.
- **Inference:** hypothesized graph edges remain labelled as inferred.
- **Corrections:** dated updates are displayed without silently replacing original wording.
- **Gate/privacy:** drafts cannot appear published; private data cannot leak into client JSON, HTML, exports, or indexes.
- **Accessibility:** mobile, keyboard-only, screen-reader, contrast, print/export, and focus persistence during depth changes.
- **Human validation:** ordinary readers and journalists identify the same finding, contradictions, limits, and sources.

Reject the build if simple and expert presentations could reasonably leave competent readers with materially incompatible conclusions.

## Implementation order

1. Map existing STANDARD.md records into a versioned evidence projection; document unknowns.
2. Build synthetic fixture, publication-safe transform, and contract validator.
3. Implement simple/explore/expert switching with preserved deep links.
4. Build StoryTeller adapter and/or companion manifest; prove provenance integrity.
5. Implement cross-view consistency, privacy, citation, and accessibility tests.
6. Conduct usability review with ordinary readers and working journalists **before** adding more automated research.

This specification does not claim the feature is built. Issues should track implementation and evidence of passing tests.
