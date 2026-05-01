---
name: speckit.system-design
description: Introduces a formal System Design phase between the clarify and plan phases.
---

# speckit.system-design

## Objective
Execute a formal System Design phase based on `spec.md` to establish architectural principles, structural diagrams, and technical boundaries before implementation planning.

## Execution Rules

### 1. Ingest & Discuss (Strictly Enforced)
- **Read Context**: You must first read `spec.md`.
- **Ingest Parameters**: Incorporate the provided rules, principles, and concerns passed by the user in the command execution (`/speckit.system-design [rules] [principles] [concerns]`).
- **Discussion-First Workflow**: Initiate a conversation with the user. Ask clarifying architectural questions based on the requirements and constraints.
- **WAIT FOR APPROVAL**: You MUST wait for explicit user approval of the architectural concepts and answers before generating any diagrams.

### 2. C4 Modeling (High-Level)
- Generate the top 3 levels of the C4 model:
  1. **Context Diagram**: System boundaries, users, and external actors.
  2. **Container Diagram**: High-level applications, data stores, and microservices.
  3. **Component Diagram**: Internal components of each container.
- **Constraint**: Do NOT use C4 for code-level design.

### 3. Practical Code-Level Modeling
- For code-level logic, use practical diagrams instead of strict UML.
- Create simple, effective:
  - Flowcharts
  - Sequence diagrams
  - Class/module diagrams
- Use these to illustrate data flow and structural patterns (e.g., Gang of Four patterns if applicable).

### 4. Standalone Files
- Every diagram must be generated as a separate, native `.mmd` (Mermaid) file.
- Save these files so they are natively renderable in the IDE (e.g., `context.mmd`, `container.mmd`, `component.mmd`, `sequence.mmd`, `flow.mmd`).

### 5. Final Aggregation
- **Condition**: Only proceed to this step once the user explicitly approves the diagrams and the discussion outcomes.
- Embed the code from the `.mmd` files directly into a new `system-design.md` file based on the `templates/system-design.md` template.
- Include a "Design Decisions Log" containing all architectural decisions and rationales discussed during the chat.
