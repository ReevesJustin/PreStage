# Workflow

This document defines the mandatory prestage-control-plane workflow.
This project performs NO execution work. It exists solely to pre-stage
projects and workstreams using filesystem-only, delta-only operations.

All steps are mandatory and ordered. Skipping or reordering steps is prohibited.

---

## Core Invariants

- Filesystem-only posture. No web, no MCP, no execution.
- Canonical docs are the sole source of truth.
- Intake artifacts are non-authoritative until applied.
- Readiness gating is evaluated ONLY against canonical docs.
- This system pre-stages work; it does not perform work.

---

## Supported Flows

### Flow A — New Project
Used when initializing a brand-new project.

### Flow B — New Workstream
Used when adding a new workstream inside an existing project.
Workstreams are recorded as **sections inside canonical docs**.
No new directories are created for workstreams.

---

## Mandatory Workflow Order (All Flows)

### Step 1 — Intake
- Complete `templates/intake_questionnaire.md`.
- Intake captures intent only.
- Intake artifacts are NOT authoritative.
- No readiness evaluation is permitted at this step.

### Step 2 — Apply (Canonical Update)
- The operator applies intake data into canonical docs using delta-only edits.
- Required canonical targets may include:
  - `docs/CONTEXT.md`
  - `docs/STATUS.md`
  - `docs/DECISIONS.md`
- For Flow B, this means inserting or updating clearly labeled sections.
- Until this step is complete, the system state is **incomplete**.

### Step 3 — Readiness Gate
- Complete `templates/readiness_gate.md`.
- Gate evaluation MUST reference canonical docs, not intake templates.
- If canonical updates are missing or incomplete, the result is NO-GO.
- A GO decision certifies readiness for downstream execution *outside* this project.

### Step 4 — Session Brief
- Generate `templates/session_brief.md`.
- The brief must reference canonical anchors (file + section).
- The brief represents the handoff artifact to a downstream execution session.

---

## Enforcement Rules

- Readiness Gate before Apply is invalid and must return NO-GO.
- Session Briefs must not exist without a prior GO decision.
- Agents may propose changes but do not modify canonical docs.
- The operator is responsible for canonical doc updates.

---

## Prohibited Actions

- Executing tasks
- Generating deliverables
- Creating workstream folders
- Bypassing canonical documentation
- Treating intake templates as authoritative

---

## End State

A successful prestage results in:
- Canonical docs updated
- A recorded GO decision
- A bounded Session Brief
- Zero execution performed
