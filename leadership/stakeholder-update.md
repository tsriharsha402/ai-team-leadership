# Monthly stakeholder update

A one-page update for leaders and partner teams. Same structure every month, so readers
know where to look. Written in plain language; numbers always come with the date they
were measured and what "good" is.

## Template

```markdown
# <Feature or team>: <Month YYYY> update

**Status:** On track / At risk / Off track, in one sentence why.

## Headlines
- <The one thing leadership should know>
- <Progress against the roadmap>
- <Risk or decision needed>

## Quality, cost, usage
| Metric | This month | Last month | Target |
|---|---|---|---|
| Evaluation pass rate | | | |
| User negative-feedback rate | | | |
| Weekly active users | | | |
| Cost per answer | | | |
| Total spend vs. budget | | | |

## Shipped
## Learned (including what didn't work)
## Next month
## Decisions or help needed
- <Specific ask, from whom, by when>
```

## Example: Handbook Assistant, pre-launch

An example using the project's actual state at the time of writing. Nothing has launched
yet, so there are no usage numbers, and the update says so instead of inventing them.

> # Handbook Assistant: October 2026 update
>
> **Status:** At risk for the Q4 pilot. The system is built and tested, but three launch
> blockers are open.
>
> ## Headlines
> - v0.1 is built: answers cite the exact handbook text and say "I don't know" when the
>   handbook doesn't cover a question.
> - Quality is measured automatically on every change (46-question evaluation suite).
>   Retrieval finds the right document for 95% of questions.
> - **Not ready for users yet:** no login (SSO), no total spend cap, and quality with
>   the production model hasn't been measured.
>
> ## Quality, cost, usage
> | Metric | Now | Target |
> |---|---|---|
> | Retrieval finds the right document | 95% | ≥ 90% |
> | Answer pass rate (production model) | Not yet measured | ≥ 90% |
> | Estimated cost per answer | ~$0.012 | ≤ $0.02 |
> | Users | 0 (pre-launch) | Pilot: 2 teams |
>
> ## Next month
> - Run the evaluation and model comparison against Claude (under $6 in API cost).
> - Integrate SSO; add a daily spend cap with an alert.
>
> ## Decisions or help needed
> - **API budget:** approve $6 for evaluation runs, and a $300/month cap for the pilot.
> - **Pilot teams:** two volunteer teams, identified by November 15.
