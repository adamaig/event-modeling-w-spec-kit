<!--
Sync Impact Report - Constitution v1.0.0 Update
================================================================
Version Change: [TEMPLATE] → 1.0.0 (Initial constitution creation)
Modified Principles: All principles created from template
Added Sections: All core principles and Event Modeling methodology compliance
Removed Sections: None (initial creation)

Templates Status:
✅ .specify/templates/plan-template.md - Constitution Check section aligns
✅ .specify/templates/spec-template.md - Testing requirements align  
✅ .specify/templates/tasks-template.md - TDD and testing structure aligns
✅ .specify/templates/agent-file-template.md - Compatible with project structure
✅ /workspace/Agents.md - TDD principles fully integrated

Follow-up TODOs: None - all placeholders resolved
-->

# Event Modeling Ruby Constitution

## Core Principles

### I. Test-Driven Development (NON-NEGOTIABLE)
TDD methodology is mandatory for all development work. The Red-Green-Refactor cycle must be strictly followed: Write failing test → Implement minimum code to pass → Refactor when tests pass. Every feature increment requires a test first. No production code without corresponding test coverage.

**Rationale**: Event Modeling requires precise behavioral specifications, which TDD enforces through executable documentation.

### II. Event Modeling Methodology Compliance
All domain logic must follow Event Modeling patterns: Commands generate Events, Events update Read Models, Queries read from Read Models. The event store is the source of truth. Commands must be validated before generating events. No direct manipulation of read models outside the event stream.

**Rationale**: Event Modeling provides clear separation of concerns and audit trails essential for complex business domains.

### III. Tidy First Structural Changes
All code changes must separate structural modifications from behavioral changes. Structural changes (renaming, extracting methods, moving code) must be completed and tested before implementing new behavior. Never mix structural and behavioral changes in the same commit.

**Rationale**: Reduces cognitive load and debugging complexity by isolating change types.

### IV. Ruby Idiomatic Design
Code must follow Ruby conventions and leverage language features appropriately. Use meaningful method names, avoid primitive obsession, prefer composition over inheritance. Embrace duck typing while maintaining clear contracts through tests.

**Rationale**: Idiomatic Ruby code is more maintainable and aligns with community best practices.

### V. Specification-Driven Development
Features must be specified using the Event Modeling notation before implementation. Orange stickies (commands), blue stickies (events), green stickies (read models), and yellow stickies (external systems) must be documented. Implementation must match the visual specification exactly.

**Rationale**: Event Modeling's visual notation prevents miscommunication and ensures complete system understanding.

## Event Store Requirements

Event storage must be append-only with immutable event records. Each event must include: event type, aggregate ID, timestamp, version number, and event data. Event versioning must handle schema evolution without breaking existing events. Replay capability is required for read model reconstruction.

## Development Workflow

All development follows the TDD cycle integrated with Event Modeling: Create Event Model → Write failing tests → Implement commands/events/read models → Ensure tests pass → Refactor structure. Code reviews must verify both test coverage and Event Modeling pattern compliance.

## Governance

This constitution supersedes all other development practices. Amendments require documentation of impact on existing Event Models and migration plan for affected components. All development decisions must be justified against these principles. Use `Agents.md` for detailed TDD and Tidy First implementation guidance.

**Version**: 1.0.0 | **Ratified**: 2025-09-29 | **Last Amended**: 2025-09-29
