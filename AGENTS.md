# AGENTS.md

Guidance for AI coding agents working in this repository. `README.md` explains the opt-out link flow
in full; read it first.

## What this is

A minimal **example** opt-out confirmation page that Optimove customers can copy and self-host
(e.g. with their own branding) instead of using the Optimove-hosted default page. It is not deployed
from this repo. **This repository is public**: anything committed here is visible to everyone.

## Layout

```
src/index.html   the whole example: markup plus inline JS (loadHandler, clickHandler)
README.md        customer-facing explanation of the slug / confirm=1 round trip
```

## Running

No build, dependencies or tests. Open `src/index.html` via `file://` with `?slug=abcd1234` (confirm
prompt) or `?confirm=1` (opted-out message).

## Things to know

- The flow is a contract with the opt-out service: the page receives `?slug=<slug>`, sends the user
  to `https://optouttxt.net/<slug>?confirm=1`, and is redirected back with `?confirm=1`. Keep the
  README and the code in sync if either changes.
- Clicking "Confirm Opt Out" calls the real opt-out service; never do it with a real slug.
- Keep the example simple and well commented: it is documentation for customers. Do not add
  frameworks, build steps, internal hostnames, dev URLs or any internal links.

## Git

- Default and base branch is `main` (there is no `dev`); open PRs against `main`. No CI or deploy
  workflow is configured.
