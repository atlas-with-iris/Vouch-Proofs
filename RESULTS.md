# Results

## General Floor Validation (v5) — 1,000,000 Plans

### Summary

| Metric | Value |
|--------|-------|
| Total plans analyzed | 1,000,000 |
| Catch rate | 100.0000% |
| False positive rate (strict) | 0.0000% |
| False positive rate (permissive) | 0.0000% |
| Legitimate plans correctly cleared | 48,485 |
| Dangerous plans missed | 0 |
| Legitimate plans incorrectly blocked | 0 |
| Throughput | 775 plans/second |
| Total runtime | 21.5 minutes |

### What These Numbers Mean

- **100% catch rate** — Every dangerous plan in the dataset was correctly identified and would have been blocked before execution.
- **0% false positive rate** — No legitimate plan was incorrectly flagged or blocked. Zero operational disruption to safe agent behavior.
- **48,485 benign plans rescued** — Plans that contained ambiguous patterns but were correctly identified as safe. These would likely trigger false positives in simpler keyword-based or LLM-based systems.
- **775 plans/second** — Sustained throughput on a single node with standard hardware. No batching, no GPU, no external API calls.

### Conditions

- Cold start — no prior data or profiles
- Deterministic — no LLM, no randomness
- Fully autonomous — no human review during the test
- Single node — no distributed infrastructure

### Historical Context

| Test | Plans | Catch Rate | FPR | Notes |
|------|-------|------------|-----|-------|
| Cold start baseline | 25,000 | 43% | — | First deployment, no optimization |
| General floor v1 | 100,000 | 98.8% | 6.36% | After initial autonomous hardening |
| General floor v5 | 1,000,000 | 100.0% | 0.0% | Current validated performance |

Detection accuracy improved from 43% to 100% through autonomous hardening alone — no manual rule writing, no human-curated training data, no LLM assistance.
