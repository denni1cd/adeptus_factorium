# Adeptus Factorium

Adeptus Factorium is a growing library of **factory-based skills** for solving recurring problems in software repositories. Each factory provides a project-aware workflow for investigating, improving, creating, or validating a particular kind of repository work.

Game dialogue and game art are the first domains represented here. They demonstrate the approach; they do not limit what the repository can cover. Future factories can address other repository concerns when a repeatable, evidence-led workflow adds value.

## What is a factory-based skill?

A factory-based skill is a reusable workflow for one class of repository problem. It first learns how the target project actually works, then carries out focused work in traceable batches, checks the result against project-specific evidence and the user's stated goals, and records enough progress for future runs to continue reliably.

The full definition and design criteria are in [Factory-based skills](docs/FACTORY_BASED_SKILLS.md).

## Current factory catalog

| Factory | Repository work | Skills |
| --- | --- | --- |
| **Dialogue Factory** | Audit and conservatively repair authored or generated game dialogue for character, context, knowledge, and routing fit. | [Dialogue Investigator](skills/dialogue-investigator/SKILL.md), [Dialogue Factory](skills/dialogue-factory/SKILL.md) |
| **Art Factory** | Investigate, assess, create, or refine game art while respecting the game's asset pipeline and developer-approved direction. | [Art Investigator](skills/art-investigator/SKILL.md), [Art Factory](skills/art-factory/SKILL.md) |

These pairs are the initial examples. A future factory may combine investigation and execution in one skill when the work does not benefit from a separate discovery stage.

## Shared working principles

- **Learn the repository before acting.** Use its implementation, data, documentation, dependencies, and available tools as evidence. Do not assume a universal layout or workflow.
- **Keep findings separate from goals.** Record project facts and uncertainties separately from user-controlled direction, constraints, and approvals.
- **Work in bounded batches.** Review a useful unit, make only changes supported by evidence, and keep progress durable so long runs can resume.
- **Preserve sound work.** Repair the actual defect and leave unaffected code, content, or assets alone.
- **Verify the result honestly.** Use checks that fit the output, distinguish checks performed from checks unavailable, and report unresolved risks or blockers.

## Current modules

### Dialogue Factory — V0.1

Dialogue Investigator maps the game's dialogue systems, character knowledge, state, triggers, voice evidence, and relevant generation paths. It records a game-specific Dialogue Envelope and source Inventory. Dialogue Factory uses that map to review reachable contexts and chooses whether to leave a line unchanged, fix its routing, provide a needed variant, or rewrite defective content.

Typical target-game artifacts live under `.adeptus_factorium/dialogue/`: `DIALOGUE_ENVELOPE.md`, `DIALOGUE_INVENTORY.md`, `DIALOGUE_DIRECTION.md`, and `FACTORY_AUDIT.md`.

### Art Factory — V0.2 skill definitions

Art Investigator maps the project's art sources, conventions, dependencies, integration requirements, and available tools. Art Factory works from that evidence and developer-approved Art Direction to recommend, create, refine, and integrate narrowly scoped assets.

The defined workflow requires a representative produced example, independent feasibility review, reversible integration, and honest visual and technical reporting. See [the Work acceptance-test handoff](docs/WORK_ART_FACTORY_HANDOFF.md). These definitions do not claim that the Work runtime or a target game's integration has already been validated.

Typical target-game artifacts live under `.adeptus_factorium/art/`: `ART_ENVELOPE.md`, `ART_INVENTORY.md`, `ART_DIRECTION.md`, and `ART_AUDIT.md`.

## Repository structure

```text
adeptus_factorium/
├── LICENSE
├── README.md
├── docs/
│   ├── FACTORY_BASED_SKILLS.md
│   └── WORK_ART_FACTORY_HANDOFF.md
└── skills/
    ├── art-factory/
    │   ├── ART_DIRECTION_TEMPLATE.md
    │   └── SKILL.md
    ├── art-investigator/
    │   └── SKILL.md
    ├── dialogue-factory/
    │   └── SKILL.md
    └── dialogue-investigator/
        └── SKILL.md
```
