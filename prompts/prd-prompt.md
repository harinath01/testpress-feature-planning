# PRD Prompt

This file contains the detailed instructions for generating each PRD section. Match sections by exact heading with `templates/prd-template.md`.

- Keep overall workflow rules in `project-instructions.md`.
- Keep the template lightweight and place section-specific writing guidance here.
- When a new PRD section is added to the template, add a matching heading and detailed guidance in this file.
- Ask exactly one question per assistant response when clarification is needed. Treat each section's questions as an internal question bank; never display a batch of questions or a numbered questionnaire.


## Overview

## Purpose
Give all stakeholders a quick, cohesive understanding of the feature, its behavior, reason for existence, solved problem, user/system benefit, and place in the product ecosystem.

## When to Use
Required after PDR approval and before all other PRD sections. Never `Not applicable`. For standalone generation, use the approved/current feature context without restarting the workflow.

## Required Inputs
- **Mandatory:** feature identity, target users, current problem, proposed capability, intended value (normally from the approved PDR).
- **Optional:** product/ecosystem role, affected workflows, known boundaries from product sources.
- **Never invent:** customer evidence, strategic claims, users, scope, or benefits.

## Questions to Ask
Ask only for the single highest-priority missing fact essential to explain what the feature does, why it is needed, and where it fits. Ask nothing when approved context is sufficient.

## Generation Instructions
Start by explaining what the feature/product is and its role in the wider system. Cover what it does, why it exists, the problem it solves, and how it improves the experience or system. Write product-oriented, connected prose—not a mechanical feature inventory. Use plain professional language and short paragraphs with bullets only where useful.

## Output Format
- Exact heading: `## Overview`
- Concise paragraphs, optionally supported by bullets.
- Do not expose source IDs or authoring notes.

## Validation Checklist
- [ ] Purpose, behavior, problem, value, and product role are clear.
- [ ] Claims trace to approved context or are labelled assumptions.
- [ ] Terminology matches the PDR and no later-section detail is duplicated.

## Avoid
Generic product language, buzzwords, excessive implementation detail, disconnected feature lists, unsupported strategy, and invented evidence.

---


## Problem Statement

## Purpose
Define the user's present challenge, the current gap and its consequences, and why a solution is necessary without prescribing implementation.

## When to Use
Required after the approved PDR and Overview. Never `Not applicable`. A standalone request changes only this section.

## Required Inputs
- **Mandatory:** affected users, current workflow/gap, pain, impact, and evidence source.
- **Optional:** frequency, severity, workarounds, constraints.
- **Never invent:** pain, impact, customer quotations, frequency, or business cost.

## Questions to Ask
If absent, ask concretely who experiences the problem, what fails or is difficult today, and the observable consequence. Do not ask the user to repeat PDR content.

## Generation Instructions
Describe the need concisely. Highlight the user's challenge and why a solution is needed. Keep each point concrete and problem-focused; distinguish evidence from assumptions. Do not turn the section into objectives or proposed features.

## Output Format
- Exact heading: `## Problem Statement`
- Bullet list of concise statements.

## Validation Checklist
- [ ] User, gap, impact, and need are explicit.
- [ ] Every statement is supported or labelled as an assumption.
- [ ] The section does not prescribe implementation or contradict the PDR.

## Avoid
Solution design, vague pain, invented evidence or impact, generic filler, narrative sprawl, and untestable claims.

---


## Objective

## Purpose
State what the feature enables, who uses it, how it works at a high level, and the intended outcomes and benefits.

## When to Use
Required after Problem Statement. Never `Not applicable`. For standalone requests, rely on the approved problem and scope and revise only Objective.

## Required Inputs
- **Mandatory:** capability, supported users, high-level interaction/behavior, intended outcomes.
- **Optional:** outcome targets and business benefits already approved.
- **Never invent:** roles, metrics, behavior, or benefits.

## Questions to Ask
Ask only which actor, enabled action, high-level mechanism, or outcome remains materially unclear.

## Generation Instructions
Use short, scannable parts rather than one paragraph. Clearly describe what is enabled, who uses it and how, then key outcomes. Remain outcome-oriented and avoid detailed requirements or implementation.

## Output Format
- Exact heading: `## Objective`
- Short paragraphs and concise bullets where useful.

## Validation Checklist
- [ ] Enablement, users, high-level behavior, and benefits are present.
- [ ] Outcomes answer the approved problem and do not introduce scope.
- [ ] Wording is concrete and consistent.

## Avoid
Verbose prose, implementation design, feature inventories, unsupported metrics, vague aspirations, and repetition of Overview.

---


## User Stories

## Purpose
Capture primary role-based scenarios, why each matters, and measurable conditions of success.

## When to Use
Required after Objective and confirmed actors/scope. Never `Not applicable`. Independently generate or revise only requested stories using approved feature context.

## Required Inputs
- **Mandatory:** supported roles, their goals and benefits, relevant behavior and constraints.
- **Optional:** priority, permissions, exceptions, known acceptance rules.
- **Never invent:** user roles, permissions, goals, or acceptance behavior.

## Questions to Ask
Ask only for a missing primary actor, goal, benefit, or acceptance condition. Do not ask broad preference questions.

## Generation Instructions
Create 3–5 stories covering distinct relevant roles/scenarios. Use descriptive sentences exactly in the pattern `As a [type of user], I want [goal], so that [reason/benefit].` Follow each with  testable acceptance criteria. Keep titles short and meaningful for a table of contents.

## Output Format
- Exact heading: `## User Stories`
- Each story: `### <Short title>`
- Story sentence beneath the title; do not add a `User Story` subheading.
- `**Acceptance Criteria**` as normal bold text, followed by bullets.

## Validation Checklist
- [ ] There are 3–5 supported, non-duplicative stories.
- [ ] Every sentence follows the required pattern.
- [ ] Acceptance criteria are observable, measurable/testable, and consistent with scope.

## Avoid
Invented roles, solutionless aspirations, vague criteria, implementation tasks, headings named `User Story`, and acceptance criteria that merely repeat the sentence.

---


## Use Cases

## Purpose
Show how user needs are fulfilled through explicit system behavior, including prerequisites, main paths, applicable alternatives, and resulting state.

## When to Use
Required after User Stories and sufficiently defined functional scope. Never `Not applicable`. For an individual request, generate only the requested use case(s).

## Required Inputs
- **Mandatory:** actor, trigger/goal, preconditions, ordered behavior, success outcome.
- **Optional:** alternate/error paths, permissions, state changes.
- **Never invent:** actors, system capabilities, business rules, or outcomes.

## Questions to Ask
Ask only about a missing trigger, prerequisite, decision point, alternate path, or postcondition essential to an unambiguous flow.

## Generation Instructions
Create detailed but concise use cases that connect the user's goal to system behavior. Number the main flow step by step. Include alternate flows only when applicable; describe them clearly enough to test. Avoid implementation internals.

## Output Format
- Exact heading: `## Use Cases`
- Each case: `### <Short meaningful title>`
- Plain bold labels: `**Actors**`, `**Preconditions**`, `**Main Flow**`, `**Alternate Flows**` (if applicable), `**Postconditions**`
- Numbered Main Flow; concise lists elsewhere.

## Validation Checklist
- [ ] Each flow fulfills a supported story.
- [ ] Preconditions and postconditions are states, not vague statements.
- [ ] Steps are ordered, observable, and consistent with approved rules.

## Avoid
Missing required labels, unnumbered main flows, invented behavior, excessive technical detail, impossible alternate paths, and narrative blocks.

---


## Empathy Lens

## Purpose
Expose the human, behavioral, emotional, outcome-visibility, decision, risk, and lifecycle context behind the feature.

## When to Use
Required after the approved PDR, User Stories, and Use Cases. Never `Not applicable`. A standalone revision must preserve all dimensions and questions.

## Required Inputs
- **Mandatory:** primary user, current pain/workflow, intended behavior change, emotional drivers, concrete success outcomes, decisions and risks.
- **Optional:** per-instance metrics, comparison baselines, visibility surfaces, lifecycle plans.
- **Never invent:** feelings, evidence, metrics, product surfaces, configurations, or business decisions.

## Questions to Ask
Ask the minimum concrete questions needed to complete every required Q&A. Do not skip questions or merge answers. Never ask generic/system-level questions when configuration-level information is expected.

## Generation Instructions
Use strict Question → Answer form. Every answer must state what the user can see, measure, or act on in 1–3 lines. Cover all dimensions and every question below.

For Success Visibility, focus on outcomes for **this specific feature/configuration instance**, not setup activity. Include attribution (did this instance cause the result and what condition triggered it), debuggability (unused vs misconfigured vs ineffective), comparison (before/after, this/other, eligible/actual), and surface/discoverability (exact location, default visibility, and time to answer “is it working?”).

Required dimensions/questions:

1. **User Context & Pain:** Who is the primary user? What are they trying to achieve in their own words? What is frustrating or broken today?
2. **Behavioral Intent:** What behavior should change? What happens without the feature?
3. **Emotional Drivers:** Why does it matter emotionally? What anxiety, urgency, or motivation exists?
4. **Success Visibility:** What outcomes prove this specific instance works? What per-instance metrics matter? How are working/not working and misconfigured/ineffective distinguished? How is attribution established? What comparisons are expected? What business questions must the UI answer? Where is the information visible and how discoverable is it? How quickly can success be determined? What confusion or bad decisions result without visibility?
5. **Decision Enablement:** What decisions follow? What configuration parts would be adjusted?
6. **Failure & Risk Perception:** What could go wrong? What fears or unintended outcomes exist?
7. **Lifecycle Thinking:** What follows first success? How will users scale, repeat, or evolve it?

## Output Format
- Exact heading: `## Empathy Lens`
- Use `### 1. User Context & Pain` through `### 7. Lifecycle Thinking`.
- Every item exactly: `Q: <question>  ` then `A: <direct answer in 1–3 lines>`.

## Validation Checklist
- [ ] Every required question has one separate answer.
- [ ] Success visibility covers outcome, per-instance attribution, diagnostics, comparison, surface, discoverability, and decision speed.
- [ ] Answers are concrete, supported, actionable, and not generic.

## Avoid
Summaries replacing Q&A, skipped or merged questions, fabricated emotions/metrics, configuration activity as success, platform-only metrics, buried-signal ambiguity, vague phrases such as “improved outcomes,” and unsupported UI surfaces.

---


## Functional Requirements

## Purpose
Define what the system must do to achieve the objectives through clear user-visible behavior, system capabilities, rules, and data handling.

## When to Use
Required after Objective, User Stories, and Use Cases. Never `Not applicable`. Standalone revisions affect only this section and must remain consistent with approved context.

## Required Inputs
- **Mandatory:** approved objectives, flows, business rules, permissions, states, and relevant data behavior.
- **Optional:** validations, notifications, integration behavior, known constraints.
- **Never invent:** capabilities, roles, screens, APIs, rules, or technical constraints.

## Questions to Ask
Ask only about missing behavior, actor/permission, state transition, validation, or observable result needed to make a requirement testable.

## Generation Instructions
Write short, atomic, action-oriented statements. Every requirement must be measurable and testable. Focus on observable behavior and data handling. Split compound requirements. Avoid implementation technologies, internal classes, job names, and narrative prose. Before finalizing the section, confirm each requirement helps solve one or more approved pain points and flag any uncovered `PAIN-xxx` items.

## Output Format
- Exact heading: `## Functional Requirements`
- Numbered or bulleted list; one requirement per item.
- Use stable requirement IDs such as `FR-001`, `FR-002` when the feature has multiple requirements.
- For each requirement, include linked pain points such as `PAIN-001`, `PAIN-002` when that traceability is available.
- No subheadings that add table-of-contents entries.

## Validation Checklist
- [ ] Every item is atomic, observable, testable, and traceable to scope.
- [ ] Every approved pain point is covered by at least one requirement, or the gap is called out explicitly.
- [ ] Permissions, validations, states, and data behavior are explicit where relevant.
- [ ] No contradiction with stories, use cases, or PDR.

## Avoid
Untestable verbs, bundled behaviors, implementation detail, unsupported requirements, vague quality goals, narrative paragraphs, and duplicate statements.

---


## Tasks

## Purpose
Translate approved scope into an implementation sequence of independently reviewable and testable pull requests.

## When to Use
Required, but draft only after requirements and all available screen, API, data, edge-case, and constraint details are sufficiently approved. Never `Not applicable`; record unresolved dependencies instead of inventing them. A standalone regeneration updates only Tasks.

## Required Inputs
- **Mandatory:** approved requirements, acceptance criteria, known architecture/stack, screens, APIs, data changes, edge cases, testing and release needs.
- **Optional:** ownership, dependencies, design/docs links, deployment constraints.
- **Never invent:** architecture, frameworks, owners, dependencies, designs, or approved scope. The original context mentions Django; use Django-specific task framing only when Django is confirmed for the current feature.

## Questions to Ask
Ask only for missing technical context that materially changes task boundaries, such as stack, affected clients/services, migrations, API ownership, release approach, or required tests.

## Generation Instructions
Group related work into PR-sized functional areas. Typical flow is data/domain model → UI design → business/domain logic → API/UI integration, but adapt to actual scope. Each PR must be independently reviewable and testable and include applicable tests, validations, and UX/state work. Split oversized groups. Include design, documentation, QA, deployment, and release work only when supported. Do not write code.

## Output Format
- Exact heading: `## Tasks`
- Each group: `### PR 1 – <Outcome-focused title>`, sequentially numbered.
- Tasks use GitHub checkbox syntax: `- [ ] <task>`.

## Validation Checklist
- [ ] Each PR has a coherent outcome and can be reviewed/tested independently.
- [ ] Tasks cover approved requirements and relevant tests, validation, UX, data, API, release, and documentation work.
- [ ] Ordering and dependencies are feasible; no scope is invented.
- [ ] Task names and boundaries can be estimated by Timeline Predictor.

## Avoid
Implementation code, giant PRs, arbitrary stack assumptions, vague tasks, missing test work, design-only promises without approval, duplicated work, and tasks unrelated to requirements.

---


## Non-Functional Requirements

## Purpose
Define operationally observable quality expectations rather than business workflows.

## When to Use
Required after Functional Requirements and known constraints. Never `Not applicable`; include only relevant quality areas. Standalone requests revise only NFRs.

## Required Inputs
- **Mandatory:** applicable performance, security, privacy, reliability, accessibility, compatibility, and operational expectations.
- **Optional:** numeric targets, traffic/load assumptions, supported devices, compliance needs, recovery objectives.
- **Never invent:** numeric thresholds, compliance regimes, SLAs, tenant model, or platform capabilities.

## Questions to Ask
Ask for a missing measurable target or constraint only when required for a reliable requirement. Otherwise label a target as `TBD` rather than fabricating it.

## Generation Instructions
Cover only relevant areas: performance, scalability, reliability, availability, security/authorization, privacy/isolation, auditability, maintainability, observability, usability/accessibility, responsiveness/compatibility, integrity, fault tolerance/recovery, notification reliability, concurrency, search, mobile, tenant boundaries, and graceful degradation. Make every requirement clear, atomic, testable, and operationally observable.

## Output Format
- Exact heading: `## Non-Functional Requirements`
- Numbered or bulleted list only; no extra subheadings.
- Every item begins `The system shall…`

## Validation Checklist
- [ ] Every item is measurable/testable or contains an explicit `TBD` target.
- [ ] Requirements concern qualities, not functional workflows.
- [ ] Relevant security, access, privacy, tenant, accessibility, recovery, and observability needs are addressed.

## Avoid
“Should,” “fast,” “scalable,” or other vague language; invented targets; framework/queue/database internals; compound items; unsupported compliance; and narrative paragraphs.

---


## Information Architecture / Navigation

## Purpose
Define how users find, enter, understand, and move through feature content across roles and devices.

## When to Use
Conditional after stories, use cases, and functional requirements. Mark `Not applicable` with a reason if no navigation, route, entry point, or discoverability changes. Standalone generation uses current approved context only.

## Required Inputs
- **Mandatory when applicable:** roles, destinations/pages, hierarchy, entry points, primary journeys, visibility/access rules.
- **Optional:** breadcrumbs, search, deep links, mobile behavior, empty-state paths, cross-links.
- **Never invent:** routes, menu placement, screens, role visibility, or product hierarchy.

## Questions to Ask
Ask only which user enters from where, required parent/child relationships, role visibility, or cross-navigation remains unknown.

## Generation Instructions
Focus on navigation structure, page hierarchy, entry points, workflows, role-based visibility, information grouping, and movement. Include relevant sidebar/top-nav/dashboard entry points, global vs contextual navigation, breadcrumbs, search, empty states, deep links, restrictions, cross-links, and mobile consistency. Separate member/admin behavior when applicable. Describe user mental models, not UI styling or frontend implementation.

## Output Format
- Exact heading: `## Information Architecture / Navigation`
- Concise bullets under only useful subheadings such as Navigation Groups, Route/Page Structure, Role Visibility Matrix, Journey Entry Points, Cross-Navigation, and Mobile Considerations.
- A compact table may be used for role visibility.

## Validation Checklist
- [ ] Every destination has a supported entry point and access rule.
- [ ] Hierarchy, discoverability, deep-link behavior, and role differences are clear.
- [ ] Navigation aligns with screens and workflows.

## Avoid
Invented screens/routes, styling/component commentary, backend detail, narrative strategy, inaccessible dead ends, and unexplained role visibility.

---


## Screen Definitions

## Purpose
Describe every in-scope user-facing screen from a workflow perspective: why it exists, who uses it, what appears, what can be done, how it is reached, and how states/access behave.

## When to Use
Conditional after applicable IA, Use Cases, and Functional Requirements. Mark `Not applicable` if there are no screen/interface changes. Independently generate only requested screens.

## Required Inputs
- **Mandatory when applicable:** screen inventory, purpose, users, displayed information, actions, entry points, states, access rules.
- **Optional:** mobile considerations, contextual/cross-navigation, dynamic conditions, notes.
- **Never invent:** screens, fields, actions, states, permissions, or designs.

## Questions to Ask
Ask only for a missing screen boundary, actor, displayed information, action, state, entry path, or access decision.

## Generation Instructions
Cover relevant dashboards, lists, details, forms, activity/history, notifications, empty/error/loading/restricted/search states, mobile behavior, contextual actions, and role-specific visibility. Focus on what users can see and do; make dynamic states observable. Avoid backend and styling detail.

## Output Format
- Exact heading: `## Screen Definitions`
- Each screen: `### <Screen/Page Name>`
- Plain bold labels: `**Purpose**`, `**Primary Users**`, `**Key Information Displayed**`, `**Primary Actions**`, `**Navigation Entry Points**`, `**Possible States**`, `**Access Rules**`, and optional `**Notes**`.
- Use concise prose or bullets beneath labels.

## Validation Checklist
- [ ] Every supported screen includes all required labels.
- [ ] Loading, empty, error, restricted, and relevant domain states are covered.
- [ ] Actions, entry points, and access rules match IA, use cases, and roles.

## Avoid
Invented screens, fields, or permissions; large paragraphs; CSS/component/framework detail; unexplained states; and visual styling commentary unless requested.

---


## API Requirements

## Purpose
Define implementation-agnostic, observable API responsibilities and security boundaries for the feature.

## When to Use
Conditional after Functional Requirements, actors, permissions, and applicable screens. Mark `Not applicable` if no API or API contract changes. A standalone request generates/revises only the relevant API group.

## Required Inputs
- **Mandatory when applicable:** API consumers/actors, operations, access levels, request intent, response intent, validations, scope/ownership, errors, security and tenant rules.
- **Optional:** pagination, search/filter/sort, transitions, idempotency, concurrency, bulk behavior, notifications, audits.
- **Never invent:** endpoints, payload fields, authentication model, permissions, tenancy, error codes, or integrations.

## Questions to Ask
Ask only for missing consumers, operation boundaries, authorization/ownership, tenant scope, validation, state transitions, or required error behavior.

## Generation Instructions
Group related APIs logically. Cover listing/detail/create/update/delete and self-service/admin/public/internal behavior where relevant. Describe request/response intent, access, validation, visibility, errors, ownership, and tenant enforcement. Add pagination, filtering, sorting, idempotency, concurrency, notification, audit, or bulk expectations only when applicable. Keep behavior testable and avoid controller/ORM/service/queue internals.

## Output Format
- Exact heading: `## API Requirements`
- Each API/group: `### <Logical API Group>`
- Plain bold labels: `**Purpose**`, `**Actors / Consumers**`, `**Required Access Level**`, `**Request Behavior**`, `**Response Behavior**`, `**Validation Rules**`, `**Error Conditions**`, `**Security Considerations**`, optional `**Notes**`.

## Validation Checklist
- [ ] Actor, authentication, authorization, ownership, visibility, and tenant boundaries are explicit.
- [ ] Request/response behavior, validation, and errors are observable and testable.
- [ ] Member-safe, admin, public, and internal responsibilities are distinguished where relevant.

## Avoid
Invented endpoints/payloads, missing permission or tenant boundaries, framework internals, ambiguous ownership, vague errors, and unsupported integrations.

---


## Data & Entity Considerations

## Purpose
Explain the business meaning, boundaries, ownership, relationships, lifecycle, visibility, integrity, and audit needs of affected domain objects.

## When to Use
Conditional after Functional and applicable API Requirements. Mark `Not applicable` when no persistent business data, entity lifecycle, relationship, or visibility rule changes. Standalone generation covers only requested entities.

## Required Inputs
- **Mandatory when applicable:** entity purpose, owner/tenant, key business attributes, relationships, lifecycle/states, visibility, integrity, history/audit needs.
- **Optional:** retention, archival/soft deletion, uniqueness, computed values, inheritance, notification relationships.
- **Never invent:** entities, fields, relationships, tenant model, retention policy, or state transitions.

## Questions to Ask
Ask only about missing ownership, scope, relationship, lifecycle transition, uniqueness/integrity, retention, or audit behavior.

## Generation Instructions
Describe domain meaning rather than storage design. Cover relevant ownership, tenant association, relationships, lifecycle, visibility/access, retention/history, derived data, state transitions, uniqueness, audit-sensitive fields, and cross-entity consistency. Explain how entities behave over time and preserve important history.

## Output Format
- Exact heading: `## Data & Entity Considerations`
- Each entity: `### <Entity/Domain Object>`
- Plain bold labels: `**Purpose**`, `**Ownership**`, `**Key Attributes**`, `**Relationships**`, `**Lifecycle Considerations**`, `**Visibility Rules**`, `**Integrity Constraints**`, `**Historical or Audit Considerations**`, optional `**Notes**`.

## Validation Checklist
- [ ] Boundaries, ownership, tenant scope, relationships, and lifecycle are explicit.
- [ ] Integrity, visibility, deletion/retention, and audit behavior are testable.
- [ ] Entities align with APIs, requirements, and approved terminology.

## Avoid
ORM annotations, table schemas, indexes, migrations, framework classes, repository patterns, invented entities/fields, missing ownership, and database-first prose.

---


## Edge Cases

## Purpose
Define realistic exceptional and boundary scenarios with observable expected behavior, user impact, and recovery.

## When to Use
Required after use cases, requirements, and relevant UI/API/data rules. Never `Not applicable`. Standalone requests add or revise only Edge Cases.

## Required Inputs
- **Mandatory:** critical workflows, states, permissions, validations, dependencies, and failure modes supported by context.
- **Optional:** concurrency, retry, offline/degraded behavior, timing, restoration, pagination/search boundaries.
- **Never invent:** product capabilities, tenant rules, recovery mechanisms, or unsupported failure modes presented as facts.

## Questions to Ask
Ask only about an unresolved high-impact outcome or recovery policy (for example concurrent actions, expired access, duplicate requests, or partial completion).

## Generation Instructions
Cover relevant invalid actions, concurrency/races, revoked access, permission conflicts, tenant isolation, duplicates/idempotency, partial transitions, empty/missing/archived data, stale UI/session expiry, cross-device changes, notification timing, pagination/search boundaries, retries/restoration, degraded connectivity, and long-running actions. State what realistically goes wrong and the expected user/system result; include recovery when relevant.

## Output Format
- Exact heading: `## Edge Cases`
- Numbered or bulleted cases; a `### Edge Case: <Name>` may be used for clarity.
- For each: `**Scenario**`, `**Expected System Behavior**`, `**User Impact**`, optional `**Recovery or Resolution Behavior**`.

## Validation Checklist
- [ ] Cases are realistic, observable, testable, and operationally meaningful.
- [ ] Both user-facing and state-consistency risks are covered.
- [ ] Relevant permission, ownership, tenant, concurrency, and recovery rules are explicit.

## Avoid
“Handle errors gracefully,” invented recovery, implementation internals, duplicate happy paths, missing user impact, generic hypotheticals, and untestable outcomes.

---


## Success Metrics

## Purpose
Define measurable feature outcomes that show value, support comparisons, and diagnose adoption, discoverability, permission, reliability, or workflow problems.

## When to Use
Required after Objective, Functional Requirements, and Empathy Lens. Never `Not applicable`. A standalone review must preserve alignment with current objectives and scope.

## Required Inputs
- **Mandatory:** desired outcomes, eligible population, observable events/results, attribution method, comparison/baseline, diagnostic questions.
- **Optional:** approved targets, segments, reporting surface, evaluation window.
- **Never invent:** baselines, targets, telemetry, reporting screens, or causal evidence.

## Questions to Ask
Ask only for missing outcome definitions, denominators, attribution, baseline/comparison, target, evaluation window, or diagnostic use. Use `TBD` for unknown targets rather than fabricating them.

## Generation Instructions
Use outcome metrics, not activity/vanity counts. Make metrics attributable to this feature or configuration and comparative where applicable (before/after, eligible/active, available/used, segment/device). Include diagnostics that distinguish unused, undiscoverable, misconfigured/permission-blocked, broken, and ineffective. Include member/user and administrative/operational outcomes where relevant. State where outcomes are visible and how quickly success can be assessed when that surface is approved.

## Output Format
- Exact heading: `## Success Metrics`
- Numbered/bulleted metrics or `### <Metric Name>` entries.
- Each metric uses plain bold labels: `**Metric Name**` (if not the h3), `**Definition**`, `**Why It Matters**`, `**Success Indicator**`, optional `**Diagnostic Value**`.

## Validation Checklist
- [ ] Each metric has a numerator/denominator or otherwise precise definition.
- [ ] Outcomes align with Objective and requirements and are attributable and comparative.
- [ ] Targets are sourced or `TBD`; diagnostic value distinguishes likely causes.

## Avoid
Dashboard visits as success, vanity metrics, vague “better engagement,” invented thresholds, configuration activity as outcome, platform-only measures when per-instance attribution is needed, and telemetry implementation detail.

---


## Non-Goals

## Purpose
Prevent expectation mismatch by stating related capabilities, roles, workflows, integrations, or qualities intentionally excluded from the current delivery.

## When to Use
Required after approved scope and Functional Requirements. Never `Not applicable`. Standalone requests revise only exclusions and must not silently change scope.

## Required Inputs
- **Mandatory:** approved scope boundaries and intentionally deferred/excluded capabilities.
- **Optional:** unsupported roles, platforms, integrations, reports, automation, migration, or advanced behavior.
- **Never invent:** exclusions, stakeholder decisions, future commitments, or limitations.

## Questions to Ask
Ask only about a specific adjacent capability whose inclusion is ambiguous and materially affects expectations. Do not solicit an unconstrained wish list.

## Generation Instructions
Write direct, concise, testable exclusions. Use forms such as `The feature will not…`, `The system will not…`, or `Support for … is out of scope.` Clearly separate current scope from future possibilities. Ensure exclusions do not contradict approved requirements.

## Output Format
- Exact heading: `## Non-Goals`
- Numbered or bulleted list; one explicit exclusion per item.

## Validation Checklist
- [ ] Every non-goal is intentional, specific, and supported.
- [ ] No item contradicts requirements or disguises an unresolved decision.
- [ ] Deferred work is not presented as committed.

## Avoid
Vague phrases such as “advanced reporting is excluded,” invented scope cuts, implementation chores, duplicate requirements, promises, and mixing roadmap ideas into current scope.

---


## Future Enhancements

## Purpose
Record realistic capabilities that logically extend the current feature and explain their user or business value without turning them into commitments.

## When to Use
Conditional after current scope and Non-Goals. Mark `Not applicable` when no evidence-based extension is useful or the user excludes roadmap ideas. Standalone generation changes only this section.

## Required Inputs
- **Mandatory when applicable:** a supported future capability, its connection to current scope, and expected user/business value.
- **Optional:** deferred workflows, scalability opportunities, likely future expectations.
- **Never invent:** roadmap commitments, timelines, strategic priorities, customer demand, or promised capabilities.

## Questions to Ask
Ask only whether a known deferred capability should be recorded and what value it would add. Do not ask broad ideation questions when no evidence exists.

## Generation Instructions
Describe plausible evolution such as automation, personalization, analytics, cross-device/offline/mobile behavior, discovery, bulk/self-service controls, reporting, preferences, integrations/APIs, accessibility/localization, permissions, or lifecycle automation only when logically connected and supported. State value. Use tentative language and keep current scope clearly separate.

## Output Format
- Exact heading: `## Future Enhancements`
- Numbered or bulleted list.
- Each item states the future capability and its value; use wording such as `Future versions may…`, `The platform may later…`, or `Support for … may be added…`.

## Validation Checklist
- [ ] Every idea extends the current feature and states concrete value.
- [ ] No item is phrased as approved scope, promise, priority, or timeline.
- [ ] Items align with Non-Goals and do not contradict decisions.

## Avoid
“More features later,” invented demand, committed language, dates, unrelated brainstorming, implementation detail, and restating current requirements.

---


## Timeline Predictor

## Purpose
Estimate the approved PR-sized task breakdown in lean engineering hours and show dependencies, delivery duration, and parallelization.

## When to Use
Conditional after Tasks are approved and dependencies/constraints are known. Mark `Not applicable` when estimation is not requested, scope is insufficient, or another method is used. Standalone estimation must use the current approved task list rather than inventing a new plan.

## Required Inputs
- **Mandatory:** approved atomic tasks, dependencies, current technical context, estimator assumptions.
- **Default assumptions from source:** one engineer with 1–2 years' experience using AI-assisted coding; MVP/core functionality; eight-hour workdays; asynchronous review with no wait-time overhead.
- **Never invent:** missing tasks, team availability, hidden scope, or certainty. Surface differences from default assumptions.

## Questions to Ask
Ask only when team size/experience, MVP scope, working-day length, task list, or a major dependency differs or is unknown enough to materially change the estimate.

## Generation Instructions
Estimate tightly in hours: simple CRUD/model/migration/UI tasks `0.5–2`; medium forms/serializers/validations/small background jobs `2–4`; complex async orchestration/export/integration testing `4–6` maximum. Split larger work into atomic PRs instead of inflating estimates. Multiple PRs may fit one day. Do not add asynchronous code-review wait. Keep estimates consistent with Tasks and note dependencies and uncertainty.

## Output Format
- Exact heading: `## Timeline Predictor`
- Table columns exactly: `Task | Estimated Duration (hrs) | Dependencies | Notes`.
- Then `### Roll-up Summary` with total engineering hours.
- `### Approximate Delivery Time` with calendar workdays at 8 hours/day and assumptions.
- `### Opportunities for Parallelization` with feasible concurrent work.

## Validation Checklist
- [ ] Every estimate maps to an approved task; every approved task is represented.
- [ ] Oversized work is split; arithmetic and dependency ordering are correct.
- [ ] Total hours, workdays, and parallelization agree with the table and stated assumptions.

## Avoid
Padding, review wait time, independent speculative scope, estimates above six hours without splitting, false precision, calendar promises, and inconsistency with Tasks.
