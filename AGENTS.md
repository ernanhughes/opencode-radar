# Build Brief for AI Agents

Implement **OpenCode Radar**, an attention router, not a general personal AI.

Read first:

1. `README.md`
2. `DESIGN.md`
3. https://github.com/ernanhughes/project-context-opencode
4. https://github.com/ernanhughes/opencode-remembering

## Priorities

Explicit dimensions, safe generic fallback, UNKNOWN/UNCERTAIN states, pre-behaviour traces, deterministic policy where possible, no hidden persona, no suppression from weak inference.

## Do not

- call Lens/Relate/Authority directly;
- add a vector database;
- create a global user profile;
- infer learning styles/personality;
- collapse dimensions to one score without evidence;
- treat urgency as truth;
- treat observed behaviour as consent.

Deliver policy/schema, pure engine, fixtures, OpenCode tools, trace/explain path, safe-default tests, generic-win tests, load check, and optional live smoke procedure.
