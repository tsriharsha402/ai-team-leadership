# Team metrics

What to measure about an AI team, and what not to. Metrics are for the team to improve
its own system, reviewed together; they are never used to rank individuals.

## Delivery

| Metric | Why | Healthy direction |
|---|---|---|
| Lead time: idea to production | Speed of learning | Falling |
| Deployment frequency | Small, safe changes | Rising |
| Change failure rate (incl. quality regressions) | Safety of changes | Low and stable |
| Time to restore after an incident | Resilience | Falling |

## AI quality

| Metric | Why | Healthy direction |
|---|---|---|
| Features with an evaluation suite in CI | Coverage of the quality safety net | 100% of launched features |
| Evaluation set size and freshness (cases added from real failures this month) | An eval set that stops growing stops finding problems | Growing |
| Pass rate on each feature's eval, trended | Quality over time | Stable or rising |
| Abstention and refusal rates in production | Early warning of drift | Stable within bands |
| User negative-feedback rate | What users actually experience | Falling |
| Time from reported failure to eval case | How fast learning is captured | Days, not weeks |

## Cost

| Metric | Why | Healthy direction |
|---|---|---|
| Cost per completed task, per feature | Unit economics | Falling or justified by quality |
| Total monthly model spend vs. budget | Predictability | Within budget |
| Cache hit rate | Cheapest cost lever | Rising |

## Team health

| Metric | Why | Source |
|---|---|---|
| Engagement and sentiment | Early warning of burnout or frustration | 1:1s, quarterly survey |
| On-call load (pages per week, night pages) | Sustainability | Paging tool |
| Growth: people moving up a level on at least one competency per half-year | Development | [Competency matrix](../hiring/competency-matrix.md) reviews |
| Regretted attrition | Retention | HR |

## What not to measure

- **Lines of code, PR counts or story points per person.** They reward activity, not outcomes.
- **Number of experiments run.** Rewards starting things, not finishing them.
- **Raw accuracy without uncertainty or a fixed test set.** A number that can't be
  compared over time is decoration.
- **Model "intelligence" benchmarks.** Only your own task's evaluation predicts your
  users' experience.
