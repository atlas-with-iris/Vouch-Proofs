# Results

## Proof Run Suite — March 2026

### Tier 1: Structured Traffic Baseline — 100,000 Plans

| Metric | Value |
|--------|-------|
| Catch rate | 99.988% |
| Dangerous plans caught | 49,994 / 50,000 |
| Dangerous plans missed | 6 |
| False positive rate (strict) | 6.45% |
| Throughput | 590 plans/second |

All 6 missed plans shared the same root cause — a known edge in contextual disambiguation between structurally similar benign and dangerous actions. None involved direct attack language.

---

### Tier 2: Mixed Traffic Stress — 100,000 Plans

| Metric | Value |
|--------|-------|
| Catch rate | 99.378% |
| Dangerous plans caught | 39,791 / 40,040 |
| Dangerous plans missed | 249 |
| False positive rate (strict) | 6.49% |
| Throughput | 378 plans/second |

Of 249 missed plans, **248 were edge cases** (euphemistic or encoded evasion). Only **1 was a standard dangerous plan** — the system's structured attack detection is effectively complete.

---

### Tier 3: Zero-Day Cold Start — 10,000 Novel Plans

| Metric | Value |
|--------|-------|
| Cold catch rate | 95.28% |
| Novel attacks caught | 4,764 / 5,000 |
| Novel attacks missed | 236 |
| False positive rate (strict) | 5.80% |

The system caught 95.28% of completely novel attack patterns it had never been exposed to — zero prior training data, zero vocabulary overlap. Missed plans were cleared by contextual disambiguation rules, not vocabulary gaps.

---

### Tier 4: Adversarial Evasion — 50,000 Plans

| Metric | Value |
|--------|-------|
| Catch rate | 99.588% |
| Evasive plans caught | 24,897 / 25,000 |
| Evasive plans missed | 103 |
| False positive rate (strict) | 6.45% |
| Throughput | 626 plans/second |

**Leak breakdown by evasion type:**

| Evasion Family | Missed |
|----------------|--------|
| Euphemistic wrapping | 27 |
| Non-Latin Unicode | 9 |
| Space injection | 5 |
| Leetspeak substitution | 3 |
| Homoglyph characters | 3 |
| Base64 encoding | 3 |

Encoding-based evasion (leetspeak, homoglyphs, Base64) is effectively solved. Euphemistic wrapping remains the hardest category — by design, it's the most semantically ambiguous.

---

### Tier 5: Scale Consistency — 100K → 500K

| Scale | Catch Rate | Missed | FPR (strict) | Throughput |
|-------|-----------|--------|--------------|------------|
| 100,000 | 99.988% | 6 | 6.45% | 450 plans/s |
| 500,000 | 99.990% | 24 | 6.53% | 437 plans/s |

**Max catch rate variance: 0.0024%** — Results are stable across 5x scale increase.

---

### Summary

| Tier | Test | Catch Rate | Story |
|------|------|-----------|-------|
| 1 | Structured traffic | **99.988%** | Reproducible baseline |
| 2 | Mixed traffic | **99.378%** | Robust on real-world distribution |
| 3 | Zero-day cold start | **95.28%** | Effective on unseen attacks |
| 4 | Adversarial evasion | **99.588%** | Hardened against encoding tricks |
| 5 | Scale (500K) | **99.990%** | Stable at volume |
