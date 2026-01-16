# OpenCode Rules — Workspace Router

This directory is a workspace container.
The actual prestage-control-plane project lives in:

- `prestage-control-plane/`

OpenCode must treat `prestage-control-plane/` as the effective project root
for all prestaging activity.

---

## Root Resolution Rule (Critical)

If OpenCode is started in `/home/justin/PreStage`:

- DO NOT assume `./templates` exists.
- DO NOT assume `./docs` exists.
- DO NOT search upward for additional AGENTS.md files.

All prestage-related file access MUST use paths prefixed with:

- `prestage-control-plane/`

Failure to do so will cause ENOENT errors.

---

## Canonical Path Prefix (Mandatory)

All prestage artifacts MUST be referenced as:

- `prestage-control-plane/templates/intake_questionnaire.md`
- `prestage-control-plane/templates/readiness_gate.md`
- `prestage-control-plane/templates/session_brief.md`

- `prestage-control-plane/docs/WORKFLOW.md`
- `prestage-control-plane/docs/CONTEXT.md`
- `prestage-control-plane/docs/STATUS.md`
- `prestage-control-plane/docs/DECISIONS.md`
- `prestage-control-plane/docs/DECISION_CHECKLIST.md`
- `prestage-control-plane/docs/SESSION_TEMPLATE.md`

If a file is not under `prestage-control-plane/`, it is out of scope.

---

## Operational Instruction

Preferred usage:
- Start OpenCode from `prestage-control-plane/`

Supported usage:
- If OpenCode is started from this workspace root,
  you MUST use the canonical prefixed paths above.

Immediately defer behavioral rules to:
- `prestage-control-plane/AGENTS.md`

---

## Tool Schema Constraints (Important)

When using any interactive question / prompt tool:

- The `header` field MUST be **12 characters or fewer**

Violating this constraint will cause tool failure.

Approved header examples:
- "Intake"
- "Proj/WS"
- "Project"
- "Wrkstream"
- "Objective"
- "Scope"
- "OOS"
- "Criteria"
- "Context"
- "Posture"
- "Gate"

---

## Startup Expectation

After routing is resolved, the prestage-control-plane agent MUST:

1. Ask whether the user is initiating:
   - New Project
   - New Workstream

2. Begin Intake immediately.

No execution, no gating, no file mutation.
