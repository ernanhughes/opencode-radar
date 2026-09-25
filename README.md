# OpenCode Radar

OpenCode Radar is a small OpenCode plugin for deciding **what deserves attention now, at what resolution, and why**.

> **Relevant does not mean new. New does not mean urgent. Urgent does not mean true.**

It refuses to collapse source importance, task relevance, novelty, accessibility, evidential validity, urgency, timing, and resolution into one vague relevance score.

## One job

```text
candidates + task + policy/state
        ↓
       RADAR
        ↓
RadarDecision[]
```

Dispositions: `SHOW`, `QUEUE`, `SIDECAR`, `SKIP`.

Requested resolutions: `GLANCE`, `BRIEF`, `DETAIL`, `SOURCE`.

Radar decides attention, not transformation. An orchestrator may ask Lens separately for the requested representation.

## Proposed OpenCode tools

- `radar_decide` — one candidate.
- `radar_batch` — bounded candidate set.
- `radar_explain` — explain a prior trace without re-deciding it.
- `radar_health` — readiness/configuration only.

## Dimensions

Keep conceptually separate:

- source importance;
- task relevance;
- novelty;
- current accessibility evidence;
- relationship to active work;
- evidential validity;
- urgency;
- cost/resolution;
- timing.

Not every dimension must exist in v0.1.

## Core result

```ts
type RadarDecision = {
  candidate: SourceRef
  disposition: "SHOW" | "QUEUE" | "SIDECAR" | "SKIP"
  resolution: "GLANCE" | "BRIEF" | "DETAIL" | "SOURCE"
  reasons: RadarReason[]
  uncertainty: string[]
  policy_version?: string
  producer: { plugin: "opencode-radar"; version: string; model?: string }
}
```

## Safe default

If evidence is insufficient to personalise or suppress safely, use a generic bounded policy rather than inventing a user profile.

"KNOWN" or equivalent means evidence that knowledge is currently accessible under specified conditions, not a stable cognitive trait.

## Composition

Radar may consume caller-supplied relationship observations or representation metadata, but it never calls Relate or Lens itself. It never grants authority.

## Status

**Design seed only.** Prove the separation of dimensions and trace before sophisticated personalisation.
