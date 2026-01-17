# Session Brief (Project Instance)

## Purpose

This document defines a **single execution session**.

It exists to:
- Declare the purpose and scope of one session
- Bind execution to explicit objectives and constraints
- Prevent scope creep and implicit task expansion

## Provenance

- Source template: prestage-control-plane/templates/session_brief.md
- Destination project root: /home/justin/projects/<project_name>
- Instantiated location: /home/justin/projects/<project_name>/SESSION/session_brief.md
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

- Pre-GO: This document defines the required structure only
- GO event: A fresh copy is instantiated into the project
- Post-GO: The instantiated copy is completed to authorize a session

This document **does not itself execute work**.

---

## Session Identification

- Session ID:
- Related Project:
- Related Workstream (if applicable):

---

## Session Purpose

Purpose statement:  
[Explicit description of what this session exists to accomplish]

Non-goals:  
[Explicit exclusions to prevent scope creep]

---

## Deliverables

Expected outputs:
- [Concrete deliverable]
- [Concrete deliverable]

Completion criteria:
- [Objective condition indicating session success]

---

## Scope & Constraints

In-scope:
- [Explicitly allowed activities]

Out-of-scope:
- [Explicitly forbidden activities]

Constraints:
- Time limits
- Resource limits
- Policy or posture limits

---

## Inputs & Context Surface

Allowed context:
- [Specific files or directories]

Explicitly disallowed context:
- [Anything not listed above]

---

## Authority & Control

- Session owner:
- Approval authority:
- Stop / abort authority:

---

## Risk & Failure Conditions

Known risks:
- [Risk description]

Abort conditions:
- [Condition requiring immediate stop]

---

## Session Acknowledgment

- This session is authorized **only** within the declared scope
- Work outside this brief is invalid
- Changes require a new or amended Session Brief

---

## Change Policy

- The prestage template may only be updated via **prestage control-plane governance**
- Session-specific edits belong exclusively in instantiated copies
- Historical session briefs must never be back-propagated into prestage

Prestage remains immutable by design.
