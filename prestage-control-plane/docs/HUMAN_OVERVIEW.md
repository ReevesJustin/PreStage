# Prestage Control Plane — Human Overview

## Purpose

This repository implements a **prestage control plane**.

Its sole purpose is to **prepare projects and workstreams for later execution**
by enforcing disciplined intake, documentation, and readiness gating.

This project **does not execute work**.
It exists to prevent premature action, scope drift, and ambiguous starts.

If you are looking for a tool that *does the work*, this is not it.  
If you want a system that ensures work starts correctly, this is.

---

## What This Project Is

Prestage is an **immutable preparation layer**.

It provides:
- Standard operating procedures (SOPs)
- Templates
- Governance rules
- Readiness criteria

All of this lives in the **prestage control plane** and is treated as **read-only**.

No project-specific state ever lives here.

---

## What This Project Does

- Captures structured intake for new projects or workstreams
- Forces intent to be written into canonical documentation
- Enforces a readiness gate before execution is permitted
- Produces a bounded Session Brief for downstream execution
- Enforces filesystem-only, non-executable behavior

In short:

**It turns “ideas” into “ready-to-execute instructions” — nothing more.**

---

## What This Project Explicitly Does NOT Do

- Execute code
- Run research
- Generate deliverables
- Modify external systems
- Access the web
- Act autonomously

All execution happens **outside** this repository.

---

## Prestage vs Project (Critical Distinction)

### Prestage Control Plane (This Repo)

- Location: this repository
- Contents:
  - SOPs
  - Templates
  - Governance rules
- Properties:
  - Immutable
  - Non-executable
  - No project state
  - No authority to act

Nothing in prestage is ever “filled out” in place.

---

### Destination Project (Created at GO)

- Location:
/home/justin/projects/<project_name>

- Contains:
- Instantiated intake
- Canonical docs
- Readiness records
- Session briefs
- Properties:
- Writable
- Project-specific
- Authoritative

All real work begins **only after** GO, in the destination project.

---

## Core Design Principles

### 1. Filesystem-Only

All state lives in markdown files.  
If it is not written to disk, it does not exist.

No memory. No hidden state. No implicit context.

---

### 2. Canonical Docs as Source of Truth

Reality is defined by canonical documents instantiated into the destination project:

- `CONTEXT.md`
- `STATUS.md`
- `DECISIONS.md`
- `WORKFLOW.md`

Templates are **structural only** until applied.

---

### 3. Strict Ordering

Steps must occur in this order:

**Intake → Apply → Readiness Gate → Session Brief → GO**

Skipping or reordering steps automatically results in **NO-GO**.

---

### 4. Delta-Only Changes

Canonical docs evolve incrementally.

- No rewrites
- No restructuring
- No retroactive cleanup
- Every change is traceable

---

### 5. Human-in-the-Loop by Design

- Agents may propose
- Humans apply
- Nothing auto-mutates state

Authority is explicit and always human-held.

---

## Supported Flows

### Flow A — New Project

Used when starting something entirely new.

Results in:
- A new destination project directory
- Canonical docs initialized from templates
- A clearly scoped initial Session Brief

---

### Flow B — New Workstream

Used when extending an existing project.

Key rules:
- Workstreams live as **sections inside canonical docs**
- No new directories are created
- No parallel project trees are allowed

---

## How to Use This Project (Human Workflow)

1. **Start Intake**
 - Use `templates/intake_questionnaire.md`
 - Decide: New Project or New Workstream

2. **Apply Intake**
 - Manually write intake data into canonical docs
 - Apply changes as deltas only

3. **Run the Readiness Gate**
 - Use `templates/readiness_gate.md`
 - Evaluate readiness against canonical docs only

4. **If GO**
 - Instantiate a Session Brief
 - Hand off to a downstream execution environment

If the gate returns **NO-GO**, fix documentation and repeat.

---

## OpenCode / AI Usage (Optional)

This repository is compatible with OpenCode and similar tools.

When launched in this repo:
- `AGENTS.md` enforces prestage-only behavior
- Execution is prohibited
- The assistant should immediately begin intake

AI tools are **assistive**, not authoritative.

---

## Who This Is For

- Engineers who want clean project starts
- Researchers who want bounded scope before exploration
- Writers who want structure before drafting
- Teams who want to eliminate “we’ll figure it out later”

---

## Mental Model

Think of Prestage as:

- A **runway**, not a plane
- A **checklist**, not a worker
- A **gate**, not a task engine

If you respect the gate, everything downstream accelerates.

---

## Final Note

If this feels slow, that is intentional.

This system trades **a small upfront cost**
for **massive downstream clarity, safety, and speed**.

---

## Recommended Test Sequence

### Phase 1 — Flow A (New Project)

**Goal:** Verify clean initialization and strict gating.

1. Start OpenCode in the repo root.
2. Confirm the assistant immediately asks:
 - New Project or New Workstream?
3. Choose New Project.
4. Complete intake using `templates/intake_questionnaire.md`.
5. Attempt readiness before applying canonical updates.
 - **Expected:** NO-GO with explicit reason.
6. Apply intake data into:
 - `CONTEXT.md`
 - `STATUS.md`
 - `DECISIONS.md` (if applicable)
7. Re-run readiness gate.
 - **Expected:** GO.
8. Generate a Session Brief.
9. Stop.

**Success criteria:**  
No execution occurred. All artifacts are traceable. No ambiguity.

---

### Phase 2 — Flow B (New Workstream)

**Goal:** Verify section-based extension without structural drift.

1. Start a new OpenCode session.
2. Choose New Workstream.
3. Point to the existing destination project.
4. Complete intake.
5. Attempt to create a new directory.
 - **Expected:** refusal or correction.
6. Apply intake data as new sections in canonical docs.
7. Run readiness gate.
8. Generate Session Brief.
9. Stop.

**Success criteria:**  
No new directories created. Canonical docs remain clean.  
Workstream exists only as sections.

---

## What to Watch For (Signal > Noise)

During both tests, note:
- Any place an agent assumes authority it should not
- Any ambiguity about who applies changes
- Any temptation to execute or generate deliverables
- Any confusion about where information “lives”

These are **design signals**, not user errors.
