# Intake Questionnaire (Project Instance)

## Purpose

This document captures **initial intent only**.

It is a **prestage intake template** used to surface scope, constraints, and intent
*prior to GO*. It is **not authoritative** and **does not permit readiness gating**
until its contents are applied to canonical project documents.

## Provenance

- Source template: prestage-control-plane/templates/intake_questionnaire.md
- Destination project root: /home/justin/projects/<project_name>
- Instantiated location: /home/justin/projects/<project_name>/CONTEXT/intake_questionnaire.md
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

- Pre-GO: This document is reviewed as a **checklist**, not filled out
- GO event: A fresh copy is instantiated into the project
- Post-GO: The instantiated copy may be edited and applied to canonical docs

This document **never becomes authoritative on its own**.

---

## Intake Classification

Intake Type: [New Project | New Workstream]

Project Name: [Required]

Workstream Name: [Required if New Workstream]

---

## Canonical Application Targets (Required)

The following canonical updates will be required during the **Apply** step
*after instantiation*:

- CONTEXT.md section to create/update: [Section header]
- STATUS.md section to create/update: [Section header]
- DECISIONS.md entry required: [Yes / No]

Flow B acknowledgment:
- Workstreams are recorded as sections inside canonical docs
- No new directories or repositories are created for workstreams

---

## Task Mode

Task Mode: [Coding | Research | Writing]

---

## Objective Definition

Objective:  
[Clear, explicit objective statement]

Out-of-Scope:  
[Explicit exclusions and non-goals]

Acceptance Criteria:  
[Concrete, measurable success conditions]

---

## Constraints and Boundaries

Constraints:  
[Hard limits: time, scope, posture, exclusions]

Allowed Context Surface:  
[Permitted files and directories only]

Tooling Posture:  
Filesystem-only. No web access. No MCP. No execution.

---

## Universal Validation Questions

- Why does this project or workstream exist?
- What does success concretely look like?
- What must explicitly NOT happen?

---

## Mode-Specific Details

### Coding
- Codebase location (path only):
- Languages / frameworks:
- Files or subsystems in scope:

### Research
- Local knowledge sources (filesystem only):
- Question boundaries:
- Required output form:

### Writing
- Topic focus:
- Intended audience:
- Structural or style constraints:

---

## Intake Acknowledgment

- This intake does **not** authorize execution
- This intake does **not** authorize readiness gating
- Readiness may only be evaluated **after** canonical docs are updated
- Canonical authority resides in CONTEXT, STATUS, and DECISIONS documents

---

## Change Policy

- The prestage template may only be updated via **prestage control-plane governance**
- Project-specific edits belong exclusively in instantiated copies
- Drift between prestage templates and project artifacts is expected and allowed

Prestage remains immutable by design.
