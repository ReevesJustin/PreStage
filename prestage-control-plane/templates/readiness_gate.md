# Readiness Gate (Project Instance)

## Purpose

This document defines the **readiness evaluation criteria** that must be satisfied
before a GO decision may be declared.

It exists to ensure that:
- Canonical documents are complete and coherent
- Scope, constraints, and authority are explicit
- Execution will not occur on ambiguous or unstable foundations

## Provenance

- Source template: prestage-control-plane/templates/readiness_gate.md
- Destination project root: /home/justin/projects/<project_name>
- Instantiated location: /home/justin/projects/<project_name>/STATUS/readiness_gate.md
- Status after instantiation: EDITABLE PROJECT STATE

---

## Template vs Project Instance

### Template (in prestage-control-plane)
- Immutable within the repository
- Contains no project-specific data
- Never edited in place

### Instantiated Copy (in destination project)
- Editable project artifact
- May be filled out and updated
- Used to apply updates to canonical docs

---

## Usage Rules

- Pre-GO: This document defines **what will be evaluated**
- GO event: A fresh copy is instantiated into the project
- Post-GO: The instantiated copy is completed to record readiness status

This document **does not authorize execution** by itself.

---

## Gate Preconditions

All of the following must exist **in the destination project** before readiness
may be evaluated:

- CONTEXT.md
- STATUS.md
- DECISIONS.md
- SESSION_BRIEF.md
- Instantiated intake questionnaire

If any are missing, readiness evaluation is invalid.

---

## Readiness Criteria

### 1. Context Integrity

- [ ] CONTEXT.md exists
- [ ] Project purpose is explicitly stated
- [ ] Scope boundaries are defined
- [ ] Assumptions are documented
- [ ] Context does not contradict itself

---

### 2. Status Clarity

- [ ] STATUS.md exists
- [ ] Current phase is declared
- [ ] Known blockers are listed (or explicitly none)
- [ ] Next decision point is identified

---

### 3. Decision Hygiene

- [ ] DECISIONS.md exists
- [ ] All irreversible or binding decisions are recorded
- [ ] Decision authority is clear
- [ ] No implicit or undocumented decisions exist

---

### 4. Intake Application

- [ ] Intake questionnaire has been completed in-project
- [ ] Intake content has been applied to canonical docs
- [ ] No unresolved intake conflicts remain

---

### 5. Session Definition

- [ ] SESSION_BRIEF.md exists
- [ ] Session purpose is narrow and explicit
- [ ] Deliverables are defined
- [ ] Success conditions are stated
- [ ] Session scope aligns with CONTEXT

---

### 6. Constraint Alignment

- [ ] Constraints are explicitly restated
- [ ] Allowed context surface is defined
- [ ] Tooling posture is documented
- [ ] No forbidden capabilities are implied

---

## Gate Outcome

One of the following outcomes must be recorded **in the instantiated copy**:

- **PASS** — All criteria satisfied; GO may be declared
- **HOLD** — Gaps exist; remediation required before GO
- **FAIL** — Preconditions unmet or contradictions detected

Outcome rationale must be documented.

---

## Authority Note

- Passing this gate **permits GO**
- Passing this gate does **not** mandate execution
- Execution authority is governed elsewhere

---

## Change Policy

- The prestage template may only be modified via **prestage control-plane governance**
- Project-specific evaluations belong exclusively in instantiated copies
- Historical gate records must never be back-propagated into prestage

Prestage remains immutable by design.
