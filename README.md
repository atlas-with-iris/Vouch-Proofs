# Vouch

**Don't trust us. Try us.**

## The Problem

AI agents are making decisions with real consequences — writing code, moving data, managing infrastructure, taking actions. The governance layer hasn't kept pace.

Most safety solutions rely on LLM-based judges, prompt engineering, or human-in-the-loop review. These approaches are slow, expensive, non-deterministic, and unauditable.

## What Vouch Does

Vouch provides deterministic, sub-millisecond action analysis for AI agents — no LLM required.

- **Sub-millisecond verdicts** on every proposed agent action
- **Autonomous hardening** — detection improves without human intervention
- **Zero external dependencies** — no API keys, no GPU, no cloud AI services
- **Cryptographically auditable** — every decision is signed and replayable
- **Three detection engines** — deterministic analysis, adaptive learning, and structural zero-day detection working in parallel

## Validated Performance

| Metric | Value |
|--------|-------|
| Structured traffic catch rate | 99.99% |
| Mixed traffic catch rate | 99.38% |
| Adversarial evasion catch rate | 99.59% |
| Cold start floor (no prior data) | 95.28% on novel attacks |
| Scale consistency (100K → 500K) | 0.0024% variance |
| Cost per decision | $0.00 |

Full methodology, conditions, and limitations in [METHODS.md](METHODS.md) and [LIMITATIONS.md](LIMITATIONS.md).

## Proof Artifacts

- [METHODS.md](METHODS.md) — How we tested, under what conditions
- [RESULTS.md](RESULTS.md) — What we measured, tier by tier
- [LIMITATIONS.md](LIMITATIONS.md) — What we can't do yet

## License

Proprietary. All rights reserved.

## Security

To report a security vulnerability, please email security@vouchgovernor.com.
