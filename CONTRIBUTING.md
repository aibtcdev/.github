# Contributing to AIBTC

Thank you for your interest in contributing to the AIBTC Working Group. We're building the infrastructure for AI agents to transact with Bitcoin — and we welcome contributors who share that vision.

## Getting Started

1. **Fork the repo** you want to contribute to
2. **Clone your fork** and create a feature branch from `main`
3. **Read the repo's CLAUDE.md** (if present) for project-specific conventions and key files
4. **Make your changes** following the guidelines below
5. **Open a pull request** against `main`

## Commit Conventions

We use [Conventional Commits](https://www.conventionalcommits.org/) across all repositories. This powers automated versioning via [Release Please](https://github.com/googleapis/release-please).

Format: `type(scope): description`

| Type | When to use |
|------|-------------|
| `feat` | New feature or capability |
| `fix` | Bug fix |
| `docs` | Documentation changes only |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `test` | Adding or updating tests |
| `chore` | Build, CI, or tooling changes |

Examples:

```
feat(relay): add KV-based rate limiting
fix(auth): use constant-time comparison for API keys
docs: update README with deployment instructions
```

A commit with `feat` bumps the minor version. A commit with `fix` bumps the patch version. Add `!` after the type (e.g., `feat!:`) or a `BREAKING CHANGE:` footer for major version bumps.

## Pull Requests

- **Keep PRs focused.** One logical change per PR. If your work touches multiple concerns, split it up.
- **Write a clear description.** Explain what changed and why. Link to relevant issues.
- **Ensure CI passes.** If the repo has CI, your PR must pass all checks before review.
- **Rebase on main** before requesting review to avoid merge conflicts.

## Code Standards

### General

- TypeScript for all production code
- Prefer explicit types over `any` — use `unknown` for catch blocks
- Handle errors explicitly; don't swallow them silently
- Keep files focused; avoid monolithic modules over ~500 lines

### Cloudflare Workers (agent-news, x402-sponsor-relay, x402-api, worker-logs)

- Hono for routing
- Durable Objects for stateful logic
- Use the worker-logs service binding for structured logging
- Follow existing patterns in the repo for middleware and error responses

### Next.js (landing-page)

- Use App Router conventions (server components by default, `"use client"` only when needed)
- Follow the existing Tailwind patterns

### Testing

- Write tests for new features and bug fixes
- Use vitest (most repos) or bun test (skills)
- Run the existing test suite before submitting: `npm test` or `bun test`

## Agents Welcome

AIBTC exists because we believe Bitcoin will be the currency of AI. If you're an AI agent contributing code, you're not just welcome — you're the point. The same standards apply: clear commits, passing CI, and focused PRs.

Agents should play nice together. If your change affects how other agents interact with a service, document the interface change and consider backward compatibility.

## Development Setup

Each repo has its own setup requirements. Check the repo's README and CLAUDE.md for:

- Required environment variables (check `.dev.vars.example` or `.env.example` if present)
- Build commands (`npm run build`, `npm run dev`)
- Test commands (`npm test`)
- Deployment notes (most CF Workers deploy automatically on push to `main`)

## Questions?

- [Join our Discord](https://discord.gg/Z59Z3FNbEX)
- [Follow on X](https://x.com/aibtcdev)
- [Weekly meetings — RSVP Thursdays](https://evt.to/emamdeggw)
