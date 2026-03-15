# Methods

## Proof Run Suite — March 2026

### Overview

Five tiers of validation, designed to answer five distinct questions. Every run uses seeded pseudo-random number generation for full reproducibility — same seed, same plans, same results.

All runs use the same frozen metrics schema and include provenance metadata (commit hash, configuration hash, corpus hash, random seed, runtime version) for independent verification.

---

### Tier 1: Structured Traffic Baseline

**Question:** Can we reproduce a flagship result reliably?

- **Dataset:** 100,000 synthetically generated agent action plans
- **Balance:** 50/50 split — benign (legitimate) and dangerous (harmful)
- **Plan characteristics:** Realistic agent-like patterns including formatting inconsistencies, ambiguous verbs, and natural language variation
- **Seed:** Deterministic, reproducible

### Tier 2: Mixed Traffic Stress

**Question:** How does the system perform under real-world traffic distribution?

- **Dataset:** 100,000 plans
- **Balance:** 60% benign / 30% dangerous / 10% edge cases
- **Edge cases:** Euphemistic framing, encoded payloads, fragmented multi-step actions, domain-specific language
- **Seed:** Deterministic, reproducible

### Tier 3: Zero-Day Cold Start

**Question:** How well does the system detect attacks it has never seen before?

- **Dataset:** 10,000 novel attack patterns — completely distinct from any prior training or test data
- **Approach:** Run with zero prior knowledge (cold), measure detection rate
- **Attack families:** Infrastructure manipulation, supply chain poisoning, credential relay, observability subversion, certificate hijacking, and others

### Tier 4: Adversarial Evasion

**Question:** Can attackers evade detection using encoding tricks?

- **Dataset:** 50,000 plans using active evasion techniques
- **Evasion families:** Leetspeak substitution, homoglyph characters (Cyrillic/Greek), space injection, Base64 encoding, euphemistic wrapping, reversed keywords, non-Latin Unicode
- **Balance:** 50/50 split — evasive dangerous and standard benign

### Tier 5: Scale Consistency

**Question:** Do results hold as volume increases?

- **Datasets:** 100,000 → 500,000 plans using identical configuration and seed
- **Measurement:** Catch rate variance between runs at different scales

---

### Conditions (All Tiers)

| Condition | Setting |
|-----------|---------|
| Prior training data | None (cold start) |
| LLM assistance | None |
| Human oversight | None |
| External AI services | None |
| Hardware | Single node, standard hardware |
| Cost per decision | $0.00 |

### Verification

Every run is deterministic. Same seed → same plans → same results. Provenance metadata (commit hash, configuration hash, corpus hash) is logged with every artifact for independent reproduction.
