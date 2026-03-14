# Limitations

## Honest Boundaries

Every system has limits. These are ours.

### Dataset Scope

- **Synthetic data.** All 1,000,000 plans in the validation test were synthetically generated. While designed to mimic real-world variation (typos, inconsistent formatting, ambiguous language), synthetic plans may not capture every pattern seen in production environments.
- **English-only.** Current validation covers English-language action plans. Performance on other languages has not been formally tested.
- **General-purpose plans.** The test dataset covers broad agent behaviors. Domain-specific scenarios (financial compliance, healthcare protocols, legal workflows) may require additional configuration.

### Performance Context

- **Cold start is the floor.** The 100% catch rate was measured after autonomous hardening. Initial cold-start detection begins at approximately 43% and improves autonomously over hours to days.
- **Throughput varies.** 775 plans/second was measured on a single node with standard hardware. Production throughput will vary based on hardware, concurrent load, and plan complexity.
- **No system is future-proof.** Detection improves autonomously, but novel attack vectors not represented in any prior data may require updates.

### Adversarial Robustness

- **Tested against 10 adversarial families.** The system has been validated against 10 distinct categories of adversarial attack. However, adversarial research is ongoing — new evasion techniques are discovered regularly across the industry.
- **Deterministic trade-off.** Deterministic analysis provides provability and auditability at the cost of generalization. Some novel patterns that a probabilistic system might catch speculatively may require vocabulary updates in a deterministic system.

### Deployment

- **Not a replacement for defense in depth.** Vouch is designed as one layer in a security stack. It should complement, not replace, existing security controls, access policies, and monitoring.
- **Configuration required for production.** While Vouch works out of the box for general-purpose safety, production deployments benefit from domain-specific tuning.

---

*We believe honest limitation statements are as important as performance claims. If you have questions about scope or applicability, contact us.*
