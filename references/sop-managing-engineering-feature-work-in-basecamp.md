# SOP: Managing Engineering Feature Work in Basecamp

## 1. Purpose

To ensure that every engineering feature has a clear and dedicated workspace where its requirements, design decisions, implementation tasks, discussions, documentation, and progress can be easily found and tracked.

This prevents feature-related information from becoming buried inside old, generic, or product-level Basecamp projects.

## 2. Scope

This SOP applies to engineering and development work across all company products and internal systems.

It covers:

* New product features
* Major feature enhancements
* Significant technical initiatives
* Large refactoring or migration projects
* Engineering work involving multiple tasks, people, or stages

Small bug fixes, routine maintenance, and minor changes may continue to be tracked in the relevant existing project unless a separate project is required for clarity.

## 3. Core Rule

Every substantial feature must be managed in its own Basecamp project.

Do not create feature implementation to-dos inside:

* Old or legacy projects
* General product projects
* Catch-all engineering projects
* Unrelated feature projects
* Campfire conversations without an associated project

A product may contain multiple features. Therefore, the product name alone is not sufficient as the project structure for feature implementation.

## 4. Before Creating a Feature To-do

Before creating any feature-related to-do:


1. Search Basecamp to determine whether a dedicated project already exists for the feature.
2. If the project exists, create all related to-dos and discussions inside it.
3. If the project does not exist, create one using the approved feature project template.
4. Do not temporarily add the work to a generic project with the intention of organising it later.

The correct project must be identified or created before implementation work is assigned.

## 5. Creating a Feature Project

A new feature project must be created using the approved Basecamp project template.

The project name should clearly identify:

* The product or system
* The feature or initiative

Recommended naming format:

**\[Product/System\] – \[Feature Name\]**

Examples:

* Testpress – Abandoned Cart Conversations
* TPStreams – Viewer Analytics
* TPSentinel – System Compatibility Check
* Internal Tools – Leave and Reimbursement Management

Avoid vague project names such as:

* New Feature
* Development Tasks
* Pending Changes
* Improvements
* Phase 2

## 6. Required Project Structure

Every feature project must contain the standard sections provided by the template.

At minimum, it must include:

* Product Requirements Document — PRD
* Problem Discovery Report/Document — PDR
* Implementation to-dos
* Relevant discussions and decisions
* Design links
* Technical documentation
* Testing and release-related information

The template must not be removed or replaced with an unstructured project.

## 7. PRD and PDR Maintenance

The PRD and PDR must not remain as empty placeholders.

### PRD

The PRD should describe:

* **Overview of the feature**, including what it is and why it exists (e.g., what capability it introduces and what it enables in the product)
* **Problem statement**, clearly describing the user pain points and current gaps (what users cannot do today and why it matters)
* **Objectives**, including:
  * What the feature enables
  * Who the target users are
  * How the system is expected to behave at a high level
  * Key benefits and outcomes
* **User stories**, describing user goals and expected interactions with clear acceptance criteria
* **Use cases**, detailing step-by-step flows, preconditions, alternate flows, and postconditions
* **Empathy lens**, capturing user context, intent, emotional drivers, success signals, risks, and decision-making needs
* **Functional requirements**, specifying system-level behaviors and rules the implementation must satisfy
* **Scope definition**, including:
  * What is included in the feature
  * What is explicitly out of scope
  * Any constraints or limitations that must be respected during implementation

### PDR

The PDR should capture:

* Customer details and interview metadata (customer name, date, interviewer(s), and feature/topic discussed)
* Context of the customer's problem and why the feature is being considered
* Customer background and how they currently use the product
* Detailed interview notes covering:
  * Current workflow
  * Pain points
  * Business impact
  * Customer expectations
  * Constraints or limitations
* Key insights derived from the interview
* Product and design decisions informed by customer feedback
* User flows and expected behaviour
* Interface behaviour and UX considerations
* Relevant mock-ups, prototypes, or design links
* Alternatives considered during solution exploration
* Final decisions along with their rationale

The feature owner must ensure that these documents are updated whenever requirements or decisions change.

Links to external documents, designs, prototypes, technical specifications, and related discussions must be added to the appropriate section of the project.

## 8. Managing Implementation Work

All implementation work associated with the feature must be created and tracked inside the feature project.

This includes:

* Backend tasks
* Frontend tasks
* Mobile application tasks
* Infrastructure tasks
* Design tasks
* Quality assurance tasks
* Documentation tasks
* Deployment and release tasks

Each to-do must have a clearly defined due date assigned at the time of creation.

To-do descriptions must contain enough context for the assignee to understand the expected outcome.

Important decisions must not exist only inside Campfire messages, personal chats, calls, or meetings. They must be documented in the relevant feature project.

## 9. Moving Misplaced Work

When feature-related work is found in an old, generic, or incorrect project:


1. Identify the correct feature project.
2. Create the feature project from the template if it does not already exist.
3. Move or recreate the to-dos in the correct project.
4. Preserve all relevant descriptions, comments, attachments, assignees, and due dates.
5. Add links to any relevant historical discussions.
6. Close or remove the misplaced to-dos after confirming that no information has been lost.

Do not continue adding new work to an incorrect project merely because earlier work was already added there.

## 10. Responsibilities

### Feature Owner

The feature owner must:

* Ensure that a dedicated project exists.
* Ensure that the approved template is used.
* Maintain the PRD and PDR.
* Keep the scope and acceptance criteria current.
* Ensure that all feature-related work is tracked in the correct project.

### Project Coordinator or Product Manager

The coordinator or product manager must:

* Verify that the project structure is complete.
* Ensure that relevant documents and links are available.
* Move misplaced work to the correct project.
* Ensure that decisions and requirement changes are documented.

### Engineering Team Members

Engineering team members must:

* Check the project before creating a feature-related to-do.
* Avoid adding feature work to generic or legacy projects.
* Update the relevant documentation when implementation decisions affect the feature.
* Ask the feature owner or team lead when the correct project is unclear.

### Team Leads

Team leads must:

* Guide team members who are unfamiliar with the project-creation process.
* Ensure that feature work is organised correctly.
* Periodically review active feature projects.
* Correct repeated non-compliance with this SOP.

## 11. Exceptions

A separate feature project may not be required for:

* Small and isolated bug fixes
* Minor UI or copy changes
* Routine operational work
* Regular maintenance
* Tasks that can be completed through a single, self-contained to-do

When uncertain, the feature owner or team lead must decide whether the work is substantial enough to require a dedicated project.

## 12. Feature Project Readiness Checklist

Before implementation begins, confirm that:

* A dedicated Basecamp project exists for the feature.
* The project name identifies both the product and the feature.
* The project was created using the approved template.
* The PRD has been completed or updated.
* The PDR has been completed or updated.
* Scope and acceptance criteria are documented.
* Designs and supporting links are included.
* Implementation to-dos are inside the feature project.
* Relevant owners and assignees are identified.
* Important decisions are documented in the project.
* No active feature work is buried inside an old or generic project.

## 13. Effective Rule

**Create the feature project before creating the feature to-dos.**

A product is not a feature project, and a generic engineering project must not become a permanent dumping ground for unrelated development work.
