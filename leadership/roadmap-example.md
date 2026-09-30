# Roadmap example: Handbook Assistant

A three-quarter roadmap for
[production-rag-service](https://github.com/tsriharsha402/production-rag-service), written
the way I'd present it to a team and its stakeholders. Each item is a **bet** with a
measurable outcome and an exit criterion, so the roadmap can be judged, not just delivered.

**Starting point (September 2026):** v0.1 built; evaluation suite in CI; launch
[review says no-go](https://github.com/tsriharsha402/ai-delivery-playbook/blob/main/examples/handbook-assistant/04-launch-readiness.md)
until authentication, a spend cap and Claude evaluation results are in place.

## Q4 2026: launch safely to a pilot

| Bet | Success metric | Exit / pivot if |
|---|---|---|
| Close launch blockers: SSO, total spend cap, privacy notice | Launch readiness review passes | n/a (required) |
| Publish Claude evaluation results; pick the model with evidence ([issue](https://github.com/tsriharsha402/production-rag-service/issues/1)) | Pass rate ≥ 90%, abstention accuracy ≥ 80% | Below threshold: fix retrieval and prompt before any pilot |
| Pilot with two teams, with thumbs up/down feedback | 40% of pilot users use it weekly; negative feedback < 20% | Usage < 15% after 4 weeks: interview users before building more |

## Q1 2027: better answers, lower cost

| Bet | Success metric | Exit / pivot if |
|---|---|---|
| Hybrid retrieval (BM25 + embeddings) ([issue](https://github.com/tsriharsha402/production-rag-service/issues/2)) | Retrieval hit@1 on the eval set +5 points | No gain: keep BM25, drop the extra infrastructure |
| Grow the eval set to 200+ cases from pilot traffic | Model comparisons with ±5-point intervals | n/a |
| Cheaper configuration if non-inferior ([method](https://github.com/tsriharsha402/llm-model-selection)) | Cost per answer −30% at equal quality | Not non-inferior: stay, re-test next model release |
| Company-wide rollout | Policy questions in chat channels −50% | Negative feedback > 20%: pause rollout |

## Q2 2027: operate and extend

| Bet | Success metric | Exit / pivot if |
|---|---|---|
| Tracing and dashboards ([issue](https://github.com/tsriharsha402/production-rag-service/issues/3)); weekly scheduled eval | Regressions detected within a day | n/a |
| Streaming answers ([issue](https://github.com/tsriharsha402/production-rag-service/issues/5)) | Time to first token < 1.5 s | No change in satisfaction: deprioritize |
| Second corpus (engineering runbooks), reusing the platform | Launch in < 4 weeks using the same playbook | Takes > 8 weeks: invest in platform before more corpora |

## Not on this roadmap (and why)

- **Conversation and follow-up questions.** Adds state and new failure modes; wait for
  pilot evidence that single questions aren't enough.
- **Answering beyond the handbook with general knowledge.** Conflicts with the grounding
  guarantee that makes answers trustworthy.
- **Fine-tuning a custom model.** No evidence hosted models fall short; revisit only if
  evaluation says so.
