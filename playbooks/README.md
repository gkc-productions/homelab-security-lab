# Playbooks

Playbooks capture repeatable, low-noise procedures for building, operating, and troubleshooting the lab. Each playbook should be actionable by a reviewer without tribal knowledge.

## When to Write a Playbook
- Provisioning or configuration tasks that will be repeated (e.g., adding a VLAN, onboarding a data source).
- Recovery or rollback actions for common failure modes.
- Checklists for upgrades, audits, and change windows.

## Writing Guidelines
- State the objective and scope up front; keep each playbook focused on one outcome.
- List prerequisites: access needed, time estimate, impacted systems, and references.
- Use ordered steps with exact commands or screenshots; prefer idempotent actions.
- Include validation steps and expected outputs; capture rollback/cleanup instructions.
- Document decisions, assumptions, and links to architecture or vendor docs.

## Suggested Template
```
Title
Objective
Prerequisites (access, time, change ticket, references)
Steps (ordered, with commands)
Validation (how to confirm success)
Rollback/Cleanup
Notes/Lessons Learned
```
