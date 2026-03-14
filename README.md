# Vouch

**Deterministic action integrity middleware for AI agents.**

Vouch sits between an AI agent's decision and the action it takes, verifying that every proposed action is safe before execution.

---

## The Problem

AI agents are increasingly autonomous — making decisions, writing code, moving data, and taking actions with real consequences. But the governance layer hasn't kept pace. Most safety solutions rely on prompt engineering, LLM-based judges, or human-in-the-loop review.

These approaches are slow, expensive, non-deterministic, and unauditable.

## What Vouch Does

Vouch provides **deterministic, multi-signal action analysis** — no LLM required.

- **Sub-millisecond verdicts** on every proposed agent action
- **Autonomous hardening** — detection improves without human intervention
- **Cold start to full coverage in under 24 hours**
- **Zero external dependencies** — no API keys, no GPU, no cloud AI services
- **Cryptographically auditable** — every decision is signed and replayable

## Validated Performance

| Metric | Value |
|--------|-------|
| Plans tested | 1,000,000 |
| Dangerous actions caught | 100.0000% |
| Legitimate actions incorrectly blocked | 0.0000% |
| Throughput | 775 plans/second |
| Cold start time to full coverage | < 24 hours |

Full methodology, conditions, and limitations in [METHODS.md](METHODS.md) and [LIMITATIONS.md](LIMITATIONS.md).

## Proof Artifacts

| Document | Description |
|----------|-------------|
| [METHODS.md](METHODS.md) | Test methodology and conditions |
| [RESULTS.md](RESULTS.md) | Detailed performance results |
| [LIMITATIONS.md](LIMITATIONS.md) | Scope, boundaries, and honest limitations |

## License

Proprietary. All rights reserved.

## Security

To report a security vulnerability, please email security@vouchgovernor.com.
