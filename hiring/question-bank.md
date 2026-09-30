# Question bank

Each question lists what it tests, what a strong answer covers, red flags, and anchors for
the [scorecard](scorecard.md)'s 1-4 scale. Interviewers use the prompts as written, then
follow the candidate's answer.

---

## Stage 2: Practical coding

### Build an answer cache for an LLM service (60 min)

> "Our service calls an LLM to answer questions. Implement a cache so repeated questions
> don't call the model again. Tests included. You can use any language and look things up."

**Follow-ups:** How do you invalidate entries when source documents change? What changes
with three replicas? What should never be cached?

| | |
|---|---|
| **Strong** | Normalizes the key (case, whitespace); includes model and a document version in the key; TTL and size bound; tests expiry and eviction; says refusals and errors must not be cached; proposes Redis for replicas |
| **Red flags** | No tests; key on raw string only; never considers stale data; can't explain their own code |
| **Anchors** | 1: incomplete or incorrect · 2: works for the basic case · 3: correct, tested, handles invalidation · 4: also reasons unprompted about replicas, what not to cache, and cost impact |

---

## Stage 3: AI system design

### Design an internal policy assistant (60 min)

> "Employees keep asking HR and team leads the same policy questions. Design a system
> that answers them from the company handbook."

A reference implementation to calibrate interviewers:
[production-rag-service](https://github.com/tsriharsha402/production-rag-service).

**Probe areas (cover at least four):**

1. Would you use an LLM at all? What's the simplest alternative?
2. How do answers stay grounded? How does a user verify one?
3. What happens when the handbook doesn't cover the question?
4. How do you know it's good before launch, and after?
5. What does it cost per question, and at 10× the traffic?
6. A policy document changes. What happens to cached or indexed content?

| | |
|---|---|
| **Strong** | Asks about users and volume first; retrieval with citations; explicit "I don't know" path; an evaluation set that includes unanswerable questions; estimates cost from token counts; mentions staged rollout and monitoring |
| **Red flags** | Jumps to fine-tuning or a vector DB before understanding the problem; no evaluation plan; treats hallucination as solved by "a better prompt"; no cost awareness |
| **Anchors** | 1: can't produce a working design · 2: working design, no evaluation or failure handling · 3: grounded design with evaluation, abstention and cost reasoning · 4: also makes tradeoffs explicit, sequences the build, and names what would change the design |

---

## Stage 4: Evaluation and debugging

### Part A: Debug a wrong answer (25 min)

> "Users report the assistant said unused vacation days don't carry over. The handbook
> says up to 5 days carry over until March 31. Here are the logs for that request:
> retrieved chunks, prompt and answer. What happened, and what do you do?"

Prepare three variants of the logs, and give one at random: (a) retrieval missed the
right chunk, (b) the right chunk was retrieved but the answer contradicted it,
(c) an outdated version of the policy was indexed.

| | |
|---|---|
| **Strong** | Reads the evidence before guessing; locates the failure layer (retrieval, generation, data); fixes the cause and **adds the case to the evaluation set**; checks whether other answers are affected; says how users are told |
| **Red flags** | Immediately edits the prompt without diagnosis; no regression test; blames the model |
| **Anchors** | 1: no diagnosis · 2: finds the layer, patches the symptom · 3: correct cause, fix, and regression case · 4: also scopes blast radius and proposes a monitoring signal that would have caught it |

### Part B: Design an evaluation (35 min)

> "We want to switch this assistant from a large model to a cheaper one. Design the
> evaluation that decides whether we can."

| | |
|---|---|
| **Strong** | Same inputs for both models; a test set with answerable and unanswerable cases; defines pass criteria and thresholds before running; talks about sample size and uncertainty; considers latency and refusals, not only accuracy; defines a decision rule |
| **Red flags** | "Try a few prompts and see"; single accuracy number with no uncertainty; picks the threshold after seeing results |
| **Anchors** | 1: no structure · 2: reasonable test set, informal decision · 3: thresholds, grading method and decision rule set in advance · 4: also addresses statistical power and a staged rollout to confirm in production |

Reference: [llm-model-selection evaluation plan](https://github.com/tsriharsha402/llm-model-selection/blob/main/docs/evaluation-plan.md).

---

## Stage 5: Collaboration and judgment

Ask for specific past situations, then follow up on what *they* did, what happened, and
what they'd do differently.

| Question | Listens for |
|---|---|
| "Tell me about a time you argued against shipping something, or for delaying it." | Used evidence; proposed an alternative; disagreed and committed when overruled |
| "Tell me about an AI or data-driven feature that didn't work as expected in production." | Owns the outcome; describes detection and the fix; changed the process afterwards |
| "A stakeholder wants the assistant to answer questions outside the handbook, using the model's general knowledge. How do you respond?" | Understands the risk; offers options with tradeoffs; doesn't simply refuse or simply comply |
| "How do you explain to a non-technical leader that a model is '87% accurate'?" | Translates into user impact and cost of errors; mentions uncertainty; avoids jargon |

| | |
|---|---|
| **Red flags** | Blames others; no concrete examples; dismisses risk concerns as "blocking"; can't disagree constructively |
| **Anchors** | 1: no relevant examples · 2: examples show participation, not ownership · 3: clear ownership and learning · 4: also shows influence beyond their role, and changed how others worked |
