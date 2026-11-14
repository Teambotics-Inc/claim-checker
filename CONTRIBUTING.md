# Contributing to Claim Checker

**You do not need to know Git to contribute.** Most contributions here are claims, evidence, corrections, and questions — not code.

You also do not need the desk to run a check. Claim Checker is a method with agent instructions: point your own AI agent at this repository (start with `AGENTS.md`) and it will run the Standard for you. The doors below are for contributing to the shared record — the desk's case studies, corrections to published audits, and subjects for future audits.

## The four doors

Use the issue forms — they ask exactly what an audit needs:

1. **Submit a claim to audit** — a claim-maker said something checkable, in public: a company, a fund, a public figure, an individual. Give us the claim verbatim and where it appeared.
2. **Send evidence or a correction** — documents, links, screenshots, first-party records. Evidence *against* our published findings is especially welcome.
3. **Suggest a subject** — nominate the next audit subject (any claim-maker, not only companies), and say why.
4. **Challenge an audit** — every published audit ends with a link to this form, pre-filled with the audit ID. Challenges are appended to the audit as dated errata. Audits are never silently edited.

No GitHub account? The desk also takes submissions by email (see FEEDBACK.md); they are transcribed into issues with the source noted, so nothing depends on which door you used.

Open-ended discussion lives in **Discussions** — ideas, methods, arguments. It is deliberately kept out of the evidence pipeline: evidence enters through the forms, where it gets a record, a verdict path, and a receipt.

## Sending evidence that cannot carry your name

Some evidence cannot safely be attached to a person. If that is your situation:

- Say so in your submission, and give the reason (safety, livelihood, legal exposure) — the reason is recorded; your identity is not published.
- The desk must be able to satisfy itself of who you are and how you know what you claim, even where readers never will. Material whose source is unknown to the desk is not evidence.
- Anonymous material corroborates; it never carries a verdict alone, and confidential material is published only in its least identifying form (see the Standard's *Anonymous and confidential sources* rules).

## If you do write code

Claim Checker descends from Moat Observer's architecture: an evidence store of atomic claim records, an independence-grouping layer for sources, a contradiction engine, and a report gate that blocks narrative until the research exists. Issues labelled `agent` and `schema` are the current build frontier. Pull requests should cite the audit or schema issue they serve.

## Ground rules for everyone

- Quote claims verbatim. Paraphrase is where claims go to become unfalsifiable.
- Label what you know: witnessed it, read it, inferred it, or heard it. We keep those separate; please don't blend them on the way in.
- No doxxing, no private data about individuals. Public claims are the subject — whoever made them; private lives are not.
- Declare your interest. If you have a relationship with a subject you are submitting claims or evidence about — employee, investor, competitor, or a personal dispute — say so in the submission. Declared interests are recorded, not punished; undeclared ones undermine the record.
- Corrections beat pride. If you were wrong in a submission, say so in the thread — it makes the record stronger, and it is the whole ethic of this place.
