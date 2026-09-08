---
name: Sync API Docs from AI Presentations
description: Updates documentation when a release ships in the AI Presentations repo
on:
  push:
    - repo: Demand-IQ/ai-presentations-demo
      branch: main
automerge: true
---

When this workflow triggers, review the changes pushed to `Demand-IQ/ai-presentations-demo` on the `main` branch.

## When to act

Documentation tracks the **released** API surface, not in-flight work on `main`. Releases are cut as `release/X.Y.Z` branches and merged back, so each release arrives on `main` as a merge commit.

Only proceed when the pushed changes contain a release merge — a commit whose subject matches `Release: X.Y.Z`, or a merge of a `release/X.Y.Z` or `chore/release-X.Y.Z` branch. If the push contains no such commit, stop without changing anything, even when API routes changed.

When a release merge is present, document the API surface as of that release, covering every API change that landed on `main` since the previous release merge — not just the changes in the triggering push.

## Instructions

1. Look at what changed in the API routes (typically under `app/api/` or `pages/api/`).
2. If new endpoints were added, ensure they are reflected in `openapi.json` and that any relevant guide pages reference them.
3. If existing endpoints changed (new parameters, updated responses, renamed routes), update any narrative documentation that references those endpoints.
4. If endpoints were removed, remove or update any docs that referenced them.
5. Keep all writing consistent with the style guidelines in `.mintlify/AGENTS.md`.
6. Do not rewrite pages that are unaffected by the code changes.

## Scope

Only generate documentation for **AI Presentations**. Do not create documentation for Journeys, even when Journeys-related code is added or changed in `Demand-IQ/ai-presentations-demo`. Specifically:

- Do not create or restore any Journeys pages or a Journeys navigation tab.
- Do not document Journeys-specific endpoints, including `POST /api/decks/{deckId}/ingest` (journey ingest). Never add them to `openapi.json`, and do not create pages for them.

This exclusion is about standalone Journeys documentation. AI Presentations features that integrate with journeys (for example, journey-backed product slides) are still in scope and should be documented as part of AI Presentations.
