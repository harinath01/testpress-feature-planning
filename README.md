# Feature Planning

A reusable planning framework for taking one software feature from discovery to an approved Problem Discovery Report (PDR), then to an approved Product Requirements Document (PRD).

The repository is designed for constrained knowledge-file setups. The core system separates:

- workflow rules
- document structure
- section-writing guidance
- prompt files

That separation keeps the system easier to maintain when sections change or new ones are added.

## Repository Structure

```text
testpress-feature-planning/
├── README.md
├── project-instructions.md
├── templates/
│   ├── pdr-template.md
│   └── prd-template.md
├── prompts/
│   ├── pdr-prompt.md
│   └── prd-prompt.md
└── references/
    ├── redesign-login-signup-pages-pdr.md
    └── redesign-login-signup-pages-prd.md
```

## How the Files Work

### `project-instructions.md`

This is the top-level workflow file.

It defines:

- how the assistant should behave
- when to start with discovery versus resume existing work
- approval gates
- source priority
- the rule that both PDR and PRD are generated section by section
- the rule that discovery starts from the problem, not the proposed feature

This file explains the process. It does not contain all section-writing detail.

### `templates/`

Template files define document structure only.

- `templates/pdr-template.md` defines the authoritative PDR section order, required or conditional status, dependencies, and applicability.
- `templates/prd-template.md` defines the authoritative PRD section order, required or conditional status, dependencies, and applicability.

Templates are intentionally lightweight. They should answer:

- what sections exist
- what order they appear in
- which sections depend on earlier sections
- whether a section is required or conditional

Templates should not hold all the detailed writing instructions for each section.

### `prompts/`

Prompt files define how to generate each section.

- `prompts/pdr-prompt.md` contains detailed instructions for every PDR section.
- `prompts/prd-prompt.md` contains detailed instructions for every PRD section.

The section headings in a prompt file should match the section headings in its template file. The system uses section-heading matching rather than repeated filename references or per-section source IDs.

Prompt files should contain the detailed authoring rules for each section, such as:

- purpose
- when to use
- required inputs
- questions to ask
- generation instructions
- output format
- validation checklist
- avoid

### `references/`

Reference files are optional examples.

They are useful for:

- style
- formatting
- completeness expectations

They must not be used as a source of feature-specific facts for a different feature.

## Template and Prompt Separation

This repository intentionally separates templates from prompts.

Use this rule:

- template = what sections exist
- prompt = how to generate that section

This makes maintenance easier.

If you want to add a new section later:

1. Add the section to the relevant template file.
2. Add a matching section heading with detailed instructions to the relevant prompt file.

That means structure changes and authoring-rule changes stay cleanly separated.

## Workflow Summary

The workflow is:

1. Start with the problem, not the feature.
2. Create or refine the PDR section by section.
3. Stay in the current section until enough grounded context is gathered.
4. Approve the full PDR.
5. Create the PRD section by section.
6. Ensure Functional Requirements solve approved pain points.
7. Approve the full PRD.
8. Use the approved PRD as the final artifact for planning and implementation follow-through.

## Pain Points and Requirements

The framework supports traceability between discovery and requirements.

- PDR should capture stable pain point IDs such as `PAIN-001`, `PAIN-002`.
- PRD Functional Requirements should use stable IDs such as `FR-001`, `FR-002`.
- Functional Requirements should clarify which approved pain points they solve.

This helps prevent solution-first PRDs that describe features without proving why they matter.

## Using the Repository

In a project or GPT setup, the intended setup is:

- copy `project-instructions.md` into the main instructions field
- upload the files under `templates/` and `prompts/` as sources or knowledge files
- upload `references/` only when example material is useful

If file-count limits are strict, prioritize:

1. `project-instructions.md`
2. `templates/pdr-template.md`
3. `templates/prd-template.md`
4. `prompts/pdr-prompt.md`
5. `prompts/prd-prompt.md`
## Maintaining the Framework

When updating this repository:

- change `project-instructions.md` when workflow behavior changes
- change a template file when section structure or dependency changes
- change a prompt file when section-generation behavior changes
- change references only when example material should be refreshed

Keep headings aligned between each template and its matching prompt file.
