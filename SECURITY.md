# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in any AIBTC repository, **please report it responsibly**. Do not open a public issue.

**Email**: security@aibtc.com

Include:
- Which repository and file(s) are affected
- A description of the vulnerability and its potential impact
- Steps to reproduce (if applicable)
- Suggested fix (if you have one)

## Response Timeline

| Step | Target |
|------|--------|
| Acknowledgment | Within 48 hours |
| Initial assessment | Within 1 week |
| Fix or mitigation | Depends on severity (see below) |
| Public disclosure | After fix is deployed |

## Severity Levels

| Severity | Examples | Response |
|----------|----------|----------|
| **Critical** | Private key exposure, unauthorized fund transfers, authentication bypass | Immediate fix, deploy within 24 hours |
| **High** | Timing attacks on auth, plaintext secret storage, rate limiter bypass | Fix within 1 week |
| **Medium** | Missing input validation, overly permissive CORS, type safety gaps | Fix in next release cycle |
| **Low** | Missing security headers, informational leaks in error messages | Tracked and addressed when feasible |

## Scope

This policy covers all repositories under the [aibtcdev](https://github.com/aibtcdev) GitHub organization, including but not limited to:

- **x402-sponsor-relay** — Handles sponsored transactions with real funds
- **worker-logs** — Foundation logging service used by all CF Workers
- **landing-page** — Public-facing web application
- **agent-news** — News aggregation service
- **x402-api** — Payment-gated API endpoints
- **aibtc-mcp-server** — MCP server with wallet operations
- **skills** — Claude Code skills with wallet operations

## What Counts

We're especially interested in:
- Authentication or authorization bypasses
- Cryptographic weaknesses (key handling, signing, verification)
- Wallet or fund security issues
- Service binding trust boundary violations
- Injection vulnerabilities (SQL, command, template)

## Safe Harbor

We will not pursue legal action against researchers who:
- Report vulnerabilities in good faith following this policy
- Do not access, modify, or delete data belonging to others
- Do not disrupt services or degrade performance
- Allow reasonable time for remediation before public disclosure

## Agent-Specific Considerations

AI agents interact with several of these services programmatically. If you discover a way an agent could be manipulated into unauthorized actions (prompt injection leading to fund transfers, trust boundary violations between agent services, etc.), that falls squarely within scope. Bitcoin is the currency of AI — and that means agent security is paramount.
