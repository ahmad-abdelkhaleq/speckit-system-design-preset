---
name: speckit.plan
description: Execute the implementation planning workflow using the design artifacts.
---

# speckit.plan

## Objective
Generate a comprehensive implementation plan (`plan.md`) based on the feature specification and the established system design.

## Pre-Execution Checks
**Check for System Design Phase**:
- Look for `system-design.md` in the current working directory.
- If it does NOT exist, you **MUST IMMEDIATELY ABORT** and output an error instructing the user to run `/speckit.system-design` first. Do NOT proceed to the outline or planning phase.

## Prerequisites
- `spec.md` must be completed and validated.
- `system-design.md` MUST exist, and the System Design phase must be fully completed and approved.

## Execution Rules

### 1. System Design Alignment (STRICT OVERRIDE)
- **Mandatory Reading**: You MUST read and analyze `system-design.md` before planning.
- **Strict Adherence**: The implementation tasks, technical boundaries, and module responsibilities must perfectly map to the components and modules defined in `system-design.md`.
- **No Architectural Deviations**: Do not invent new architectural patterns or flows during the planning phase. Defer to the "Design Decisions Log" in the system design.

### 2. Task Breakdown
- Break down the functional requirements from `spec.md` into concrete, actionable implementation steps.
- Group and organize these tasks by the components and modules established in the `system-design.md` C4 and structural diagrams.

### 3. Plan Generation
- Generate or update `plan.md` to outline the technical approach, step-by-step implementation guide, and testing strategy.
- Ensure all technical choices and implementation details align with the decisions documented in `system-design.md`.
