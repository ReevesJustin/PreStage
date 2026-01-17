# Workflow

This repository is a prestage control plane.
It defines a strict SOP for pre-staging projects and workstreams.

This repository is IMMUTABLE:
- Do not write project-specific state here.
- Do not modify canonical templates to fit a project.
- All per-project artifacts are created in a destination project directory.

This project performs NO execution.

---

## Core Invariants

- Filesystem-only posture. No web, no MCP, no execution.
- Prestage repo is immutable (templates + SOP only).
- Project-specific state is instantiated outside this repo.
- Intake artifacts are non-authoritative until instantiated into a project folder.
- Workstreams live as sections in project canonical docs (not folders).

---

## Supported Flows

### Flow A — New Project
Pre-stage a brand-new project and instantiate its project-canonical docs
in a destination project directory.

### Flow B — New Workstream
Pre-stage a new workstream for an existing project and instantiate the
workstream section updates into that project’s canonical docs.

---

## Mandatory Workflow Order (All Flows)

### Step 1 — Intake (Template Only)
- Complete `templates/intake_questionnaire.md`.
- Intake captures intent only.
- No readiness evaluation is permitted at this step.
- No files are created or modified.

### Step 2 — Readiness Gate (Template Only)
- Complete `templates/readiness_gate.md`.
- Gate evaluates whether intake is sufficiently complete to instantiate
  project artifacts.
- Gate does not modify any files.

### Step 3 — Destination Resolution (Required)
- The operator provides the destination directory for the execution project.
- For Flow A: a new project directory is created at the destination.
- For Flow B: an existing project directory is used.

### Step 4 — Project Canon Instantiation (Outside This Repo)
- Create or update project artifacts in the destination directory only.
- Minimum project-canonical artifacts:
  - `<DEST>/docs/CONTEXT.md`
  - `<DEST>/docs/STATUS.md`
  - `<DEST>/docs/DECISIONS.md`
- Produce `<DEST>/SESSION_BRIEF.md` (or equivalent) for downstream execution.

Prestage repo remains unchanged.

---

## Enforcement Rules

- Any instruction to write project state into this repo is invalid.
- A GO decision authorizes only:
  - selecting a destination directory
  - instantiating project artifacts in that destination
- Session briefs are instantiated into destination projects only.
- Workstreams are represented as sections in project canonical docs.

---

## Prohibited Actions

- Executing tasks
- Generating deliverables
- Writing project-specific state into prestage-control-plane
- Modifying prestage templates for a specific project
- Creating workstream folders (Flow B)

---

## End State

A successful prestage results in:
- A GO decision based on complete intake
- A destination project directory identified
- Project-canonical docs instantiated in the destination
- A bounded session brief instantiated in the destination
- Zero execution performed
- Zero project state written into this repo
