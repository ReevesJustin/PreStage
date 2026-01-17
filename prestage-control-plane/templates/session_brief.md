# Session Brief (Immutable Template)

## Purpose

This document defines a **single execution session**.

It exists to:
- Declare the purpose and scope of one session
- Bind execution to explicit objectives and constraints
- Prevent scope creep and implicit task expansion

This file is an **immutable prestage template**.

---

## Immutability Contract

- This file resides in the **prestage control plane**
- It contains **no project-specific session state**
- It is **never completed or edited in place**
- It is **copied verbatim** into a destination project directory at GO

At GO, this template is instantiated as a writable artifact in:

/home/justin/projects/<project_name>/SESSION/session_brief.md


All session-specific content belongs **only** in the destination project.

Prestage itself remains unchanged.

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

- This template may only be updated via **prestage control-plane governance**
- Session-specific edits belong exclusively in instantiated copies
- Historical session briefs must never be back-propagated into prestage

Prestage remains immutable by design.
