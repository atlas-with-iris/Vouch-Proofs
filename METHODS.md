# Methods

## Test: General Floor Validation (v5)

### Objective

Measure Vouch's baseline detection accuracy on uncurated, general-purpose AI agent action plans — without any prior training data, LLM assistance, or human oversight.

### Approach

- **Analysis type:** Deterministic multi-signal analysis
- **Dataset:** 1,000,000 synthetically generated agent action plans
- **Balance:** Approximately 50/50 split between benign (legitimate) and dangerous (harmful) plans
- **Plan characteristics:** Realistic agent-like patterns including typos, formatting inconsistencies, ambiguous verbs, long-tail intents, and natural language variation
- **No adversarial bias:** Plans were not specifically designed to evade or trick the system

### Conditions

| Condition | Setting |
|-----------|---------|
| Prior training data | None (cold start) |
| LLM assistance | Disabled |
| Human oversight | None |
| External AI services | None |
| Hardware | Single node, standard hardware |
| Runtime environment | Node.js |

### What Was Measured

1. **Catch rate** — Percentage of dangerous plans correctly identified
2. **False positive rate (strict)** — Percentage of legitimate plans incorrectly blocked at the highest severity
3. **False positive rate (permissive)** — Percentage of legitimate plans flagged at any severity
4. **Throughput** — Plans analyzed per second
5. **Benign rescue rate** — Legitimate plans that would have been flagged by simpler systems but were correctly cleared

### Verification

Results are deterministic: the same input dataset produces the same output every time. No randomness, no probabilistic classifiers.
