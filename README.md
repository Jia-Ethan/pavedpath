# PavedPath

**Find proven paths for non-code problems from the open internet.**

PavedPath is a portable agent skill for turning public internet experience into practical answers, decisions, workflows, and playbooks. It is designed for problems where the world has probably already tried many approaches: tool selection, creator workflows, learning methods, buying decisions, home/life fixes, career preparation, local services, and other real-world planning tasks.

PavedPath is not a search wrapper. It is the reasoning layer above search: it frames the problem, routes research to the right evidence surfaces, filters weak signals, extracts repeated patterns, compares paths, and adapts the strongest path to the user's stated constraints.

## 中文简述

PavedPath 用于解决非代码问题：先从开放互联网中寻找已经被多人走通的方法，再提炼成当前问题可执行的路径。它适合生活方案、消费选型、自媒体工作流、学习方法、工具选择、职业准备、本地服务等场景。

代码、工程、依赖、构建、部署、API 使用等问题请使用 **PavedPath Code（代码版）**。

## Why PavedPath

Agents often answer from general model knowledge even when better answers already exist in public experience. PavedPath changes the default behavior:

- Do not invent from scratch when proven paths are available.
- Prefer repeated patterns over one-off anecdotes.
- Separate practical evidence from ads, hype, and vague recommendations.
- Match answer depth to the task: a simple question should get a short answer; a project-level question should get a full playbook.
- Keep the skill portable across agent environments and research backends.

## Install / Use with your agent

PavedPath is a plain skill folder. To use it with an agent system that supports skills, copy or reference this repository as a skill package:

```text
pavedpath/
├── SKILL.md
├── agents/openai.yaml
├── references/
└── examples/
```

Example agent prompt:

```text
Use PavedPath to find mature public-internet approaches for my non-code problem, compare the strongest paths, and answer at the right depth.
```

For systems that do not support skill folders, paste `SKILL.md` into the agent's instruction layer and keep the files in `references/` available as supporting material.

## Recommended companion: Agent Reach

PavedPath is backend-agnostic: it does not require one specific search tool. When live external evidence is needed, use the strongest research backend available in your environment.

If you have access to [Agent Reach](https://github.com/Panniantong/Agent-Reach), install it alongside PavedPath. Agent Reach is a strong companion because it can retrieve evidence from web search, social platforms, forums, videos, RSS, GitHub, and platform-specific channels.

Recommended division of labor:

```text
PavedPath = problem framing, source routing, evidence grading, pattern extraction, comparison, adaptation, final answer
Agent Reach = multi-platform retrieval and content access
```

Agent Reach is recommended, not required. PavedPath can also work with browser search, search APIs, RSS readers, platform CLIs, user-provided links, or manually supplied source packs.

## How it works

PavedPath follows seven steps:

1. **Frame** the real problem, desired outcome, constraints, and decision stakes.
2. **Route** research to suitable evidence surfaces.
3. **Gather** enough public evidence for the task depth.
4. **Distill** repeated patterns and discard weak signals.
5. **Compare** candidate paths by fit, effort, cost, reversibility, and evidence strength.
6. **Adapt** the best path to the user's stated context.
7. **Answer** in the smallest format that fully solves the problem.

## Output modes

PavedPath adapts its answer shape to the task:

| Mode | Use when | Output shape |
| --- | --- | --- |
| Quick Path | The user asks a simple question or wants a direct direction | Short conclusion, a few reasons, and a practical next step |
| Decision Brief | The user is choosing among tools, methods, products, or routes | Recommendation, option comparison, fit notes, and next action |
| Project Playbook | The user asks for a workflow, system, launch plan, or complex project | Problem model, evidence synthesis, recommended path, steps, tools, checks, and iteration plan |

See [`references/output-modes.md`](references/output-modes.md) for the detailed contracts.

## Examples

- [`examples/quick-path-humidity.md`](examples/quick-path-humidity.md): a simple home/life question should stay concise.
- [`examples/decision-brief-creator-tools.md`](examples/decision-brief-creator-tools.md): a tool-selection question should compare options and recommend one path.
- [`examples/project-playbook-content-workflow.md`](examples/project-playbook-content-workflow.md): a project-level creator workflow should become an executable playbook.

## PavedPath vs PavedPath Code

| Skill | Problem type | Primary evidence world |
| --- | --- | --- |
| PavedPath | Non-code problems: life, tools, learning, creator workflows, buying decisions, career prep, local services | Open web, social platforms, forums, videos, official docs, reviews, public communities |
| PavedPath Code | Software engineering problems: bugs, builds, dependencies, APIs, integrations, implementation patterns | GitHub repositories, issues, PRs, discussions, examples, release notes, open-source docs |

Use PavedPath Code when the main task is to change, debug, build, deploy, or integrate software. Use PavedPath when the main task is a non-code decision or workflow.

## Roadmap

- Add more real-world examples across learning, buying, creator, local-service, and workflow use cases.
- Add optional source-pack templates for agents that cannot browse live.
- Add backend-specific adapters for environments with Agent Reach, browser tools, or search APIs.
- Add evaluation prompts for testing whether agents choose the correct output mode.

## License

License not selected yet. Add a `LICENSE` file before publishing this repository as an open-source project.
