# Prestage Control Plane — Human Overview

## Purpose

This repository implements a **prestage control plane**.

Its sole purpose is to **prepare projects and workstreams for later execution**
by enforcing disciplined intake, documentation, and readiness gating.

This project **does not execute tasks**.
It exists to prevent premature work, scope drift, and ambiguous starts.

If you are looking for a tool that *does the work*, this is not it.
If you want a tool that ensures you start work correctly, this is.

---

## What This Project Does

- Captures structured intake for new projects or workstreams
- Forces intent to be written into canonical documentation
- Applies a readiness gate before any execution is allowed
- Produces a bounded Session Brief for downstream execution
- Enforces filesystem-only, non-executable behavior

In short:
**It turns “ideas” into “ready-to-execute instructions” — nothing more.**

---

## What This Project Explicitly Does NOT Do

- Execute code
- Run research
- Generate content
- Modify external systems
- Access the web
- Act autonomously

All execution happens **outside** this repository.

---

## Core Design Principles

### 1. Filesystem-Only
All state lives in markdown files.  
If it is not written to disk, it does not exist.

### 2. Canonical Docs as Source of Truth
The following files define reality:

- `docs/CONTEXT.md`
- `docs/STATUS.md`
- `docs/DECISIONS.md`
- `docs/WORKFLOW.md`

Templates and notes are non-authoritative until applied.

### 3. Strict Ordering
No steps may be skipped or reordered:

**Intake → Apply → Readiness Gate → Session Brief**

Violating order automatically results in NO-GO.

### 4. Delta-Only Changes
Canonical docs are updated incrementally.
No rewrites, no restructuring, no memory sprawl.

### 5. Human-in-the-Loop by Design
Agents may propose.
Humans apply.
Nothing auto-mutates state.

---

## Supported Flows

### Flow A — New Project
Used when starting something entirely new.

Results in:
- New sections in canonical docs
- A clearly scoped initial Session Brief

### Flow B — New Workstream
Used when extending an existing project.

Key rule:
- Workstreams live as **sections inside canonical docs**
- No new directories are created

---

## How to Use This Project (Human Workflow)

1. **Start Intake**
   - Use `templates/intake_questionnaire.md`
   - Decide: New Project or New Workstream

2. **Apply Intake**
   - Manually write intake data into canonical docs
   - Use delta-only edits

3. **Run the Readiness Gate**
   - Use `templates/readiness_gate.md`
   - Gate is evaluated against canonical docs only

4. **If GO**
   - Generate a Session Brief
   - Hand off to a downstream execution environment

If the gate returns NO-GO, fix documentation and repeat.

---

## OpenCode / AI Usage (Optional)

This repo is compatible with OpenCode and similar tools.

When launched in this directory:
- `AGENTS.md` enforces prestage-only behavior
- No execution is permitted
- The assistant should immediately begin intake

AI tools are **assistive**, not authoritative.

---

## Who This Is For

- Engineers who want clean project starts
- Researchers who want bounded scope before exploration
- Writers who want structure before drafting
- Teams who want to avoid “we’ll figure it out as we go”

---

## Mental Model

Think of this project as:

- A **runway**, not a plane
- A **checklist**, not a worker
- A **gate**, not a task engine

If you respect the gate, everything downstream goes faster.

---

## Final Note

If something feels slow here, that is intentional.

This project trades **a small upfront cost**
for **massive downstream clarity**.


## Recommended Test Sequence

**Phase 1 — Flow A (New Project)**

**Goal:** Verify that the system can initialize a project cleanly and enforce all gates.

1. Start OpenCode in the repo root.
2. Confirm the assistant immediately asks:
- New Project or New Workstream?
3. Choose New Project.
4. Complete the intake using templates/intake_questionnaire.md.
5. Attempt to trigger readiness before applying canonical updates.
- Expected result: NO-GO, with explicit “Apply step incomplete.”
Apply intake data into:
- docs/CONTEXT.md
- docs/STATUS.md
- docs/DECISIONS.md (if applicable)
7. Re-run the readiness gate.
- Expected result: GO.
8. Generate a Session Brief.
9. Stop.

**Success criteria:**
No execution occurred. All artifacts are traceable. No ambiguity.

---

**Phase 2 — Flow B (New Workstream)**

**Goal:** Verify section-based extension without structural drift.

1. Start a new OpenCode session.
2. Choose New Workstream.
3. Point to the project created in Phase 1.
4. Complete intake.
5. Attempt to create a folder for the workstream.
- Expected result: refusal or correction.
6. Apply intake data as new sections in canonical docs.
7. Run readiness gate.
8. Generate Session Brief.
9. Stop.

**Success criteria:**
No new directories created. Canonical docs remain clean. Workstream exists only as sections.

---

**What to Watch For (Signal > Noise)**

During both tests, note:
- Any place the model assumes authority it shouldn’t
- Any ambiguity about “who applies changes”
- Any temptation to execute or generate content
- Any confusion about where information “lives”
- These are design signals, not mistakes.