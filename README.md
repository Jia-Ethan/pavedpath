# PavedPath

**Turn open-internet evidence into practical paths for non-code problems.**

PavedPath is a portable agent skill for finding approaches that people have already tried, filtering the evidence, and turning the strongest patterns into usable answers, decisions, workflows, or playbooks.

It is built for real-world, non-code questions: life and home decisions, tool selection, creator workflows, learning methods, buying decisions, career preparation, local services, and other planning problems where public internet experience is often more useful than starting from scratch.

PavedPath does **not** replace search tools. It sits above them: search and retrieval tools collect material; PavedPath frames the problem, grades the evidence, compares mature paths, and adapts the result to the user's constraints.

## 中文简述

PavedPath 是通用版 skill，用于非代码问题：从开放互联网中找已经被多人走通的成熟路径，再转成当前场景可执行的答案。它适合生活方案、工具选型、自媒体工作流、学习方法、消费决策、职业准备、本地服务等问题。代码、工程、调试、构建、部署、依赖和 API 集成问题请使用 **PavedPath Code**。

## What it is

PavedPath is a reasoning, decision, and synthesis layer for practical non-code problems.

It helps an agent:

- define the real goal and constraints before researching;
- route the question to useful public evidence surfaces;
- separate official facts, long-term experience, deep reviews, failure reports, ordinary anecdotes, and promotional content;
- extract repeated patterns instead of copying source summaries;
- compare candidate paths by fit, cost, effort, reversibility, maintenance burden, and evidence strength;
- answer in the smallest format that fully solves the user's problem.

## When to use it

Use PavedPath when the user needs a practical path for a non-code problem, especially:

- home, life, travel, local-service, or everyday decisions;
- buying decisions and product/service comparisons;
- creator workflows, content systems, and media operations;
- learning methods, study plans, and career preparation;
- non-code tool selection and workflow design;
- project plans where existing public examples can reduce trial and error.

Simple questions should get short answers. Complex projects should get detailed playbooks.

## When not to use it

Do not use PavedPath when the main problem is software engineering.

Use **PavedPath Code** instead for:

- code implementation or refactoring;
- debugging, build failures, deployment failures, or dependency issues;
- SDK/API integration work;
- package, framework, or runtime compatibility questions;
- adapting implementation patterns from repositories, issue trackers, docs, changelogs, or engineering examples.

Also do not use PavedPath as a generic search transcript. The goal is not to collect links; the goal is to turn evidence into a path the user can act on.

## Quick start

This repository is a plain skill folder. There is no package-manager install step yet.

For agents that support skill folders:

1. Clone or download this repository.
2. Copy or reference the whole folder as `pavedpath` in your agent's skill directory.
3. Keep `SKILL.md`, `agents/openai.yaml`, `references/`, and `examples/` together.
4. Ask your agent to use PavedPath for a non-code problem.

Folder shape:

```text
pavedpath/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
└── examples/
```

Minimal prompt:

```text
Use PavedPath for this non-code problem. Find mature public-internet approaches, compare the strongest paths, and answer at the right depth for my constraints.
```

For agents that do not support skill folders:

1. Paste `SKILL.md` into the agent's instruction or system-prompt layer.
2. Keep the files in `references/` available for the agent to consult.
3. Use the examples in `examples/` as output-shape references.
4. Provide retrieved sources directly if the agent cannot browse.

## Recommended companion: Agent Reach

PavedPath is backend-agnostic. It can work with any reliable way of getting evidence.

[Agent Reach](https://github.com/Panniantong/Agent-Reach) is a recommended companion, not a hard dependency. Use it when available for multi-platform retrieval across web search, social platforms, forums, videos, RSS, GitHub, and platform-specific channels.

Recommended division of labor:

```text
PavedPath = reasoning / decision / synthesis layer
Agent Reach = retrieval layer
PavedPath Code = code-focused edition for software engineering problems
```

If Agent Reach is unavailable, PavedPath can still work with browser search, search APIs, RSS readers, platform CLIs, user-provided links, pasted source packs, or manually supplied notes.

## How PavedPath works

PavedPath follows a simple workflow:

1. **Frame** the real problem, desired outcome, constraints, stakes, budget, time horizon, and reversibility.
2. **Choose depth**: short answer, decision brief, or project playbook.
3. **Route research** to suitable evidence surfaces for the problem type.
4. **Gather evidence** with the best available retrieval method.
5. **Grade evidence** by reliability, independence, recency, methodology, and practical applicability.
6. **Extract paths** by grouping repeated patterns and failure modes.
7. **Compare paths** by fit, effort, cost, maintenance, reversibility, and risk.
8. **Adapt and answer** with concrete steps matched to the user's constraints.

## Output modes

PavedPath uses the smallest answer shape that solves the problem.

| Mode | Use when | Output shape |
| --- | --- | --- |
| Quick Path | The user asks a simple question or wants a direct direction | Short conclusion, a few reasons, and a practical next step |
| Decision Brief | The user is choosing among tools, methods, products, services, or routes | Recommendation, option comparison, fit notes, and next action |
| Project Playbook | The user asks for a workflow, system, launch plan, study system, or other multi-step project | Problem model, evidence synthesis, recommended path, steps, tools, checks, and iteration loop |

See [`references/output-modes.md`](references/output-modes.md) for the detailed contracts.

## Examples

- [`examples/quick-path-humidity.md`](examples/quick-path-humidity.md): a simple home/life question should stay concise.
- [`examples/decision-brief-creator-tools.md`](examples/decision-brief-creator-tools.md): a tool-selection question should compare options and recommend one path.
- [`examples/project-playbook-content-workflow.md`](examples/project-playbook-content-workflow.md): a project-level creator workflow should become an executable playbook.

## PavedPath vs PavedPath Code

| Skill | Use it for | Do not confuse it with |
| --- | --- | --- |
| PavedPath | Non-code problems: life, tools, learning, creator workflows, buying decisions, career preparation, local services, and practical planning | Search itself, generic advice, or software engineering work |
| PavedPath Code | Software engineering problems: implementation, debugging, build/deploy, dependencies, SDK/API integration, runtime behavior, and engineering pattern research | A GitHub-only search tool or a general life/workflow decision skill |

The boundary is the user's real problem. If the answer primarily requires changing, debugging, building, deploying, or integrating software, use PavedPath Code. If the answer primarily requires choosing or executing a non-code path, use PavedPath.

## Project structure

```text
.
├── README.md                         # Human-facing project overview
├── SKILL.md                          # Agent-facing skill instructions
├── agents/openai.yaml                # UI metadata for agent skill lists
├── references/
│   ├── evidence-rubric.md            # How to grade and filter evidence
│   ├── output-modes.md               # Output contracts by task depth
│   └── research-routing.md           # Source routing by problem type
├── examples/
│   ├── quick-path-humidity.md
│   ├── decision-brief-creator-tools.md
│   └── project-playbook-content-workflow.md
└── .gitignore
```

## Roadmap

Near-term improvements that fit the current scope:

- add more examples across buying, learning, creator, local-service, and career-preparation use cases;
- add compact source-pack templates for agents that cannot browse live;
- add backend notes for environments using Agent Reach, browser tools, search APIs, or user-provided sources;
- add lightweight evaluation prompts for checking whether agents choose the right output mode.

These are roadmap items, not current feature guarantees.

## License

No license has been selected yet. Add a `LICENSE` file before treating this repository as an open-source distribution.
