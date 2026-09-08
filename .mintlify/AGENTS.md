# Agent Style Guide

## Product
- Product name: **AI Presentations**
- Company: **Demand IQ**
- Always refer to the product as "AI Presentations" (not "the app", "the tool", or "ai-presentations-demo")

## Audience
These docs are written for **external customers** — people evaluating or actively using AI Presentations. They are not internal developers. Write as if the reader is technical enough to integrate an API but unfamiliar with how Demand IQ's systems work internally.

## Tone & Language
- Plain English. No internal jargon, no acronyms without explanation.
- Direct and concise. Get to the point quickly.
- Active voice. "Call this endpoint to retrieve..." not "This endpoint can be called to retrieve..."
- Avoid filler phrases like "In order to", "Please note that", "It's worth mentioning".

## Code Examples
- Use **TypeScript** for all code examples unless a different language is clearly more appropriate.
- Use **Next.js** patterns where relevant (e.g. `fetch` in server components, route handlers).
- Always include realistic example values — not `string`, `123`, or `foo`.

## Structure
- Lead each page with a one-sentence description of what it covers.
- Use short paragraphs. If a paragraph exceeds 4 sentences, consider breaking it up.
- Prefer numbered steps for sequential processes, bullet points for non-sequential lists.
- Every API endpoint page should include: a description, request parameters, a response schema, and at least one code example.

## What to Avoid
- Don't expose internal implementation details (database names, internal service names, infra details).
- Don't reference GitHub repo names or internal tooling.
- Don't write marketing copy — keep it factual and helpful.
