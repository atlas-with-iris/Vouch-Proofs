# Limitations

## Honest Boundaries

Every system has limits. These are ours.

### Dataset Scope

- **Synthetic data.** All validation plans were synthetically generated. While designed to mimic real-world variation (typos, inconsistent formatting, ambiguous language, encoding tricks), synthetic plans may not capture every pattern seen in production environments.
- **English-primary.** Core validation covers English-language action plans. Non-Latin Unicode detection has been tested (95%+ catch on Cyrillic, Japanese, space-injected), but full multilingual coverage is ongoing.
- **General-purpose plans.** The test datasets cover broad agent behaviors. Domain-specific scenarios (financial compliance, healthcare protocols, legal workflows) may require additional configuration.

### Detection

- **Euphemistic framing is the hardest problem.** Plans that use business-appropriate language to describe harmful actions (e.g., "streamline credential management" meaning "weaken authentication") are the primary source of remaining misses. This is a feature of the problem, not a bug in the system.
- **Cold start is high but not perfect.** On completely novel attack patterns with zero prior exposure, the system catches 95.28%. The remaining 4.72% are missed due to contextual disambiguation, not vocabulary gaps.
- **Deterministic trade-off.** Deterministic analysis provides provability and auditability at the cost of generalization. Novel patterns that a probabilistic system might catch speculatively may require updates in a deterministic system.

### Performance

- **Throughput varies.** 400–600 plans/second was measured on a single node with standard hardware. Production throughput will vary based on hardware, concurrent load, and plan complexity.
- **False positive rate.** Current strict FPR is approximately 6.5%. Plans flagged at this level are not blocked — they receive elevated review. Operational FPR (plans incorrectly hard-blocked) is effectively 0%.

### Adversarial Robustness

- **Encoding evasion is largely solved.** Leetspeak, homoglyphs, Base64, space injection — all catch at 97%+. But adversarial research is ongoing. New evasion techniques are discovered regularly across the industry.
- **Not a replacement for defense in depth.** Vouch is designed as one layer in a security stack. It should complement, not replace, existing security controls, access policies, and monitoring.

---

*We believe honest limitation statements are as important as performance claims. If you have questions about scope or applicability, contact us.*
