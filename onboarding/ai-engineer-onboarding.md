# AI engineer onboarding: the first 90 days

Goal: by day 90, a new engineer independently ships changes to an AI feature, with
evaluation results, and is on the on-call rotation. Every week has one concrete outcome,
so both the engineer and the manager can see progress.

Each new engineer gets an **onboarding buddy** (a teammate, not the manager) for the
first 90 days, and a 30-minute check-in with the manager every week of the first month.

## Days 1-30: learn the system by running it

| Week | Outcome |
|---|---|
| 1 | Laptop, access and local setup done. Runs the service and the evaluation suite locally. **Merges a first small pull request** (docs, a test, a new eval case) |
| 2 | Reads the decision records and the evaluation plan. Walks the buddy through the request path, from question to cited answer, on a whiteboard |
| 3 | Reviews 30 real (anonymized) interactions with the buddy and labels the failures. Adds 10 new cases to the evaluation set from what they found |
| 4 | Ships a small, scoped improvement with before/after evaluation results in the PR, using the [AI change review](https://github.com/tsriharsha402/ai-delivery-playbook/blob/main/templates/06-ai-change-review.md) |

**Check at day 30:** can explain how quality is measured, what a request costs, and
the three most common failure types, in their own words.

## Days 31-60: own something

| Week | Outcome |
|---|---|
| 5-6 | Owns a feature or improvement end to end, from a short design note to release |
| 7 | Presents at the weekly evaluation review: what changed, the evidence, what they'd do next |
| 8 | Shadows two on-call shifts; walks through a past AI incident postmortem with the buddy |

**Check at day 60:** shipped an owned change safely; reads evaluation results critically
(asks "is that difference real?").

## Days 61-90: operate and improve

| Week | Outcome |
|---|---|
| 9-10 | Writes a decision record for a real choice the team faces |
| 11 | Joins the on-call rotation as secondary |
| 12 | Writes a one-page "fresh eyes" note: what confused them, what's missing from docs, what they'd fix first. The team acts on at least one item |

**Check at day 90:** a structured conversation against the
[competency matrix](../hiring/competency-matrix.md): current level per competency and
two growth goals for the next quarter.

## What the manager provides

- A starter task list, prepared before day one, with the first PR already scoped
- Access to real (anonymized) production samples, not only synthetic examples
- Protected time: no on-call and no incident duty in the first 60 days
- Explicit permission to ask "why" about any decision, and to update docs that are wrong
