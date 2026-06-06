# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

This repository is in its very earliest stages. It currently contains only:
- `README.md` — a one-line title (`# lunodynamics`)
- `backend/app.js` — a minimal Express server skeleton

There is **no `package.json`** anywhere in the repo yet, so dependencies (e.g. `express`, which `backend/app.js` requires) are not declared or installed, and there are no npm scripts, build step, linter, or test suite. Running `node backend/app.js` as-is will fail with a "Cannot find module 'express'" error until a `package.json` is added and `npm install` is run.

## Current architecture

`backend/app.js` is the entire application:
```js
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;
app.listen(PORT, () => { ... });
```
It creates an Express app and starts it listening on `process.env.PORT` (defaulting to `3000`). No routes, middleware, or other modules exist yet.

## Working in this repo

- Before adding code that depends on a package (Express or otherwise), set up a `package.json` (`npm init`) and install the dependency — don't assume it's already available.
- Since the codebase is essentially a blank slate, prefer establishing simple, conventional structure (e.g. a standard Express layout under `backend/`) over speculative abstractions. Build out only what's asked for.
- Update this file as real build/lint/test/run commands and architectural patterns are introduced, since none exist to document yet.
