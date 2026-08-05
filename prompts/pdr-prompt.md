# PDR Prompt

This file contains the detailed instructions for generating each PDR section. Match sections by exact heading with `templates/pdr-template.md`.

- Keep overall workflow rules in `project-instructions.md`.
- Keep the template lightweight and place section-specific writing guidance here.
- When a new PDR section is added to the template, add a matching heading and detailed guidance in this file.
- Work section by section and stay in the current section until enough grounded context exists to complete it well.
- Start from the problem, not the proposed feature. Clarify the proposed solution only after the current pain, workflow, impact, and urgency are understood.
- Do not invent user quotes, evidence, impact, frequency, emotions, costs, or business decisions. Label assumptions and open questions explicitly.
- Preserve stable pain point IDs such as `PAIN-001`, `PAIN-002` once they are introduced.

## Understand the Context

## Purpose
Establish the baseline business and product context for the request before discussing solutions in detail.

## When to Use
Required at the start of discovery. Never `Not applicable`.

## Required Inputs
- **Mandatory:** who raised the issue, affected account or user type, what job they are trying to do, and why the topic is being discussed now.
- **Optional:** product area, customer history, previous related requests, known account context.
- **Never invent:** business type, request history, urgency, or feature framing.

## Questions to Ask
Ask only for missing context that is necessary to understand the user and situation. Prefer questions about the real-world job, current product usage, and reason this topic surfaced now. Do not let the conversation stay solution-first if the actual problem is still vague.

## Generation Instructions
Summarize the context in grounded terms. Focus on the user, the situation, and why the issue is now important. If the user starts with a feature request, translate it into the underlying problem context instead of simply restating the request.

## Output Format
- Preserve the template heading and substructure.
- Use concise factual statements under the template prompts.

## Validation Checklist
- [ ] The user or account context is clear.
- [ ] The real situation is described without relying only on the feature name.
- [ ] Why this topic is being discussed now is explicit or marked unknown.

## Avoid
Feature inventories, solution design, generic product summary, unsupported urgency claims, and invented customer background.

## Current Workflow

## Purpose
Capture how the user currently accomplishes the job today, including manual steps, workarounds, tools, and failure points.

## When to Use
Required before Pain Points and Impact are finalized. Never `Not applicable`.

## Required Inputs
- **Mandatory:** current steps, tools or systems involved, actors, and where the flow slows down or breaks.
- **Optional:** frequency, channel, device, handoffs, admin/member differences.
- **Never invent:** tools, steps, actors, or workarounds.

## Questions to Ask
Ask only for missing parts of the actual flow. Good questions clarify sequence, ownership, tools used, and where users leave the happy path. Keep probing until the current workflow can be explained clearly enough for someone else to understand the problem without seeing the feature request.

## Generation Instructions
Describe the current workflow in plain language and in the order it happens. Make the flow concrete enough to reveal where the pain originates. Distinguish confirmed facts from assumptions.

## Output Format
- Preserve the template heading and prompt structure.
- Use short stepwise or paragraph-style answers that follow the current workflow prompts.

## Validation Checklist
- [ ] The current way of doing the job is understandable end to end.
- [ ] Workarounds and supporting tools are visible.
- [ ] The workflow shows where pain and friction actually occur.

## Avoid
Jumping to the desired future state, abstract summaries, technical implementation internals, and vague statements like “the process is manual.”

## Pain Points

## Purpose
Identify the concrete user problems, frustrations, delays, risks, and points of failure in the current workflow.

## When to Use
Required after the current workflow is clear. Never `Not applicable`.

## Required Inputs
- **Mandatory:** specific pain points, who experiences them, what happens, and why they are painful.
- **Optional:** frequency, severity, workaround quality, emotional effect, stakeholder-specific pain.
- **Never invent:** frustrations, severity, quotes, emotional impact, or operational loss.

## Questions to Ask
Ask for missing concrete pain. Push past “we need feature X” until the user can explain what breaks today, what extra effort is created, and what makes the experience frustrating, risky, embarrassing, slow, or costly.

## Generation Instructions
List pain points as concrete problem statements, not solution statements. Assign stable IDs such as `PAIN-001`, `PAIN-002` when more than one pain point is identified. Each pain point should describe the affected person, the failure or friction, and the consequence.

## Output Format
- Preserve the template heading and prompt structure.
- Where multiple pain points exist, include stable IDs inline with the answer text.

## Validation Checklist
- [ ] Each pain point describes a real present-tense problem.
- [ ] Pain points are user-centered, not feature-centered.
- [ ] Stable pain IDs are used when appropriate and can be reused later in the PRD.

## Avoid
Restating requested features, vague claims like “not efficient,” bundled problems, invented emotional language, and future-state requirements.

## Impact

## Purpose
Explain what the pain points cost in human, workflow, business, or trust terms.

## When to Use
Required after at least one clear pain point exists. Never `Not applicable`.

## Required Inputs
- **Mandatory:** observable consequence of the pain, such as time loss, workflow blockage, quality risk, missed adoption, support burden, demo weakness, customer dissatisfaction, or business risk.
- **Optional:** urgency, severity, commercial effect, confidence impact, team impact, account risk.
- **Never invent:** revenue impact, quantified cost, churn risk, or business priority.

## Questions to Ask
Ask what happens because the problem exists today. Clarify impact on the person doing the work, on the broader team, and on the business where relevant. If impact is emotional or trust-related, make that explicit.

## Generation Instructions
Make impact concrete. Distinguish user-level impact from business-level impact where useful. If the evidence is partial, label assumptions rather than overstating certainty.

## Output Format
- Preserve the template heading and prompt structure.
- Use direct consequence statements rather than generic commentary.

## Validation Checklist
- [ ] The cost of the problem is explicit.
- [ ] Human, workflow, and business impact are distinguished where relevant.
- [ ] Unsupported numeric or commercial claims are not invented.

## Avoid
Vague statements like “this is bad for business,” unsupported ROI claims, solution benefits presented as current facts, and generic severity language.

## Expectations

## Purpose
Capture what the stakeholder believes a good outcome should look like, without allowing the section to become final requirements too early.

## When to Use
Required after the problem and impact are understood. Never `Not applicable`.

## Required Inputs
- **Mandatory:** desired outcome, must-haves versus nice-to-haves when known, and any constraints on the acceptable solution shape.
- **Optional:** examples from competitors, operational expectations, rollout concerns.
- **Never invent:** final requirements, commitments, or approved scope.

## Questions to Ask
Ask what improvement would make the problem meaningfully solved. Clarify the outcome they care about, not just the named feature. If they provide a feature idea, connect it back to the pain it is meant to solve.

## Generation Instructions
Describe expectations in terms of outcomes, not implementation. Keep the distinction clear between what the stakeholder wants to achieve and how the eventual product might accomplish it.

## Output Format
- Preserve the template heading and prompt structure.
- Use concise answers that separate must-haves from nice-to-haves when that distinction is available.

## Validation Checklist
- [ ] The desired future state is clear.
- [ ] Expectations remain outcome-focused.
- [ ] Must-haves and nice-to-haves are separated when supported.

## Avoid
Turning this section into final scope, inventing commitments, and mixing approved requirements with early wishes.

## Constraints

## Purpose
Record known limits, dependencies, or conditions that materially shape discovery or eventual solution scope.

## When to Use
Required when constraints are known; otherwise mark the answers as unknown rather than fabricating them.

## Required Inputs
- **Mandatory:** known timing, compliance, technical, operational, contractual, or organizational constraints when provided.
- **Optional:** budget sensitivity, rollout dependency, staffing limits, cross-team coupling.
- **Never invent:** technical blockers, deadlines, resourcing, or policy restrictions.

## Questions to Ask
Ask only about constraints that would materially change how the problem should be framed or how realistic solutions will later be evaluated.

## Generation Instructions
State constraints concretely and separately from pain points. If none are known yet, say so clearly instead of filling the section with guesses.

## Output Format
- Preserve the template heading and prompt structure.
- Use short direct statements.

## Validation Checklist
- [ ] Real constraints are separated from preferences.
- [ ] Unknowns are labelled honestly.
- [ ] No invented technical or organizational assumptions appear.

## Avoid
Assumed deadlines, fabricated complexity, and mixing solution ideas into constraints.

## Key Insights

## Purpose
Synthesize the main discovered problems, why they matter, and any early solution ideas without losing the distinction between facts and proposals.

## When to Use
Required after the earlier discovery sections are sufficiently complete. Never `Not applicable`.

## Required Inputs
- **Mandatory:** main problems identified, why they matter, and any solution ideas explicitly mentioned.
- **Optional:** strongest evidence, major unknowns, important tradeoffs.
- **Never invent:** new pain points, decisions, or recommendations not supported by earlier sections.

## Questions to Ask
Ask only if the current draft cannot clearly summarize the discovery. Do not reopen solved questions unless the earlier sections are contradictory or still vague.

## Generation Instructions
Summarize the discovery crisply. Preserve the distinction between:
- confirmed problems
- why they matter
- solution ideas mentioned but not yet approved

If pain point IDs exist, reuse them here.

## Output Format
- Preserve the template heading and prompt structure.
- Use concise summary statements tied back to earlier discovery.

## Validation Checklist
- [ ] The summary reflects the earlier sections accurately.
- [ ] Solution ideas are separated from confirmed problems.
- [ ] Important unknowns are not hidden.

## Avoid
Introducing new scope, rewriting the whole document, and treating ideas as decisions.

## After the Call

## Purpose
Capture the concise takeaway and immediate follow-up from the discovery conversation.

## When to Use
Required when the PDR includes interview or discussion notes. For non-interview internal discovery, adapt the same intent to a brief wrap-up.

## Required Inputs
- **Mandatory:** short summary and next steps when known.
- **Optional:** owner, follow-up artifact, open question, evidence still needed.
- **Never invent:** commitments, timelines, or owners.

## Questions to Ask
Ask only for the next action or unresolved need if it is important to close the discovery cleanly.

## Generation Instructions
Keep this short. Summarize what was learned and what should happen next without overcommitting.

## Output Format
- Preserve the template heading and prompt structure.
- Keep summary and next steps brief.

## Validation Checklist
- [ ] The wrap-up is concise and accurate.
- [ ] Next steps are grounded in the discovery, not invented.
- [ ] No premature commitments are introduced.

## Avoid
Long recap paragraphs, speculative next steps, and hidden assumptions about ownership or delivery timing.
