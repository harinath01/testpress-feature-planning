# SOURCE ID: PRD-AUTHORITATIVE-TEMPLATE

# Product Requirements Document Authoring Template

## Authoring Rules

- Use the sections below in this exact order in the assembled PRD. Required sections cannot be omitted.
- Mark a conditional section `Not applicable` only when genuinely irrelevant. Never silently remove a section; retain its heading and a concise reason unless the user explicitly requests otherwise.
- Satisfy dependencies before generating dependent sections where practical.
- Tasks must derive from approved requirements, screens, APIs, data considerations, edge cases, and constraints. Timeline Predictor must estimate the approved task breakdown, not an independent speculative plan.
- Success Metrics must align with Objective and Functional Requirements. Non-Goals must not contradict scope. Future Enhancements are not current commitments.
- The final PRD contains only feature-specific content—no source IDs, filenames, instructions, checklists, or workflow notes.

## Overview

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-OVERVIEW`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Explain what the feature is, what it does, why it exists, the problem it solves, and its strategic product role.  
**Depends on:** Approved PDR  
**Not applicable when:** Never

## Problem Statement

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-PROBLEM-STATEMENT`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Define the concrete user challenge, current gap, impact, and need for a solution.  
**Depends on:** Approved PDR; Overview  
**Not applicable when:** Never

## Objective

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-OBJECTIVE`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** State what the feature enables, who uses it, how it works at a high level, and intended outcomes.  
**Depends on:** Problem Statement  
**Not applicable when:** Never

## User Stories

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-USER-STORIES`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Express primary role-based goals and testable acceptance criteria.  
**Depends on:** Objective; approved actors and scope  
**Not applicable when:** Never

## Use Cases

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-USE-CASES`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Describe end-to-end system behavior through main and alternate flows.  
**Depends on:** User Stories; Functional scope  
**Not applicable when:** Never

## Empathy Lens

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-EMPATHY-LENS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Analyze human context, intent, emotion, visible success, decisions, risks, and lifecycle in strict Q&A form.  
**Depends on:** Approved PDR; User Stories; Use Cases  
**Not applicable when:** Never

## Functional Requirements

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-FUNCTIONAL-REQUIREMENTS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Define atomic, observable, testable system capabilities and behaviors.  
**Depends on:** Objective; User Stories; Use Cases  
**Not applicable when:** Never

## Tasks

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-TASKS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Break approved scope into independently reviewable and testable PR-sized work.  
**Depends on:** Functional Requirements and available approved design, API, data, edge-case, and constraint details  
**Not applicable when:** Never; defer drafting until dependencies are sufficiently defined

## Non-Functional Requirements

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-NON-FUNCTIONAL-REQUIREMENTS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Specify measurable operational and quality expectations.  
**Depends on:** Functional Requirements; known technical/product constraints  
**Not applicable when:** Never

## Information Architecture / Navigation

**Status:** Conditional  
**Instruction source ID:** `PRD-SECTION-INFORMATION-ARCHITECTURE`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Define hierarchy, entry points, navigation, discoverability, role visibility, and cross-navigation.  
**Depends on:** User Stories; Use Cases; Functional Requirements  
**Not applicable when:** The feature creates no user-facing navigation, route, entry point, or discoverability change

## Screen Definitions

**Status:** Conditional  
**Instruction source ID:** `PRD-SECTION-SCREEN-DEFINITIONS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Define each user-facing screen's purpose, users, content, actions, entry points, states, and access.  
**Depends on:** Information Architecture when applicable; Use Cases; Functional Requirements  
**Not applicable when:** The feature has no user-facing screen or interface changes

## API Requirements

**Status:** Conditional  
**Instruction source ID:** `PRD-SECTION-API-REQUIREMENTS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Define observable API responsibilities, access, validation, scope, errors, security, and tenant boundaries.  
**Depends on:** Functional Requirements; actors; permissions; Screen Definitions when UI consumes APIs  
**Not applicable when:** No API is introduced or changed and no existing API contract is affected

## Data & Entity Considerations

**Status:** Conditional  
**Instruction source ID:** `PRD-SECTION-DATA-ENTITY-CONSIDERATIONS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Define domain meaning, ownership, relationships, lifecycle, visibility, integrity, and audit behavior.  
**Depends on:** Functional Requirements; API Requirements when applicable  
**Not applicable when:** The feature adds or changes no persistent business data, entity lifecycle, relationship, or visibility rule

## Edge Cases

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-EDGE-CASES`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Specify realistic failure, boundary, concurrency, permission, and recovery behavior.  
**Depends on:** Use Cases; Functional Requirements; relevant screens, APIs, and data rules  
**Not applicable when:** Never

## Success Metrics

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-SUCCESS-METRICS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Define measurable, attributable, comparative, and diagnostic outcome measures.  
**Depends on:** Objective; Functional Requirements; Empathy Lens  
**Not applicable when:** Never

## Non-Goals

**Status:** Required  
**Instruction source ID:** `PRD-SECTION-NON-GOALS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** State intentional exclusions that prevent scope ambiguity.  
**Depends on:** Approved scope; Functional Requirements  
**Not applicable when:** Never

## Future Enhancements

**Status:** Conditional  
**Instruction source ID:** `PRD-SECTION-FUTURE-ENHANCEMENTS`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Record plausible future capabilities without committing them to current scope.  
**Depends on:** Non-Goals; current scope  
**Not applicable when:** No evidence-based future extension is useful or the user elects not to include roadmap ideas

## Timeline Predictor

**Status:** Conditional  
**Instruction source ID:** `PRD-SECTION-TIMELINE-PREDICTOR`  
**Suggested filename:** `prd-section-prompts.md`  
**Purpose:** Estimate approved PR-sized tasks in lean engineering hours and summarize delivery and parallelization.  
**Depends on:** Approved Tasks; relevant dependencies and constraints  
**Not applicable when:** Estimation is not requested, task scope is not sufficiently defined, or the team uses another estimation process

## Missing-source fallback

If a detailed section source cannot be located, use the section's purpose, dependencies, and output expectations above. Do not invent strict formatting rules that are absent. Identify the missing source when it materially reduces confidence or completeness, and ask for direction only when reliable output is otherwise impossible.
