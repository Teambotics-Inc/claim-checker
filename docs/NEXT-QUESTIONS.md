# Claim Checker — the Next Questions step

**Origin:** Added 2026-11-13, at the direction of the desk's publisher, on completion of the Ground News audit: once the agent has conducted the research, the agent itself should produce the list of questions and next tasks worth digging into — the user shouldn't have to invent the follow-ups cold, because the agent is the one holding the built context. The user picks; the agent digs from warm context.

**Status:** A standard step of the method (see `docs/STANDARD.md`, *Next questions*). First dogfood: the Ground News audit's Round 2 question set, produced with its launch case study.

## The rule

Every audit ships with a **Next Questions** section, produced by the generating agent after the audit *and* after the independent (validator) check. It is a standard output, not an optional extra. An audit without one is incomplete in the same way an audit without a contradiction pass is incomplete. In the audit's StoryTeller presentation, the final guided path ends on these open questions.

## Why (the reasoning, so future agents don't cargo-cult it)

- The audit's failures and flags are a map: generator-capture-only items, unresolved leads, verdicts resting on one source, counterparties never heard, claims that are unverifiable *as currently framed* but might become verifiable with a different instrument (a records request, a product-in-hand test, a live experiment).
- The user cannot see that map as clearly as the agent can at the end of a run — they would have to re-read the whole ledger to invent questions the agent already knows.
- Context is perishable and expensive to rebuild. A question picked from the list starts from the audit's context, not from zero. That is the compounding advantage of the desk.

## What each question must carry

1. **The question, as a question** — something that could actually be asked, of a source, a dataset, or the subject itself.
2. **Provenance** — which claim, flag, validator exception, or contradiction-pass item it grows from. No provenance, no place on the list. Generic curiosity ("look into their marketing") is not a Next Question.
3. **What's already known** — the evidence in hand, so the dig is visibly an increment, not a restart.
4. **What the dig needs** — sources, access, captures, money, or an external send (and whose approval that send needs).
5. **What could move** — which verdicts could change, which new claims could open, or which loop could close (e.g. an accountability experiment whose result *is* the evidence).

## Ranking and shape

- Group by thread (money, product-in-hand, method, people, accountability), rank within and across threads by expected yield against cost.
- Lead with the questions whose answers would most change the audit's verdicts or its one-line finding.
- Cheap unblocking questions (re-captures of flagged items) are ranked visibly even when unglamorous — they are what makes the audit publishable.
- Label any question that requires contacting the subject or a third party. Those are proposals, not tasks; they execute only on the user's word, under the standing send rules.

## Interaction

The list is presented to the user as a menu in chat. The user's pick is the authorisation for that dig. Unpicked questions stay on file with the audit — they are part of its longitudinal record, and a later run (or a challenger) can pick them up. When a Round 2 dig completes, it produces its own Next Questions in turn.
