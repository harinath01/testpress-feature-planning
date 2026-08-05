# Feature Planning

A reusable prompt and source framework for taking one software feature from discovery to an approved Product Requirements Document (PRD), then to a Basecamp-ready implementation plan.

The repository can be used in:

- A normal ChatGPT conversation without creating a custom GPT.
- A ChatGPT Project with reusable Project Instructions and Sources.
- A custom GPT for reusable guided workflows.
- Any compatible AI assistant that supports instructions and reference files.

No API, application installation, or Basecamp connection is required. The Basecamp material generates planning artifacts; it does not make changes in Basecamp.

## Use the Existing GPT

The hosted **Testpress Feature Planning** GPT is available here:

[Open Testpress Feature Planning in ChatGPT](https://chatgpt.com/g/g-6a71d63be760819185a5a89f06ca7816-testpress-feature-planning)

Start a new conversation for each feature, unless you are intentionally continuing the same feature in an existing conversation. The repository remains the editable source of truth for the GPT's instructions, templates, and reference material.

## What This Repository Provides

The workflow guides a user through:

1. Identifying the current feature.
2. Determining whether a Problem Discovery Report (PDR) exists.
3. Creating or refining the PDR section by section.
4. Reviewing and approving the complete PDR.
5. Creating the PRD section by section.
6. Reviewing and approving the complete PRD.
7. Applying the Basecamp SOP to produce requested project structure and implementation to-dos.

It avoids asking for information already available in the current conversation, approved artifacts, uploaded sources, or earlier answers for the same feature.

## Repository Structure

```text
feature-planning/
├── project-instructions.md
├── prd-template.md
├── prd-section-prompts.md
├── README.md
└── references/
    ├── problem-discovery-report.md
    ├── sop-managing-engineering-feature-work-in-basecamp.md
    ├── redesign-login-signup-pages-pdr.md
    └── redesign-login-signup-pages-prd.md
```

### Core files

- `project-instructions.md` controls feature isolation, workflow sequencing, approval gates, source priority, resumption, and Basecamp readiness.
- `prd-template.md` defines the authoritative PRD section order, required or conditional status, dependencies, applicability, and exact instruction source mapping.
- `prd-section-prompts.md` contains the detailed instructions for all 18 PRD sections. Each section retains a unique `SOURCE ID` for reliable semantic retrieval.
- `README.md` explains setup, usage, and maintenance.

### Reference files

- `problem-discovery-report.md` is the canonical PDR structure.
- `sop-managing-engineering-feature-work-in-basecamp.md` governs feature-project and implementation planning after PRD approval.
- `redesign-login-signup-pages-pdr.md` and `redesign-login-signup-pages-prd.md` are examples of style, structure, formatting, and expected completeness. Their feature-specific content must not be reused for another feature.

## Use in a Normal ChatGPT Conversation

This path does not require creating a custom GPT or sharing Project knowledge.

### Recommended method

1. Download or clone this repository.
2. Start a new ChatGPT conversation for one feature.
3. Paste the complete contents of `project-instructions.md` as the first message.
4. Upload these six knowledge files to that conversation:

   - `prd-template.md`
   - `prd-section-prompts.md`
   - `references/problem-discovery-report.md`
   - `references/sop-managing-engineering-feature-work-in-basecamp.md`
   - `references/redesign-login-signup-pages-pdr.md`
   - `references/redesign-login-signup-pages-prd.md`

5. Send:

   ```text
   Help me plan a new feature. Follow the uploaded Feature Planning sources.
   ```

6. Answer the assistant's questions one logical section at a time.
7. Explicitly approve the completed PDR before starting the PRD.
8. Explicitly approve the completed PRD before requesting Basecamp planning artifacts.

If the chat cannot accept all reference files, prioritize:

1. `project-instructions.md` pasted into the conversation
2. `prd-template.md`
3. `prd-section-prompts.md`
4. `problem-discovery-report.md`
5. The Basecamp SOP when implementation planning begins
6. Example documents only when style guidance is needed

### Resume in a new conversation

Conversations do not automatically share the working feature context. To resume:

1. Paste `project-instructions.md`.
2. Upload `prd-template.md` and `prd-section-prompts.md`.
3. Upload or paste the latest approved PDR and any approved PRD sections.
4. State the exact stage to resume, for example:

   ```text
   Continue the Checkout Recovery feature from API Requirements.
   The attached PDR and preceding PRD sections are approved.
   ```

Do not expect the assistant to recover feature decisions from another conversation unless those decisions are supplied again.

## Create a ChatGPT Project

Use this option when you want the framework and sources available across multiple conversations inside one Project.

1. In ChatGPT, create a new Project named **Feature Planning**.
2. Open the Project settings or instructions editor.
3. Paste the complete contents of `project-instructions.md` into **Project Instructions**.
4. Upload the following as **Project Sources**:

   - `prd-template.md`
   - `prd-section-prompts.md`
   - `references/problem-discovery-report.md`
   - `references/sop-managing-engineering-feature-work-in-basecamp.md`
   - `references/redesign-login-signup-pages-pdr.md`
   - `references/redesign-login-signup-pages-prd.md`

5. Do not upload `project-instructions.md` as a source after pasting it into Project Instructions.
6. The README is optional and is not required for the planning workflow.
7. Start a new conversation inside the Project and send:

   ```text
   Help me plan a new feature.
   ```

8. Keep each feature in a separate Project conversation unless intentionally continuing an existing feature.
9. Test the setup by confirming that the assistant:

   - Asks for the feature and existing-PDR status only when they are not already known.
   - Uses the canonical PDR template.
   - Waits for PDR approval before starting the PRD.
   - Retrieves PRD rules by exact SOURCE ID.
   - Waits for PRD approval before Basecamp planning.
   - Lists open Basecamp readiness items instead of silently completing them.

### Update an Existing ChatGPT Project

When this repository changes:

1. Copy the latest `project-instructions.md` into the Project Instructions field, replacing the previous version.
2. Remove or replace the old copies of changed Project Sources.
3. Upload the latest `prd-template.md` and `prd-section-prompts.md` whenever either file changes.
4. Replace a reference file only when that template, SOP, or example changed.
5. Confirm that no obsolete or duplicate source remains uploaded.
6. Start a new test conversation inside the Project so previous chat context does not hide setup problems.
7. Run the validation checks listed in this README before using the updated Project for feature work.

## Create a Custom GPT

An existing configured version is available as [Testpress Feature Planning](https://chatgpt.com/g/g-6a71d63be760819185a5a89f06ca7816-testpress-feature-planning). The steps below are for maintainers who want to create their own copy or test modified repository instructions.

1. Open the GPT editor in ChatGPT.
2. Create a GPT named **Feature Planning**.
3. Paste the contents of `project-instructions.md` into the **Instructions** field.
4. Upload the following as **Knowledge**:

   - `prd-template.md`
   - `prd-section-prompts.md`
   - All four files under `references/`

5. Add optional conversation starters:

   - `Help me plan a new feature.`
   - `I already have a PDR. Help me refine it.`
   - `Resume this feature from the PRD stage.`
   - `Generate only the API Requirements.`

6. Test the PDR approval gate, PRD approval gate, individual-section requests, and missing-source fallback before sharing the GPT.

Do not upload `project-instructions.md` as Knowledge after pasting it into Instructions. The README is also not required as GPT Knowledge.

### Update the Existing Custom GPT

After modifying this repository:

1. Open the GPT editor for [Testpress Feature Planning](https://chatgpt.com/g/g-6a71d63be760819185a5a89f06ca7816-testpress-feature-planning).
2. Replace the GPT Instructions with the latest contents of `project-instructions.md` when workflow behavior changed.
3. Remove the old version of each changed Knowledge file before uploading its replacement.
4. Upload the latest `prd-template.md` and `prd-section-prompts.md` when section mappings or writing rules changed.
5. Replace only the reference files that changed.
6. Confirm that no individual prompt files or duplicate source versions are attached.
7. Test in Preview before saving or publishing the update.

## How SOURCE IDs Work

ChatGPT retrieves uploaded knowledge semantically; filenames alone are not guaranteed lookup keys. Every detailed instruction source therefore has a stable identifier such as:

```text
PRD-SECTION-EMPATHY-LENS
PRD-SECTION-API-REQUIREMENTS
PRD-SECTION-TIMELINE-PREDICTOR
```

The PRD template maps every section to:

- Its exact `SOURCE ID`
- The consolidated filename `prd-section-prompts.md`

Users do not need to type SOURCE IDs during normal use. They are internal retrieval anchors.

Do not remove, casually rename, or duplicate an existing SOURCE ID.

## Workflow Rules

### Feature isolation

Use a separate conversation for each feature unless intentionally continuing an existing one. Requirements, evidence, roles, screens, APIs, metrics, and assumptions must not leak between features.

### PDR approval gate

The assistant must complete and present the PDR before beginning the PRD. Corrections are feedback, not approval. The PRD begins only after clear approval or an explicit instruction to skip discovery.

### PRD approval gate

PRD sections are normally generated one at a time in the order defined by `prd-template.md`. The assistant may revise or generate one requested section without restarting. The complete PRD must be approved before Basecamp implementation planning.

### Basecamp readiness

Before generating implementation to-dos, the assistant checks the SOP's Feature Project Readiness Checklist. Missing requirements, designs, owners, dependencies, dates, testing details, documentation, or links remain visible as open items. This repository does not connect to or modify Basecamp.

## Modifying the Framework

### Change one PRD section

1. Find its exact SOURCE ID block in `prd-section-prompts.md`.
2. Edit only that block.
3. Preserve its eight instruction headings:

   - Purpose
   - When to Use
   - Required Inputs
   - Questions to Ask
   - Generation Instructions
   - Output Format
   - Validation Checklist
   - Avoid

4. Keep the SOURCE ID unchanged.
5. Review its purpose, dependencies, and applicability in `prd-template.md`.
6. Test both full-workflow and standalone-section generation.

### Add a PRD section

1. Confirm that a new section is genuinely required.
2. Create one unique ID using `PRD-SECTION-<DISTINCTIVE-NAME>`.
3. Add the complete section source to `prd-section-prompts.md`.
4. Add its mapping, status, purpose, dependencies, and applicability to `prd-template.md`.
5. Review ordering and downstream dependencies.
6. Test clean final-PRD assembly to ensure internal instructions do not appear in the output.

### Change PRD order

Change the order in `prd-template.md`, then review all dependency fields. Tasks must remain grounded in approved requirements and available design/API/data/edge-case information. Timeline Predictor must remain grounded in Tasks.

### Change workflow behavior

Edit `project-instructions.md` only for global behavior such as workflow stages, approvals, source priority, feature isolation, or resumption. Keep section-specific writing rules in `prd-section-prompts.md`.

## Validation Before Publishing Changes

Confirm that:

- All 18 expected PRD section SOURCE IDs are present exactly once.
- Every section prompt contains all eight standard instruction headings.
- `prd-template.md` maps every section to the correct exact SOURCE ID.
- Every suggested filename is `prd-section-prompts.md`.
- Required sections cannot disappear silently.
- Conditional sections retain a reason when marked not applicable.
- The final PRD excludes SOURCE IDs, filenames, authoring instructions, and validation checklists.
- Example feature facts have not leaked into reusable instructions.
- Tasks and Timeline Predictor remain consistent.
- Approval gates and feature isolation still work.

## Contributing

Keep changes focused and explain:

- Which workflow or section rule changed.
- Why the change is needed.
- Whether SOURCE IDs or template mappings changed.
- How the PDR, PRD, standalone-section, and Basecamp-planning paths were tested.

Avoid combining unrelated prompt changes in one pull request.

## Important Limitations

- AI-generated planning documents require human review and approval.
- The framework must not fabricate customer interviews, quotations, evidence, business impact, user roles, metrics, APIs, screens, or constraints.
- Example documents demonstrate format and completeness only.
- Basecamp outputs are planning artifacts; users must review them before creating or assigning work.
- Availability and file limits for ChatGPT features can vary by account and plan. Check the options shown in the account before setup.
