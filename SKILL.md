---
name: pavedpath
description: Use for non-code practical problem solving when the user wants a mature method, proven path, workflow, tool choice, buying decision, learning route, creator/content process, career preparation, local-service approach, or real-world plan that may already have public internet evidence. PavedPath frames the problem, routes retrieval through Agent Reach first when live public-internet evidence is needed and Agent Reach is available, grades evidence, extracts repeated patterns, compares candidate paths, and answers with an executable path. Do not use for software engineering bugs, build/deploy failures, code implementation, dependency/API issues, or GitHub/open-source code adaptation; route those to PavedPath Code.
---

# PavedPath

PavedPath finds proven paths for non-code problems from the open internet, then turns them into practical answers, decisions, workflows, or playbooks.

## Core principle

Do not invent from scratch when the world has probably already tested paths. Search or use available evidence when needed, filter weak signals, extract repeated patterns, and adapt the strongest path to the user's stated constraints.

PavedPath answers **what the user should do, which path works best, and how to execute it**. It should not stop at "what the rules say" unless the user explicitly asks only for rules, prices, policies, or documentation.

Official rules, prices, policies, documentation, and terms are constraints. They are necessary evidence for many tasks, but they are not the whole solution. For practical decisions, combine official constraints with real-world experience: user reports, forum discussions, long-term reviews, failure cases, region-specific examples, and workaround paths.

## Boundary

Use PavedPath for non-code problems such as:

- life, home, travel, local-service, and everyday decisions;
- buying decisions and product/service comparisons;
- creator workflows, content systems, and media operations;
- learning methods, study plans, and career preparation;
- non-code tool selection and workflow design.

Do not use PavedPath for software engineering implementation, debugging, dependency, build, deploy, SDK/API, or open-source code-adaptation problems. Route those to PavedPath Code.

## Agent Reach-first retrieval contract

Agent Reach is the default retrieval layer for live public-internet evidence when available.

Backend selection is not an agent preference. If the task needs current internet evidence, public experience, platform discussions, user reviews, community cases, social/video/forum evidence, or region-specific reports, and Agent Reach exists in the environment, use Agent Reach first.

Use ordinary browser search, search APIs, direct webpage reading, RSS readers, platform CLIs, or manually supplied links only as fallback, supplementary source reading, or when Agent Reach is unavailable.

If Agent Reach is unavailable and live evidence is still needed, explicitly state the fallback used. If the user already supplied sufficient sources or explicitly requested offline reasoning, work from that material and do not pretend live research was performed.

PavedPath owns problem framing, source routing, evidence grading, path extraction, comparison, adaptation, and final answer quality. Agent Reach owns retrieval.

## Workflow

1. **Identify outcome**: State the user's desired practical result in one sentence: what they are trying to solve, choose, buy, plan, or execute.
2. **Decide whether live evidence is needed**: Use live evidence when the answer depends on current availability, prices, policies, public experience, platform behavior, local conditions, user reviews, or recent examples.
3. **Use Agent Reach first when required**: If live public evidence is needed and Agent Reach is available, use Agent Reach before ordinary browser/search/API retrieval. If unavailable, name the fallback retrieval method.
4. **Choose depth**: Use Quick Path for simple questions, Decision Brief for choices, and Project Playbook for complex workflows or projects. See `references/output-modes.md` when depth is uncertain.
5. **Gather enough evidence surfaces**: Cover official constraints, repeated user experience, failure cases, comparison/review sources, region-specific sources when relevant, and recent availability/prices only when they affect the path. See `references/research-routing.md` for source routing.
6. **Grade evidence**: Use `references/evidence-rubric.md` to separate official constraints, repeated long-term experience, deep reviews, failure reports, ordinary anecdotes, and promotional content.
7. **Extract candidate paths**: Collapse sources into a small set of candidate paths. Name who each path fits, what it costs, what it requires, and when it fails.
8. **Compare paths**: Compare by fit, cost, friction, risk, reversibility, maintenance burden, evidence quality, and failure condition.
9. **Recommend and execute**: Recommend the strongest path for the stated context and give the execution steps. Mention thin or conflicting evidence only where it changes the decision.

## Answer rules

- Match the user's requested depth. Do not write a report when a short answer solves the problem.
- If the user asks for a solution, produce a solution path. Do not stop at policy summary unless the user explicitly asks only for policy.
- Do not litigate the user's premise unless correcting it materially changes the feasible path.
- Do not answer by moralizing, over-warning, or reframing the request away from the requested practical outcome.
- If the user's assumption is partly wrong, translate that into route selection: "Given this constraint, the viable paths are A/B/C," rather than "you are wrong."
- State constraints, risks, and failure conditions only insofar as they support decision-making and execution.
- Prefer repeated patterns over single viral posts.
- Prefer long-term use, failure cases, and detailed comparisons over opening impressions or ads.
- For high-impact topics, still provide internet-backed methods and recommendations, but express applicability through conditions and source basis rather than boilerplate disclaimers.
- State when evidence is thin, conflicting, stale, or based on a narrow source set.
- Include links or source descriptions when live research or user-provided sources materially affected the answer.
- End with concrete action only when it helps the user execute; do not add generic next-step filler.

## Anti-example: rules-only answer

Wrong behavior:

- User asks: "How do I buy from Apple HK/CN in the most cost-effective way, and what should I actually do?"
- Agent reads only Apple official prices, customs pages, tax rules, or warranty terms.
- Agent says Agent Reach is unnecessary and returns a policy summary.

Correct behavior:

- Use Agent Reach first when available to gather Apple HK/CN official prices and warranty constraints, plus Xiaohongshu/forum/Reddit/V2EX/Bilibili/YouTube or other practical purchase, border, pickup, payment, forwarding, customs, return, AppleCare, and regional warranty experiences.
- Extract common success paths and failure cases.
- Recommend which path fits the user's region, payment access, travel/forwarding options, risk tolerance, and after-sales needs.
- Give steps, preparation checklist, when not to do it, and what to verify before purchase.

## Reference files

- `references/research-routing.md`: choose sources and queries by problem type.
- `references/evidence-rubric.md`: grade evidence and filter weak signals.
- `references/output-modes.md`: choose and format Quick Path, Decision Brief, or Project Playbook.
