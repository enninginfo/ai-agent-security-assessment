# Risk and control guidance

## Rubric
Define task/time horizon. Rate likelihood and impact Low/Moderate/High with reasons; use Unknown where evidence is insufficient. Track confidence separately. Do not multiply ordinal labels or call this matrix NIST-prescribed.

Likelihood: Low = substantial unlikely preconditions; Moderate = credible exposure/preconditions with uncertainty; High = routinely exposed preconditions or reproducible applicable failure. A single test does not establish frequency.
Impact: Low = limited reversible low-sensitivity effects; Moderate = meaningful limited disclosure/disruption/repair; High = sensitive disclosure, consequential action, broad account exposure, or difficult recovery.

| Likelihood / Impact | Low | Moderate | High |
| --- | --- | --- | --- |
| Low | Low | Low | Moderate |
| Moderate | Low | Moderate | High |
| High | Moderate | High | High |

Keep inherent-risk assumptions explicit; assess residual risk only within supported safeguards. Future connection scenarios are not current exposure. Missing evidence is not Low risk. Distinguish demonstrated failure, configuration exposure, design limitation, contradictory claim, and evidence gap.

## Controls and mistaken inferences

| Scenario | Supported controls to verify | Avoid inferring |
| --- | --- | --- |
| Account/session takeover | MFA/passkeys, recovery/session/grant review | MFA prevents delegated-token misuse |
| External instruction injection | Untrusted-input handling, separate authority, scopes/destination checks | A defensive prompt guarantees resistance |
| Unapproved send/share/delete | Host approval, exact binding, expiry, bounded retries | Dialog/timeout proves prevention |
| Excessive access | Source scopes, read/write separation, task grants, isolated data | Read-only has no confidentiality risk |
| Secrets exposure | Secret broker/vault, isolated credentials, secure entry | Mentioning a vault proves all secrets hidden |
| Confidential disclosure | Source minimization, access/egress policy, handling rules | Classification after reading prevents exposure |
| Persistent/provider access | Documented lifecycle, key ownership, preferences | Opt-out/forget implies zero retention |
| Skill modification | Review/provenance, restricted editing, least privilege | Generated skills enforce permissions |
| Silent/delayed misuse | Host/source audit, event coverage, tested alerts | Logs/promises prevent covert actions |
| Revocation/recovery gaps | Grants/sessions/jobs/copies inventory, evidence preservation | Disconnect deletes all access and data |

Do not invent unsupported settings or DLP/monitoring. If granular controls do not exist, recommend constrained tasks, dedicated accounts, less sensitive data, manual review, or deferring connection.

For findings use scenario → evidence/type → controls/layer → likelihood/impact/reasons → confidence → recommendation/owner/priority → implementation status → acceptance test → uncertainty. Do not credit proposed controls or claim effectiveness from configuration alone.

## Primary anchors
Verify current official editions and exact category identifiers when applying mappings:
- SP 800-30 Rev. 1: https://csrc.nist.gov/pubs/sp/800/30/r1/final
- CSF 2.0: https://www.nist.gov/cyberframework
- AI RMF: https://www.nist.gov/itl/ai-risk-management-framework
- GenAI Profile: https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence

Use SP 800-30 for assessment reasoning and CSF for cybersecurity outcomes. Optionally use AI RMF Govern/Map/Measure/Manage for lifecycle framing; keep it distinct from CSF. State “NIST-informed”; never claim certification, compliance, a complete audit, or prescribed NIST scoring.

