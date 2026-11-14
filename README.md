# Claim Checker

**An open, auditable claim-verification method — built for journalists, usable by anyone with an AI agent.**

Claims get published every day — user counts, money "introduced," revenue run-rates, partnership announcements, fundraising stories — by companies, funds, public figures, and individuals. Almost nobody checks them. Claim Checker is a method, and the agent instructions that run it, for checking a public claim against what the record actually supports.

## Use it: point your agent at this repo

You do not send claims to a desk and wait. **You run it yourself:**

1. Give any capable AI agent this repository and a claim to check — *"Follow `AGENTS.md` in this repo and check this claim: …"*
2. Your agent reads the method in [`docs/STANDARD.md`](docs/STANDARD.md), captures the claim verbatim, researches it against the public record, runs the eight-test battery and a contradiction pass, and hands you back an audit with citations.
3. Every verdict carries its sources, so you can open them and judge for yourself. The output is produced by *your* agent; the human who publishes it answers for it. That is the design, not a caveat — see the AI-provenance rule in the Standard.

## What an audit looks like

Every audit Claim Checker's method produces is:

- **Evidence before narrative** — claims are atomic records with provenance, captured verbatim, before any analysis is written.
- **Independence-grouped** — fourteen outlets rewriting one press release count as one source, not fourteen corroborations.
- **Contradiction-tested** — every material thesis gets a dedicated falsification pass.
- **Verdict-honest** — each claim resolves to exactly one of *confirmed*, *partially corroborated*, *self-reported only*, *unverifiable by design*, or *contradicted*. "We could not verify this" is a publishable result, never a gap to be smoothed over.
- **Checked by someone who didn't produce it** — generator ≠ validator is structural: an independent agent or human re-checks the verdicts before the audit is treated as checked, and the audit says on its face who reviewed it — or that nobody did.
- **Fair before publication** — the subject sees the verbatim claims and draft verdicts and gets a window to respond, before anything is published; the response runs in the audit.
- **Longitudinal** — audits are never overwritten. Updates produce "What Changed?" deltas, so claims are tracked over time, not summarised once and forgotten.
- **Score-free** — no universal hype score. Precision without methodology is the disease, not the cure.

## Presentation: StoryTeller is the default output

The audit ledger is the evidence record. Its default **presentation** is a **[StoryTeller](https://github.com/Teambotics-Inc/StoryTeller)** story: one self-contained, explorable HTML file — a sourced graph of the claims, verdicts, and evidence, with contradictions shown standing side by side, inferences drawn dashed, and open leads left visibly open. Following `AGENTS.md` here will instruct your agent to build one for every audit, following StoryTeller's own `AGENTS.md`. The rules binding every presentation to the ledger are in [`docs/OUTPUT-CONTRACT.md`](docs/OUTPUT-CONTRACT.md).

## Next Questions: the audit ends with a map

Every audit closes with **Next Questions** — the generating agent's ranked list of follow-up questions and next digs, each tied to a claim, flag, or unresolved lead in that audit. You pick where to dig; the agent continues from the context the audit already built. Spec: [`docs/NEXT-QUESTIONS.md`](docs/NEXT-QUESTIONS.md).

## Optional: the story in minutes (Gemini Notebook)

Proof and storytelling are different jobs. The ledger is the proof; the StoryTeller story is its navigable presentation. If you have **Gemini Notebook (NotebookLM)**, your agent can also assemble an optional **Notebook pack** from the audit — the ledger, the story record, a timeline document, and the audit's key source links — from which Notebook generates short video or audio explainers and answers cited questions about the pack in chat. It's how you grasp the story in minutes and get ideas for telling it; anyone who wants to challenge the story still digs in the ledger, where the citations live. Notebook output is never evidence, the method never depends on it, and the offer happens once, at hand-back. Spec: [`docs/NOTEBOOK-PACK.md`](docs/NOTEBOOK-PACK.md).

## Case studies (launch dogfoods)

Worked examples of the method, run by TeamBotics with its own agents, each delivered as an audit ledger plus its StoryTeller presentation:

- **Paradox (Front Door)** — a large-scale audit of public claims made by employers about their application front doors, tested against what the record supported. *[Forthcoming at launch]*
- **Ground News** — an audit of a news-aggregation company's claims about its own scale, funding, and rating methodology — including where its own pages contradict its methodology page. *[Forthcoming at launch]*

Case studies are examples of the product in use. They are not findings your agent inherits; it runs its own check.

## You do not need to know Git to contribute

Most contributions here are not code. They are claims, evidence, corrections, and questions — and they arrive through the issue forms:

- **Submit a claim to audit** — someone said a number, in public. Send it.
- **Send evidence or a correction** — including evidence against our own findings. Especially that.
- **Suggest a subject** — nominate the next audit.
- **Challenge an audit** — every published audit links a correction form pre-filled with its ID. Corrections are appended as a dated errata log; audits are never silently edited.

See [CONTRIBUTING.md](CONTRIBUTING.md) and [FEEDBACK.md](FEEDBACK.md). The developer path is in there too — it just comes second, on purpose.

## The method

The Standard, the audit battery, and the evidence rules live in [`docs/`](docs/), along with the [journalism direction](docs/JOURNALISM-DIRECTION.md) and the [output contract](docs/OUTPUT-CONTRACT.md). Who runs the desk, who holds editorial control, and how the desk is funded: [`docs/FUNDING-AND-ORGANISATION.md`](docs/FUNDING-AND-ORGANISATION.md). The system's analytical spine descends from Moat Observer, an auditable competitive-intelligence research agent: same evidence store, same contradiction engine, same refusal to manufacture precision — aimed at claims instead of moats.

## Status

Claim Checker is free to use and free to challenge, permanently. Audits produced with this method by anyone other than the desk are those producers' own work: check the AI-provenance block on any audit to see which agent produced it, which method version it used, and which human reviewed it.
