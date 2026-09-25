# OpenCode Radar — Design Contract

## Invariants

1. Source importance != task relevance.
2. Relevance != novelty.
3. Novelty != urgency.
4. Urgency != evidential confidence.
5. Preference != performance.
6. Behaviour != consent.
7. Temporary context != durable policy.
8. No suppression solely because the system claims the user "knows" something.
9. Safe generic behaviour exists when personal state is absent, disabled, uncertain, or unauthorised.
10. Decision traces are produced before downstream behaviour.
11. No direct sibling-plugin calls.

## Seed processing shape

```text
candidate
→ source/import context
→ task relevance
→ novelty/accessibility evidence
→ validity/uncertainty
→ urgency/timing
→ resolution/cost
→ policy
→ disposition + trace
```

Prefer explicit gates/decisions where dimensions are not commensurable.

## v0.1

Start with a small deterministic/hybrid policy over caller-supplied metadata:

- task relevance;
- novelty state: `NEW | ACCESSIBLE | UNCERTAIN | STALE | UNKNOWN`;
- evidential validity;
- urgency;
- cost/resolution.

Do not infer a durable personal model in v0.1.

## Safe-default test

Behaviour must remain bounded with no user policy, learning disabled, every personal field unknown, and a user who never inspects settings.

The generic baseline is allowed to beat adaptation.

## Non-goals

No summarisation, retrieval/indexing, durable memory, relation classification, action permission, personality/learning-style inference, or universal importance score.

## Acceptance test

Given a duplicate warning, a new test failure contradicting the working hypothesis, a useful non-urgent architecture note, and an unverified urgent claim, Radar separates their dispositions and explains why without inventing a persona.
