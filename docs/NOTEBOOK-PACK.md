# Claim Checker — the Notebook pack (optional layer)

**Status:** An optional output of the method, offered once at hand-back (see `AGENTS.md`, Step 11). It is **not** part of the audit, not a step of the Standard, and never a dependency: an audit is complete without it. First specified 2026-11-13, against the Gemini Notebook (NotebookLM) product as surveyed live that day.

## The idea: proof and storytelling are different jobs

A Claim Checker audit produces proof: the ledger, where every verdict carries its citations, and the StoryTeller story, the navigable graph a challenger can dig through. Proof is built for scrutiny, not for speed — it takes time to absorb, and most people will never read a ledger cold.

**Gemini Notebook (NotebookLM)** is a third-party service that generates explainers from a set of sources a user gives it: short and long video overviews, audio overviews, briefing documents. That is the storytelling layer. Fed the audit's own materials, it lets the user grasp the story in minutes, hear how it sounds told aloud, and get ideas for how they want to present it — while the proof stays where it belongs, in the ledger and the story graph, one link away for anyone who comes digging.

Four layers, four jobs:

| Layer | Job |
|---|---|
| The ledger | The proof. The citable record. |
| The StoryTeller story | The navigable graph and timeline — for readers and challengers. |
| The Notebook pack | The story in minutes — video/audio explainers and cited chat over the audit's own materials. |
| The Next Questions | The map of what to dig next. |

## When the offer happens

Once, at **hand-back**, after the StoryTeller step and the Next Questions have been delivered. One line, no nagging, no menu of options. If the user declines — or doesn't answer it — skip it silently and finish the hand-back as normal. Never offer it mid-audit, and never let it delay the ledger, the story, or the Next Questions.

### The offer wording

Use this, close to word for word:

> If you have Gemini Notebook (NotebookLM), I can prepare a Notebook pack from this audit — the ledger, the story record, the timeline and the source links — so you can generate a short video or audio explainer and ask cited questions about the pack. Want me to build it?

With the offer, in the same message, one line of disclosure:

> Notebook is a third-party service (Google's); anything added there is subject to its terms, and generation runs on your own account and its limits.

Build the pack only if the user says yes.

## The pack

A folder named `notebook-pack/`, assembled from the audit's own materials — assembly, not new research. Every file is Markdown (Notebook accepts `.md` uploads natively). Each file stays far below Notebook's per-source limit of 500,000 words in any realistic audit; if a ledger ever approached that limit, split it by claim range into numbered parts and note the split in `SOURCES.md`.

| File | Contents |
|---|---|
| `00-audit-ledger.md` | The audit ledger itself, complete: verbatim claims, verdicts, evidence with citations, the eight-test battery, the contradiction-pass log, the reply record, the conflict declaration, the limits. Carries the disclaimer and the AI-provenance block, exactly as stamped on the audit. This is the pack's anchor source. |
| `01-verdicts-and-claims.md` | A quick-reference table generated from the ledger: one row per atomic claim — claim (short label plus where it was made), verdict, and the strongest source for that verdict. Nothing in this file may state a finding more strongly than its verdict in the ledger. |
| `02-story-record.md` | The StoryTeller story's research record (`research.md` from the story build): the sourced narrative base behind the graph — facts, disagreements, and open leads, with their sources. |
| `03-timeline.md` | A dated chronology generated from the audit and the story record: every dated event in order — claims made, records created, replies received, corrections issued — each with its source. **Notebook has no timeline output**, so the timeline travels as a document in the pack; the interactive timeline remains StoryTeller's. Do not invent dates to fill gaps; a gap is stated as a gap. |
| `04-next-questions.md` | The audit's Next Questions, as delivered. |
| `05-reply-and-corrections.md` | The subject's reply in full (as published in the audit) plus any errata appended since. **Include only when a reply or errata exist.** When neither exists, omit the file and note the omission at the top of `SOURCES.md` ("No 05 file: the subject has not replied and no errata have been issued as of <date>"). |
| `SOURCES.md` | The link manifest (below). Not itself a Notebook source — it is the instruction sheet for adding the link sources, and the record of what went in. |

### SOURCES.md — the URL manifest

Notebook accepts website links as sources and fetches them itself, so primary sources join the pack as URLs rather than copies. List them in this order:

1. **The subject's own claim pages first** — the pages where the checked claims were made, in the form the audit cited them.
2. **Primary records** — registries, filings, official pages, the record-keepers' own publications.
3. **Key independent reporting** — only reporting the audit actually relied on, independence-grouped as in the ledger (fourteen outlets rewriting one release are still one source; list the strongest, not all fourteen).

For each URL: the URL, a one-line description of what it is, and which claim(s) it bears on. **Cap guidance: roughly 40 URLs.** The pack's own files (5–6) plus ~40 links stays under the free tier's 50-source limit per notebook (paid tiers allow more — 100 on Plus — but design to the free cap so the pack works for anyone). If the audit relied on more than ~40 link-worthy sources, the ledger and story record already carry the rest as citations; the manifest takes the load-bearing ones, in the order above.

## Delivery: two modes

Notebook has **no API or developer access**. The pack reaches a notebook in exactly two ways:

### Mode A — Agent-assisted (a browser-capable agent, user present and directing)

Use only when the agent genuinely has browser control and the user is present and directing the session — this is the user's own Google account. The agent:

1. Creates a new notebook and names it **`<Subject> — Claim Checker audit <date>`** (the audit's assessment date).
2. Uploads the pack files (`00`–`05` as present) from `notebook-pack/`.
3. Adds each URL in `SOURCES.md`, in manifest order, as a website link source.
4. Confirms the source count back to the user (files + links) and stops there. Generating explainers is the user's call, in the session or later — the recipes below are left with the user either way.

The agent never asks for, receives, or stores the user's Google credentials. If the session is not already signed in, the user signs in themselves.

### Mode B — Hand-off (the default)

The agent delivers the `notebook-pack/` folder plus these exact steps, and the user (or their own assistant, human or agent) does the adding:

1. Open Gemini Notebook (NotebookLM) and create a new notebook.
2. Name it **`<Subject> — Claim Checker audit <date>`**.
3. Add sources → upload the files from `notebook-pack/` (`00` through `05`, whichever are present).
4. Add sources → website link: paste each URL from `SOURCES.md`, in order, one at a time.
5. Check the source count shown in the notebook against your plan's per-notebook limit (50 sources on the free tier) — the pack is sized to fit, but if you add sources of your own, count again.
6. Use the Studio recipes below to generate your explainers.

## Studio recipes

Copy-ready. Steering text is written to be pasted as-is; replace the bracketed parts from the audit before handing them over. Generation runs on the user's account and its usage limits; video generation in particular can take a long while (30+ minutes was normal when this was surveyed) — it can be left running.

*Where the steering text goes (verified in the product, 2026-11-13):* in the Video Overview dialog, under "What should the video focus on?", choose **Custom topic** and paste the steering note into the text box that appears; the Audio Overview takes its steering as producer notes. Both dialogs also let the user choose **which sources** a generation uses (all are selected by default) — the recipes below assume the full pack; if a recipe names a narrower focus, say which sources to leave selected.

### Video Overview — Explainer (the main explainer)

Format: **Explainer**. Steering note:

> Audience: [who this is for — e.g. "a journalist deciding whether this story holds up"]. The one-sentence finding of this audit is: [the audit's one-line finding, verbatim from the ledger]. Walk the claims in the order the verdicts table presents them. Use the verdict words exactly as written — Confirmed, Partially corroborated, Self-reported only, Unverifiable by design, Contradicted — and do not soften or strengthen any verdict. Where sources disagree, present the disagreement; do not resolve it. End with what remains open: the Next Questions.

### Video Overview — Short (the shareable one)

Format: **Short** (about 60 seconds). Steering note:

> The one-sentence finding is: [verbatim]. State it, give the single strongest piece of evidence for it, state the verdict tally exactly ([n] Confirmed, [n] Partially corroborated, [n] Self-reported only, [n] Unverifiable by design, [n] Contradicted), and close by pointing viewers to the full audit — the proof is in the ledger, not in this video.

### Audio Overview — Deep Dive (the briefing)

Format: **Deep Dive**, with producer notes:

> Treat this as a briefing for [a journalist / the user] who is about to work with this audit. Role: two hosts walking a colleague through what was checked. Focus: the claims, the verdicts and the strongest evidence for each, where the subject's own record disagrees with itself, what the subject said when given the chance to reply, and what is still open. Keep every verdict exact. Do not speculate beyond the sources; where the record has a gap, name the gap.

### Report — Briefing Doc

Generate a **Briefing Doc** report from the pack. It drafts itself from the sources; the user's job is to check it against `01-verdicts-and-claims.md` before using it for anything — a briefing that drifts from the verdict table is a draft with an error in it, not a summary.

### Chat starter questions

Notebook's chat answers carry **inline citations** to the pack's sources, with the cited text openable — this is the pack's interrogation layer, and the place where Notebook output *is* checkable on the spot. Suggest these three:

1. "Which claims are Contradicted, and what is the single strongest source for each?"
2. "Which verdicts rest only on the subject's own statements, and what independent record would settle each one?"
3. "What did the subject say in reply, what did the reply change, and which questions are still open?"

## Guardrails

1. **Public claims only — the pack contains audit materials about public claims, and nothing else.** No private data, ever: no contact details, no material the user supplied privately unless it is already part of the audit record, nothing from outside the audit's scope.
2. **Notebook outputs are derivative views, never evidence.** Generated video, audio and reports carry no verified per-claim citations (only chat answers carry inline citations, verified at survey time). Never cite a Notebook output as evidence for anything. The ledger is the citable record; the StoryTeller story is its presentation.
3. **Published explainers point at the proof.** If the user publishes a generated video or audio explainer anywhere, it should link the audit ledger (and the StoryTeller story where one is published) so a challenger can reach the citations. The explainer is the story told short; the link is how it stays honest.
4. **Corrections make packs stale.** If the audit is corrected or a reply arrives after the pack was built, the pack no longer matches the record. Rebuild the affected files (and say which changed) — the same reach rule that governs corrections everywhere else in this method applies here: a stale pack circulating as the story is a corrections failure, not a convenience.
5. **The user's account, the user's call.** Generation happens on the user's own Gemini Notebook account and subscription, under its limits and terms. The method neither requires nor provides access, and nothing in the method changes if the user has no account at all.
6. **Verdicts travel exact.** Every recipe and steering note in this spec exists to stop generated narration from drifting stronger or softer than the ledger. If the user edits a steering note, the verdict vocabulary and the one-line finding are the parts that must not move.
