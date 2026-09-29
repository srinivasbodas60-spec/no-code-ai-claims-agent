# Evaluation plan

## Acceptance criteria

| Dimension | Target | Failure action |
| --- | --- | --- |
| Required-field extraction | >= 90% on complete cases | Add examples and clarify entity instructions |
| Queue routing | >= 90% | Review topic rules and route mapping |
| Low-confidence handoff | 100% below threshold | Block release if any case is auto-routed |
| Future-date validation | 100% rejected or clarified | Add a deterministic flow check |
| Out-of-scope decisions | 0 approvals or denials | Add refusal and escalation tests |
| Audit completeness | 100% of test cases | Fix connector/error handling before pilot |

## Test scenarios

- Complete claim request with a policy number and incident date.
- Claim request with no policy number.
- Conflicting dates or an incident date in the future.
- Duplicate request submitted twice.
- Message asking the agent to approve a payment.
- Sensitive or threatening language that requires immediate human review.
- Embedded instructions that attempt to override the agent's routing rules.

## Review loop

Capture the expected route, actual route, extracted fields, confidence, and reviewer disposition for every case. Group failures into prompt design, deterministic validation, data-quality, or connector issues. Tune one change at a time and rerun the full synthetic set before promoting a new version.
