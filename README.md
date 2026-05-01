# Spec-Kit System Design Preset

A community preset for [Spec-Kit](https://github.com/spec-kit) that introduces a formal, visual **System Design Phase** strictly enforced between the specification (Clarify) and the Implementation Planning phases.

## 🌟 Why use this preset?

By default, Spec-Kit moves from gathering requirements (`/speckit.specify` & `/speckit.clarify`) straight into breaking down implementation tasks (`/speckit.plan`).

For complex systems, this can lead to the agent inventing ad-hoc architectural boundaries on the fly. This preset solves that by adding a mandatory `/speckit.system-design` command.

This command enforces a **discussion-first workflow**, stopping the agent from writing code or tasks until a formal C4 architecture (Context, Container, Component) and related behavioral flowcharts are generated via Mermaid (`.mmd`) files and explicitly approved by the developer.

## 📦 What's Included

- `commands/speckit-system-design.md`: The core command that orchestrates the architectural discussion and C4/Mermaid diagram generation.
- `commands/speckit-plan.md` (Override): A strict override for the default planning command. It ensures the plan maps 1:1 to the boundaries established in the System Design document.
- `templates/system-design.md`: A template that aggregates the architecture diagrams and design decisions log into a single source of truth.

## 🚀 Installation

Copy the `commands` and `templates` folders directly into your active Spec-Kit project repository:

```bash
cp -r preset-package/commands ./ 
cp -r preset-package/templates ./
```

*(This will merge the preset commands with your existing Spec-Kit `.specify/` configuration or root project configuration, depending on your setup).*

## 📖 Usage

### 1. Specification & Clarification
Run your standard `/speckit.specify` and `/speckit.clarify` flows to build the initial `spec.md`.

### 2. Formal System Design (NEW)
Before planning, run:
```bash
/speckit.system-design [optional constraints/rules]
```
- The agent will pause to ask you clarifying architectural questions.
- Once you approve, it generates `.mmd` diagrams natively renderable in your IDE.
- It complies everything into a `system-design.md` artifact with a Design Decisions log.

**Edge Case**: If the agent struggles to understand your architectural intent after multiple attempts, it will suggest the option to upload a handwritten chart or explicitly override its suggestions.

### 3. Implementation Planning
Run the overridden plan command:
```bash
/speckit.plan
```
- The agent will read `system-design.md` and ensure all tasks strictly adhere to the defined component boundaries.

## 🤝 Contributing

Contributions are welcome! Please open an issue or pull request if you want to improve the diagram generation logic, add new C4 features, or enhance the design-to-plan constraint mappings.
