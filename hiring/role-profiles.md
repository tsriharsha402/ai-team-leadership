# Role profiles

Job titles in AI are inconsistent across companies. These profiles define roles by what
they **own**, so a job posting, an interview loop and a performance review all describe
the same job.

| Role | Owns | Typical background | Hire when |
|---|---|---|---|
| **AI engineer** (applied LLM engineer) | Features built on hosted models: prompts, retrieval, tool use, evaluation, and the service around them | Backend or full-stack engineer who has shipped LLM features | **First hire.** Most product teams need this role and nothing else at first |
| **AI platform engineer** | Shared infrastructure: model gateway, evaluation pipelines, observability, cost controls, access to data | Platform / infrastructure / SRE | Three or more teams are building AI features and duplicating plumbing |
| **ML engineer** | Training, fine-tuning and serving custom models; data pipelines for them | ML engineering, MLOps | Evaluations prove hosted models can't meet quality, latency, cost or data requirements |
| **Applied scientist** | Novel methods, rigorous experiments, research-grade evaluation | Research background, publications | The product's advantage depends on techniques that don't exist off the shelf |

## A first team of four

For a product team starting with LLM features on hosted models:

| Seat | Role | Why |
|---|---|---|
| 1 | Senior AI engineer | Sets technical direction, owns the evaluation strategy |
| 2 | AI engineer | Feature delivery |
| 3 | AI engineer with strong frontend skills | AI features live or die on the user experience of uncertainty: citations, "I don't know", feedback |
| 4 | AI platform engineer (can be shared with another team) | Observability, cost controls, deployment |

An ML engineer is added only when an [evaluation](https://github.com/tsriharsha402/llm-model-selection)
shows hosted models can't do the job. Hiring one first usually leads to a custom model
nobody needed.

## What every role needs

Whatever the title, everyone on the team can:

- write and extend an evaluation set, and read failed cases critically;
- explain what a change costs per request;
- say "the data doesn't support that yet" to a stakeholder.

See the [competency matrix](competency-matrix.md) for how these are assessed by level.
