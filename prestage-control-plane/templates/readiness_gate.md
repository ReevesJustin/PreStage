# Readiness Gate

This gate certifies that canonical documentation is complete
and the project or workstream is ready for downstream execution.
This project itself performs no execution.

---

## Intake Reference

Intake Type: [New Project | New Workstream]

Project:
Workstream: [If applicable]

---

## Canonical Application Verification (Mandatory)

Canonical Docs Updated: [Yes | No]

Evidence (file + section headers):
- CONTEXT.md §
- STATUS.md §
- DECISIONS.md entry: [If applicable]

If Canonical Docs Updated = No → **NO-GO (do not proceed further)**

---

## Readiness Checklist

Objective explicitly defined: [Yes | No]

Out-of-Scope explicitly bounded: [Yes | No]

Acceptance Criteria measurable and concrete: [Yes | No]

Allowed Context Surface narrowly defined: [Yes | No]

Tooling posture confirmed filesystem-only: [Yes | No]

---

## GO / NO-GO Decision

Decision: [GO | NO-GO]

Rule:
- GO is permitted ONLY if all checklist items are Yes
  AND Canonical Docs Updated = Yes.
- Any No results in NO-GO.

---

## NO-GO Remediation Guidance (Max 5)

1. [Missing or vague objective]
2. [Unbounded scope or exclusions]
3. [Incomplete acceptance criteria]
4. [Over-broad context surface]
5. [Canonical docs not updated]

---

## Gate Declaration

- This decision does not authorize execution inside this project.
- A GO decision authorizes creation of a Session Brief only.
