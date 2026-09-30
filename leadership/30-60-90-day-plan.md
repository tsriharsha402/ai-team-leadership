# 30-60-90 day plan: new AI engineering manager

My plan for the first 90 days leading a team that builds AI features. The principle:
**listen before changing things, make quality visible before improving it, and earn
trust with small, delivered wins.**

## Days 1-30: understand

**Goal:** know the people, the systems, and where quality, cost and risk actually stand.

| Area | Actions |
|---|---|
| People | 1:1 with every team member: what's working, what's frustrating, what they want to grow into. 1:1s with product, design, and the teams we depend on |
| Systems | Run every AI feature myself. Read the architecture, decision records and the last three incident postmortems |
| Quality | Find out how quality is measured today. If there's no evaluation suite, that's the first finding, not a failure to hide |
| Cost | Get the monthly model spend, broken down by feature. Estimate cost per task |
| Risk | List AI features by [risk tier](https://github.com/tsriharsha402/ai-delivery-playbook#right-size-the-process-risk-tiers); check which have had a risk review |
| Delivery | Measure how long a change takes from idea to production, and where it waits |

**Deliverable at day 30:** a two-page "state of AI" document shared with the team first,
then my manager: strengths, top three risks, top three opportunities, and questions
still open. No big changes yet.

## Days 31-60: make quality visible, fix the biggest risk

**Goal:** the team and stakeholders can see how good the AI features are, and the most
serious gap is being closed.

| Area | Actions |
|---|---|
| Evaluation | Stand up (or improve) an evaluation suite for the highest-traffic feature. Run it in CI on every change |
| Rituals | Start a weekly 30-minute evaluation review: results, failures, what changed. See the [operating model](team-operating-model.md) |
| Biggest risk | Close the top risk from the day-30 document (often: no abstention path, no spend limit, or no rollback) |
| Quick win | Ship one improvement users notice, chosen with the team, measured before and after |
| Process | Introduce the [AI change review](https://github.com/tsriharsha402/ai-delivery-playbook/blob/main/templates/06-ai-change-review.md) for model and prompt changes |

**Deliverable at day 60:** a quality dashboard or report stakeholders can read, and one
closed risk.

## Days 61-90: set direction

**Goal:** a roadmap the team believes in, and a team shape that can deliver it.

| Area | Actions |
|---|---|
| Roadmap | Draft a two-quarter roadmap with the team and product: bets, success metrics, what we won't do. See the [roadmap example](roadmap-example.md) |
| Cost | Run a model selection review for the most expensive feature ([method](https://github.com/tsriharsha402/llm-model-selection)) |
| Team | Gap analysis against the [competency matrix](../hiring/competency-matrix.md): growth plans for each person, and whether a hire is needed |
| Stakeholders | First monthly [stakeholder update](stakeholder-update.md) |

**Deliverable at day 90:** an agreed roadmap, a hiring plan (or a decision not to hire),
and the monthly update running.

## How I'll know it's working

| Signal | Target by day 90 |
|---|---|
| Features with an evaluation suite in CI | The highest-traffic feature, at minimum |
| Team can answer "how good is it?" with a number | Yes, with the date it was measured |
| Cost per task known for every AI feature | Yes |
| Team sentiment in 1:1s | Same or better than day 1 |
| Stakeholders know what's coming next quarter, and what isn't | Yes |

## What I won't do in the first 90 days

- Reorganize the team or change everyone's tools
- Rewrite a working system because I'd have built it differently
- Promise stakeholders dates before understanding the team's delivery pace
