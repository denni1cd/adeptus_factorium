# Factory-based skills

## Definition

A **factory-based skill** is a reusable, repository-aware workflow for a recurring class of software-project work. It learns the target repository's actual structure, behavior, conventions, dependencies, and constraints; uses that evidence to investigate a bounded unit of work; then creates, repairs, or improves project artifacts and checks the result against the project's real requirements and the user's stated goals.

The output may be code, tests, configuration, documentation, data, dialogue, artwork, or another maintained repository artifact. A factory is organized around the kind of work it can carry out reliably, not around one industry or file type.

## The pattern built so far

Dialogue Factory and Art Factory use a shared pattern:

1. **Investigate the actual project.** Find the relevant sources, runtime or production paths, dependencies, constraints, and available tools. Separate direct evidence from inference and unknowns.
2. **Keep useful discoveries.** Record a compact, navigable map of relevant evidence, dependencies, decisions, and coverage so later work can reuse it. The current skills call these records an Envelope and Inventory.
3. **Set a meaningful scope.** Use the user's stated goals, constraints, and approvals. Do not silently invent preferences or expand a focused task into a broad rewrite.
4. **Work in reviewable batches.** Examine a coherent unit, identify a supported defect or opportunity, and make the smallest effective change. Preserve work that already fits its purpose.
5. **Check the result.** Verify the change with evidence and checks appropriate to its output. State what was checked, what was not available, what remains uncertain, and where work can resume.

This makes a factory more than a prompt that generates or edits files. It is a repeatable process for understanding the repository, doing controlled work at useful scale, and leaving an auditable result.

## Investigator and Factory roles

Both current modules have an **Investigator** and a **Factory**. The Investigator discovers how the target project works and preserves that discovery. The Factory uses it to review and change project artifacts. This split is useful when discovery is substantial or expensive, since future runs can reuse verified findings.

The split is a pattern, not a requirement. A future skill can combine discovery and execution when the project is small, the context is clear, or a separate Investigator would add little value. Any design should still ground its work in current repository evidence.

## What belongs in Adeptus Factorium

A factory belongs here when it offers a repeatable, evidence-led way to address a meaningful class of repository work. That can include investigating and repairing defects, improving quality, updating documentation, creating or integrating assets, or validating a subsystem. Game dialogue and game art are the first examples, not the boundary of the library.

A generic checklist alone is not enough. The skill should explain how to find the project-specific evidence that matters, how to make and bound decisions, how to preserve existing work, and how to tell whether the result is complete.

## Current examples

- **Dialogue Factory:** Dialogue Investigator maps dialogue sources, routes, character knowledge, voice evidence, state, and generation. Dialogue Factory checks materially different reachable contexts and leaves good lines alone while routing, varying, or rewriting only when evidence supports it.
- **Art Factory:** Art Investigator maps assets, conventions, dependencies, integration paths, and actual tool availability. Art Factory follows developer-approved direction, produces representative examples, uses independent feasibility review, and reports visual and technical verification separately.

The detailed workflows remain in their respective skill files. This page describes the shared design idea that future factories can build on.
