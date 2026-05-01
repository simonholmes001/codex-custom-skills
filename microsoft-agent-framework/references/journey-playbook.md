# Journey Playbook (Architecture Evolution)

Use this guide when users follow the "journey" learning path and need practical build sequencing.

## Recommended Progression

1. Add tools.
2. Add skills.
3. Add middleware.
4. Add context providers.
5. Use agents as tools.
6. Add agent-to-agent.
7. Move to workflows.

## Stage Outcomes

- Tools: deterministic capability extension with explicit contracts.
- Skills: reusable, discoverable capability packaging.
- Middleware: policy, safety, telemetry, and reliability cross-cuts.
- Context providers: runtime grounding with external state.
- Agents as tools: composition without full protocol hosting.
- A2A: cross-service/framework interoperability.
- Workflows: deterministic orchestration and resumability.

## Decision Gates

- Do not advance stage just because it is available.
- Move to next stage only when current stage cannot meet quality, security, or scale requirements.

## Production Readiness Per Stage

- Add telemetry and approvals before scaling autonomy.
- Version tool/skill/context contracts.
- Add rollback plan before introducing A2A or workflow-wide changes.
