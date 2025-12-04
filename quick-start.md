# Quick Start: AI-FDD in Practice

This guide shows how to apply the AI Feature-Driven Development design theory from [README.md](README.md) with an AI coding agent.

## 1) Set Up the Agent
- Load [AGENTS.md](AGENTS.md) into your AI assistant so it automatically pulls [feature-driven-development-rules.md](feature-driven-development-rules.md).
- The agent should begin every session with: `I am your feature-driven code developer`.
- Keep [BEST_PRACTICES.md](BEST_PRACTICES.md) handy for incremental, verifiable delivery.

## 2) Run the Feature Loop
1. Clarify intent in user terms only (no architecture, no APIs).
2. Trigger a command:
   - `task xxx`: read `instructions/xxx.md`, refine, propose `features/yyy-zzz.md` for approval.
   - `complete yyy-zzz`: implement from an existing feature spec.
   - `refer yyy-zzz`: recall the feature and its docs/APIs before new work.
   - `review yyy-zzz`: audit code against the spec and docs.
   - `search xxx`: when external knowledge is needed.
   - `do`: act on the currently opened markdown file (interpreted as `task` or `complete`).
3. After approval, implement one Atom Feature at a time and deliver code plus minimal docs.
4. Update `features/docs/yyy-zzz.md` and `features/apis/yyy-zzz.md` after review is accepted.

## 3) Keep Features Atomic
- Scope for a single AI pass and a 2–3 minute human review.
- Write outcomes only: what the user experiences, not how to build it.
- Name features as reusable index entries (avoid verbs like add/update/fix).

## 4) Maintain the Index
- Keep `features/readme.md` concise but current so the AI can load the right slices.
- When fixing or enhancing code, sync the matching `features/*.md`, `features/docs/*.md`, and `features/apis/*.md`.
- Avoid external references; include the needed context directly in the feature docs.

## 5) Flow Reminders
- Start small, ship fast: intent → AI build → human review → next slice.
- Architecture emerges from consistent feature intent; resist upfront design bloat.
- If context is large, load only the relevant feature files as an index for the AI.

With this loop, the AI handles the building while you steer the product through crisp feature intent and rapid review.
