<!-- markdownlint-disable MD013 MD033 -->

<h1 align="center">PavedPath</h1>

<p align="center">
  PavedPath is a reusable Skill for finding lived-practice-first, effective, feasible real-world paths for non-code problems.
</p>

<p align="center">
  <a href="#复制给智能体安装">复制给智能体安装</a>
  ·
  <a href="#简体中文">简体中文</a>
  ·
  <a href="#english">English</a>
  ·
  <a href="#license">License</a>
</p>

<p align="center">
  <img alt="Reusable Skill" src="https://img.shields.io/badge/Reusable-Skill-111827?style=flat-square">
  <img alt="PavedPath" src="https://img.shields.io/badge/PavedPath-General-2563eb?style=flat-square">
  <img alt="Lived practice first" src="https://img.shields.io/badge/lived--practice-first-0f766e?style=flat-square">
  <img alt="Agent Reach first-choice when present" src="https://img.shields.io/badge/Agent%20Reach-first--choice%20when%20present-7c3aed?style=flat-square">
  <img alt="License not selected" src="https://img.shields.io/badge/license-not%20selected-lightgrey?style=flat-square">
</p>

> **Status boundary / 状态边界**
>
> PavedPath is the general-purpose edition for non-code problems. It helps agents start from the user's real objective, search for lived public practice first, extract repeated routes and failure conditions, and adapt the strongest feasible path to the user's context.
>
> PavedPath 是通用版 Skill，用于生活方案、工具选型、自媒体工作流、学习方法、消费决策、职业准备、本地服务等非代码问题。它不是“官方答案复述器”，也不是“合规叙事生成器”；它默认先找已经有人走通过的方法、经验帖、避坑帖、失败复盘和评论区补充，再把重复出现的实践路线转成可执行答案。
>
> Code, engineering, debugging, build, deploy, dependency, SDK/API integration, and implementation-pattern problems are out of scope here. Use **PavedPath Code** for those.

## 复制给智能体安装

把下面这段话复制到 Codex、Claude Code、Cursor Agent、ChatGPT Agent 或其他支持读取 GitHub 项目的智能体：

```text
请使用 https://github.com/Jia-Ethan/pavedpath 帮我安装或接入 PavedPath 这个通用 Skill。先阅读 README、SKILL.md、agents/openai.yaml、references/ 和 examples/，确认它的边界是非代码问题：生活方案、工具选型、自媒体工作流、学习方法、消费决策、职业准备、本地服务和工作流设计。PavedPath 的默认方法是 lived-practice-first：先找网上已经有人实际走通的方法，优先检索经验帖、方法帖、避坑帖、失败复盘、论坛讨论、评论区补充、长期使用回报、V2EX / Reddit / 知乎 / 小红书 / Bilibili / YouTube 评论等，再从多人重复出现的做法里抽取可执行路线。不要把官方政策、政府/海关/税务/法律/平台条款或政策 PDF 当作默认检索入口；只有用户主动问政策、规则、是否合法、税费、海关、官方要求或合规条款时才查。官方价格、产品页、规格页、保修页可以作为价格、配置、可买性和支持事实输入，但不要让它们挤掉经验帖和实操流程。找不到可复用经验时，直接报告“没有找到可复用的已有经验 / 方法帖”，不要自动转去查官方政策；只有用户要求继续时，才问是否扩大平台、改查官方来源或基于相近案例做低置信推演。保留硬排除：不要推荐诈骗、盗取、盗号、冒充、贩卖隐私、恶意入侵、恶意绕过安全控制或明确违法行为。Agent Reach 是可选安装依赖，但如果环境中已经可用，它就是 live public-internet evidence 的第一选择检索层。若 Agent Reach 不可用，再使用浏览器搜索、搜索 API、RSS、平台 CLI、用户提供链接或 source pack，并说明 fallback。安装前先审计将写入的准确路径；如果你的环境有 skills 目录，就安装到对应 active skill 目录；如果没有固定 skill 目录，就把 README 和 SKILL.md 转成你的本地可复用指令。写入前展示计划和备份路径，等我确认；确认后再备份、安装，并用一次最小调用验证 pavedpath / PavedPath 可被正确识别。不要保存 token、cookie、私有内容、敏感日志或凭证。
```

## 友链 / Community

推荐配套安装：[Agent Reach](https://github.com/Panniantong/Agent-Reach) — first-choice retrieval layer for live public-internet evidence when present.

---

## 简体中文

### 项目定位

PavedPath 帮助 Agent 解决非代码现实问题：先识别用户真正想达成的结果，再从开放互联网和用户提供材料中寻找已经有人实际走通过的路线，最后把重复出现的有效模式转译成可执行答案、决策建议、工作流或 playbook。

它的优先级是：

```text
已有真实经验 / 方法帖 → 重复出现且能解释成败 → 用户当前条件下可执行 → 必要事实输入足够
```

官方价格页、产品页、规格页、保修页和支持页可以作为事实输入，用来确认价格、配置、可买性、支持范围和售后条件。它们重要，但不是默认路线来源。

官方政策、政府、海关、税务、法律、平台条款和政策 PDF 默认不查。只有用户主动问政策、规则、是否合法、税费、海关、官方要求、合规条款，或答案本身正在回答政策问题时，才查这类来源。不要为了证明某条实操路线“可接受”而例行查政策。

PavedPath 回答的是“现实中大家怎么做、哪条路最可执行、我下一步怎么做”，不是只复述规则、价格或政策。

### 核心原则

1. **真实目标优先**：先问用户真正要达成什么，再找能达成这个目的的路径。
2. **实操经验优先**：优先经验帖、方法帖、避坑帖、失败复盘、论坛讨论、评论区补充、长期使用回报和多平台重复模式。
3. **可执行性必须落地**：比较成本、时间、材料、账号/设备/地区前提、维护量、可逆性、售后/支持摩擦和失败条件。
4. **官方事实只是输入**：价格、规格、库存、保修、退换、支持范围等会影响路线时可以查官方页，但不要让官方页挤掉经验帖。
5. **找不到经验就直说**：没有可复用已有经验 / 方法帖时，直接报告；不要自动转向官方政策。用户要求继续时，再扩大平台、改查官方来源或做低置信推演。
6. **保留硬排除**：不要推荐诈骗、盗取、盗号、冒充、贩卖隐私、恶意入侵、恶意绕过安全控制或明确违法行为。

### 适用范围

适合使用 PavedPath：

- 生活、家居、旅行、本地服务和日常决策；
- 消费决策、产品/服务比较和低维护方案选择；
- 自媒体、内容生产、素材/参考收集和创作者工作流；
- 学习方法、备考路径、职业准备和作品集规划；
- 非代码工具选型、个人/团队工作流设计；
- 需要从公开经验中找到成熟路径、替代做法或现实 workaround 的复杂非代码项目。

不要用于：

- 代码实现、重构、debug、runtime error、build/test/deploy failure；
- dependency、SDK、framework、API usage、integration blocker；
- 从 GitHub issue、PR、release notes、代码示例中提取工程实现路径；
- 用户明确禁止联网或外部研究的任务；
- 未授权的私有内容、凭证、cookie、token、敏感日志或不可公开上下文。

这些代码 / 工程问题请使用 **PavedPath Code**。

### Features

| 能力 | 已包含内容 | 边界 |
| --- | --- | --- |
| 真实目标框定 | 识别用户真正要达成的结果、约束、预算、时间、可逆性和输出深度 | 不把官方流程当成目标本身 |
| 实操路径检索 | 搜索论坛、视频、社交平台、评论、RSS、平台 CLI、用户 source pack、经验帖、方法帖、避坑帖和 workaround | 不绑定单一搜索后端；默认不查政策来源 |
| Agent Reach 配套 | Agent Reach 是可选安装依赖；一旦环境中可用，就是 live public-internet evidence 的第一选择 retrieval layer | PavedPath 自身是方法与判断层；没有 Agent Reach 时才使用 browser/search/API/RSS/platform CLI 等 fallback |
| 证据分级 | 区分现实有效路径、深度教程、失败复盘、官方事实输入、普通个例和营销内容 | 不把官方、链接数量、热度或广告文案当结论 |
| 路径提取 | 把重复模式压缩成候选路径，并比较目标达成率、成本、摩擦、维护量和失败条件 | 不输出无取舍的资料堆叠 |
| 输出模式 | Quick Path、Decision Brief、Project Playbook 三种深度 | 简单问题保持短答；复杂项目才给详细 playbook |

### 工作流

```mermaid
flowchart LR
  A["User's real non-code objective"] --> B["Search lived practice first"]
  B --> C["Use Agent Reach first when live evidence is needed and available"]
  C --> D["Find repeated methods, comments, and failure cases"]
  D --> E["Add official product or price facts only when useful"]
  E --> F["Extract candidate paths"]
  F --> G["Compare by outcome, friction, cost, and failure conditions"]
  G --> H["Recommend effective feasible path"]
  H --> I["Give executable steps at the smallest useful depth"]
```

默认路径：

1. 定义用户真正想要的结果：要解决、选择、购买、计划、收集、验证或执行什么。
2. 先找真实经验：经验帖、方法帖、避坑帖、失败复盘、论坛讨论、评论区补充、长期使用回报、V2EX / Reddit / 知乎 / 小红书 / Bilibili / YouTube 评论等。
3. 判断是否需要 live public-internet evidence：如果答案依赖当前价格、可用性、公开经验、平台讨论、用户评价、社区案例、视频/社交媒体/论坛证据或地区差异，就需要。
4. 如果需要 live evidence 且 Agent Reach 可用，先用 Agent Reach；普通浏览器搜索、搜索 API、直接读网页、RSS、平台 CLI 只作为 fallback 或补充阅读。若 Agent Reach 不可用，说明 fallback。
5. 判断答案形态：简单问题用 Quick Path；多选项决策用 Decision Brief；复杂项目用 Project Playbook。
6. 先收集实操证据：重复方法、操作步骤、摩擦、隐藏成本、失败条件、售后/维修/退换体验、长期结果。
7. 只在影响路线时补充官方价格、规格、库存、保修、支持范围、退换窗口等事实输入。
8. 不主动查政府、海关、税务、法律、平台条款或政策 PDF，除非用户问这类问题。
9. 提取候选路径：说明每条路径适合谁、需要什么、为什么有效、成本是什么、何时会失败。
10. 输出建议：推荐最强可执行路径，给出步骤；只有证据薄弱、冲突、过时或失败条件会改变决策时才说明。

### Apple HK / CN 示例查询

遇到“港澳买 Apple / 怎样最划算 / 实际怎么做”这类问题，先搜：

```text
香港 买 Mac 过关 经验
港版 Mac 内地保修 实测
Apple HK 购买 取货 转运 经验
V2EX 港版 Mac 过关
小红书 香港买 Mac 攻略 避坑
B站 港版 Mac 保修 评论
Reddit Apple HK China warranty experience
```

不要先搜海关总署公告、税率表、政策 PDF 或官方征税办法。Apple / 厂商 / 平台官方价格或产品页可以在后面作为价格、配置、保修、库存、取货、退换事实输入。

### Installation

安装到你的智能体 active skill / instructions 目录。下面示例使用 `~/.codex/skills`；Claude Code、Cursor Agent、ChatGPT Agent 或其他智能体请按自己的本地指令目录改写路径：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/Jia-Ethan/pavedpath.git \
  ~/.codex/skills/pavedpath
```

更新已有安装：

```bash
git -C ~/.codex/skills/pavedpath pull --ff-only
```

如果你的 agent 不支持 skill folder，可以把 `SKILL.md` 放进 agent 的 instruction / system prompt 层，并把 `references/` 和 `examples/` 保留为可查资料。

### Recommended companion: Agent Reach

PavedPath 不把检索后端当成方法层本身。Agent Reach 是可选安装依赖，但如果环境中已经存在，它就是 live public-internet evidence 的第一选择检索层：

```text
PavedPath = reasoning / decision / synthesis layer
Agent Reach = first-choice retrieval layer when present
PavedPath Code = code-focused edition for software engineering problems
```

如果 Agent Reach 可用，凡是任务需要当前互联网证据、公共经验、平台讨论、用户评价、社区案例、视频/社交媒体/论坛来源、地区案例、非官方但有效的 route 或 workaround，都先用它做多平台检索。Backend selection 不是 agent 偏好。

只有在 Agent Reach 不可用、用户已经提供足够 sources、或用户明确要求 offline reasoning 时，才不使用 Agent Reach。如果 Agent Reach 不可用，说明 fallback，并使用 browser search、search APIs、RSS readers、platform CLIs、user-provided links、pasted source packs 或 manually supplied notes。

### Usage examples

最小调用：

```text
Use $pavedpath for this non-code problem. Find lived-practice-first, effective, feasible real-world paths, compare the strongest options, and answer at the right depth for my constraints.
```

Quick Path：

```text
Use $pavedpath. My room feels humid. Is a dehumidifier actually worth it? Keep it short.
```

Decision Brief：

```text
Use $pavedpath. I want a lightweight content idea database. Compare Notion, Airtable, and a spreadsheet, then recommend one path.
```

Lived-practice-first example：

```text
Use $pavedpath. I need to collect visual references and reaction GIFs for an internal non-commercial draft. Find practical public-source workflows; do not limit the answer to official stock libraries unless publication is part of the goal.
```

Project Playbook：

```text
Use $pavedpath. Design a practical weekly workflow for producing short-form social media posts. Include tools, cadence, review loop, and failure conditions.
```

### Output contract

当 PavedPath 实质影响结论时，回答应根据任务深度选择以下形态：

| 模式 | 适用场景 | 输出形态 |
| --- | --- | --- |
| Quick Path | 用户要短答案、方向判断或简单操作建议 | Conclusion、Why、Do this |
| Decision Brief | 用户在多个工具、方法、服务或路线之间选择 | Recommendation、Options、Avoid/delay、Next action |
| Project Playbook | 用户要工作流、系统、计划、长期执行方案 | Goal and constraints、Evidence-backed patterns、Recommended path、Steps、Tools、Failure modes、Verification loop |

通用要求：

- 简单问题保持短，不要自动写成长报告。
- 复杂项目要可执行，不要停留在原则或口号。
- 如果用户问“怎么解决 X”，输出可执行路径；不要只总结政策、规则、价格或条款，除非用户只问这些。
- 优先推荐最可能实现用户真实目标的路径，而不是最官方、最保守、最容易写成合规叙事的路径。
- 不因“非官方 / 民间流程 / workaround / 授权链条不完美”自动降权；只在它影响可执行性、发布条件或成败时处理。
- 不默认标注“未查官方政策”；除非用户需要官方政策核验，或答案本身正在回答政策问题。
- 对个人研究、内部评估、非商业草稿、灵感收集、工作流摸索，不默认套用商业发布级标准。
- 对正式公开发布、对外商业交付、真实交易、监管场景或高影响后果，补充会直接影响执行的必要条件。
- 不把“风险提示”做成常规输出要求；只用中性语言说明成本、前提、失败条件或不适用场景。
- 优先重复模式、长期使用、失败案例、论坛讨论和后续反馈，而不是单条爆款内容或营销文案。
- 如果使用了 live research 或用户提供 sources，输出中要给出关键来源或来源说明。

### Project structure

```text
pavedpath/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── evidence-rubric.md
│   ├── output-modes.md
│   └── research-routing.md
├── examples/
│   ├── quick-path-humidity.md
│   ├── decision-brief-creator-tools.md
│   ├── decision-brief-apple-hk-cn.md
│   ├── decision-brief-internal-reference-pack.md
│   └── project-playbook-content-workflow.md
└── .gitignore
```

### Security

- 默认只使用公开互联网资料或用户明确提供的 sources。
- 不要保存 token、cookie、密码、API key、私有仓库内容、内部上下文、敏感日志、production data 或凭证。
- 不要把私有内容、敏感日志、secrets、production data 或凭证交给检索工具或子代理。
- 不要推荐诈骗、盗取、入侵、窃取凭证、冒充身份、贩卖隐私、恶意绕过安全控制或明确违法行为。
- 不要为了证明路线“合规”而默认查政策；用户问政策/规则/税务/海关/官方要求时再查。
- 不要复制大段第三方内容；总结路径、模式、限制和可执行步骤即可。

### Roadmap

当前已包含：

- Skill 主入口：`SKILL.md`
- Agent metadata：`agents/openai.yaml`
- 证据分级、研究路由和输出模式参考：`references/`
- Quick Path、Decision Brief、Project Playbook 示例：`examples/`
- Agent Reach 作为可选安装依赖、但在可用时为 live public-internet evidence 第一选择 retrieval layer 的说明
- 与 PavedPath Code 的边界说明

可改进方向：

- 增加学习方法、职业准备、本地服务和更多创作者工作流示例。
- 增加 source pack 模板，方便不支持联网的 agent 使用。
- 增加针对 Agent Reach、浏览器工具和搜索 API 的 backend notes。
- 增加轻量评估 prompt，用来检查 agent 是否优先寻找 lived-practice-first paths。

不会承诺：

- 自动替用户做最终决策。
- 保证每个问题都有公开成熟路径。
- 替代搜索工具、浏览器或事实核验。
- 覆盖代码 / 工程 / debug / build / deploy / dependency / API integration 问题。
- 推荐违法路线或要求保存敏感凭证。

---

## English

### Project positioning

PavedPath helps agents solve non-code practical problems by starting from the user's real objective, finding routes already tested in public practice, grading the evidence, comparing candidate routes, and adapting the strongest feasible route to the user's context.

Its priority order is:

```text
existing real-world experience / method posts → repeated and failure-aware pattern → feasible for this user → enough supporting facts
```

Official product, price, spec, warranty, support, and availability pages may be useful factual inputs when they affect price, configuration, buyability, support, or timing. They are not the default route source.

Official policy, government, customs, tax, legal, platform-terms, and policy-PDF sources are not searched by default. Search them only when the user asks about policy, rules, legality, tax, customs, official requirements, compliance terms, or when the answer itself is a policy answer.

PavedPath answers what people actually do, which path is most workable, and how the user should execute it. It should not stop at rules, prices, or policy summaries unless the user asked for those.

### Core principles

1. **Outcome framing first**: identify what the user is actually trying to achieve before choosing sources or paths.
2. **Lived practice first**: prioritize experience posts, method posts, avoidance notes, failure retrospectives, forum discussions, comment follow-ups, long-term reports, and cross-platform repeated patterns.
3. **Feasibility must be operational**: compare cost, time, prerequisites, access, support friction, maintenance, reversibility, and failure conditions.
4. **Official facts are inputs**: use price, spec, stock, warranty, return, and support pages when they change the path, but do not let them replace practical evidence.
5. **No automatic policy fallback**: if reusable experience or method posts cannot be found, say so directly; continue into official sources or adjacent-case inference only if the user asks.
6. **Hard exclusions remain**: do not recommend fraud, theft, credential theft, impersonation, privacy trafficking, malicious intrusion, malicious security-control bypass, or clearly illegal conduct.

### Scope

Use PavedPath for:

- home, life, travel, local-service, and everyday decisions;
- buying decisions and product/service comparisons;
- creator workflows, content systems, reference gathering, and media operations;
- learning methods, study plans, and career preparation;
- non-code tool selection and workflow design;
- practical projects where public examples, alternative routes, or reality-tested workarounds can reduce trial and error.

Do not use PavedPath for:

- code implementation or refactoring;
- debugging, runtime errors, build failures, deployment failures, or dependency issues;
- SDK/API integration work;
- package, framework, or runtime compatibility questions;
- adapting implementation patterns from repositories, issue trackers, docs, changelogs, or engineering examples.

Use **PavedPath Code** for those software engineering problems.

### Features

| Capability | Included | Boundary |
| --- | --- | --- |
| Outcome framing | Real objective, constraints, budget, time horizon, reversibility, decision stakes, and output depth | Does not treat an official process as the goal itself |
| Evidence routing | Forums, videos, social platforms, reviews, comments, RSS, platform CLIs, user source packs, community workflows, and workarounds | Uses Agent Reach first for live public-internet evidence when present; policy sources are not default |
| Agent Reach pairing | Agent Reach is an optional installation dependency, but the first-choice retrieval layer once available | PavedPath remains the reasoning layer; browser/search/API/RSS/platform CLI are fallbacks or supplementary readers |
| Evidence grading | Reality-proven paths, deep tutorials, failure retrospectives, official factual inputs, anecdotes, and promotional content | Does not treat officialness, popularity, or link count as proof |
| Path extraction | Candidate paths with outcome fit, cost, friction, prerequisites, maintenance, and failure conditions | Does not dump raw sources as the answer |
| Output modes | Quick Path, Decision Brief, Project Playbook | Simple questions stay short; complex projects become executable playbooks |

### Workflow

```mermaid
flowchart LR
  A["User's real non-code objective"] --> B["Search lived practice first"]
  B --> C["Use Agent Reach first when live evidence is needed and available"]
  C --> D["Find repeated methods, comments, and failure cases"]
  D --> E["Add official product or price facts only when useful"]
  E --> F["Extract candidate paths"]
  F --> G["Compare by outcome, friction, cost, and failure conditions"]
  G --> H["Recommend effective feasible path"]
  H --> I["Give executable steps at the smallest useful depth"]
```

Default process:

1. Identify the practical outcome the user wants: solve, choose, buy, plan, collect, evaluate, or execute.
2. Search lived practice first: experience posts, method posts, avoidance notes, failure retrospectives, forum discussions, comment follow-ups, long-term reports, Reddit, V2EX, Zhihu, Xiaohongshu, Bilibili, YouTube comments, and region-specific communities.
3. Decide whether live public-internet evidence is needed. Use it when the answer depends on current prices, availability, public experience, platform discussions, reviews, community cases, social/video/forum evidence, or regional differences.
4. If live evidence is needed and Agent Reach is available, use Agent Reach first. Use browser search, search APIs, direct webpage reading, RSS, platform CLIs, user links, pasted source packs, or manual notes only as fallback or supplementary reading; state the fallback when Agent Reach is unavailable.
5. Choose the output depth: Quick Path, Decision Brief, or Project Playbook.
6. Gather practical evidence first: repeated methods, operational steps, friction, hidden costs, failure cases, workarounds, support/repair experiences, and long-term outcomes.
7. Add official price/spec/product/support facts only when they affect the path.
8. Do not search government, customs, tax, legal, platform-terms, or policy-PDF sources unless the user asked for that category.
9. Extract candidate paths from repeated patterns and failure conditions.
10. Adapt the strongest feasible path to the user's context and answer with executable steps.

### Apple HK / China query example

For “buying Apple from Hong Kong/Macau / most cost-effective / what should I actually do,” start with:

```text
香港 买 Mac 过关 经验
港版 Mac 内地保修 实测
Apple HK 购买 取货 转运 经验
V2EX 港版 Mac 过关
小红书 香港买 Mac 攻略 避坑
B站 港版 Mac 保修 评论
Reddit Apple HK China warranty experience
```

Do not start with customs authority announcements, tariff tables, policy PDFs, or official tax/customs enforcement methods. Use Apple/manufacturer/platform official pages later only as price, configuration, warranty, stock, pickup, shipping, and return factual inputs.

### Installation

Install this repository into your agent's active skill or instruction directory. This example uses `~/.codex/skills`; adapt it for Claude Code, Cursor Agent, ChatGPT Agent, or other local agent systems:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/Jia-Ethan/pavedpath.git \
  ~/.codex/skills/pavedpath
```

Update an existing install:

```bash
git -C ~/.codex/skills/pavedpath pull --ff-only
```

If your agent does not support skill folders, paste `SKILL.md` into the agent's instruction layer and keep `references/` and `examples/` available as supporting material.

### Recommended companion: Agent Reach

PavedPath does not make the retrieval backend its method layer. [Agent Reach](https://github.com/Panniantong/Agent-Reach) is optional as an installation dependency, but first-choice when present:

```text
PavedPath = reasoning / decision / synthesis layer
Agent Reach = first-choice retrieval layer when present
PavedPath Code = code-focused edition for software engineering problems
```

If Agent Reach is available, use it first whenever the task needs current internet evidence, public experience, platform discussions, user reviews, community cases, social/video/forum sources, regional examples, unofficial routes, or workarounds. Backend selection is not an agent preference.

Only skip Agent Reach when it is unavailable, the user has supplied sufficient sources, or the user explicitly requested offline reasoning. If Agent Reach is unavailable, state the fallback and use browser search, search APIs, RSS readers, platform CLIs, user-provided links, pasted source packs, or manually supplied notes.

### Usage examples

Minimal prompt:

```text
Use $pavedpath for this non-code problem. Find lived-practice-first, effective, feasible real-world paths, compare the strongest options, and answer at the right depth for my constraints.
```

Quick Path:

```text
Use $pavedpath. My room feels humid. Is a dehumidifier actually worth it? Keep it short.
```

Decision Brief:

```text
Use $pavedpath. I want a lightweight content idea database. Compare Notion, Airtable, and a spreadsheet, then recommend one path.
```

Lived-practice-first example:

```text
Use $pavedpath. I need to collect visual references and reaction GIFs for an internal non-commercial draft. Find practical public-source workflows; do not limit the answer to official stock libraries unless publication is part of the goal.
```

Project Playbook:

```text
Use $pavedpath. Design a practical weekly workflow for producing short-form social media posts. Include tools, cadence, review loop, and failure conditions.
```

### Output contract

When PavedPath materially shapes the answer, use the smallest output mode that solves the problem:

| Mode | Use when | Output shape |
| --- | --- | --- |
| Quick Path | The user wants a short answer, direct direction, or simple next step | Conclusion, Why, Do this |
| Decision Brief | The user is choosing among tools, methods, services, or routes | Recommendation, Options, Avoid/delay, Next action |
| Project Playbook | The user asks for a workflow, system, plan, or repeated operating process | Goal and constraints, Evidence-backed patterns, Recommended path, Steps, Tools, Failure modes, Verification loop |

Answer rules:

- Simple questions should get short answers.
- Complex projects should get detailed, executable playbooks.
- If the user asks how to solve X, provide workable solution paths; do not stop at policies, rules, prices, or terms unless the user asked only for those.
- Prefer the route most likely to achieve the user's real objective, not the route that is merely official, conservative, or easiest to narrate as compliant.
- Do not downgrade unofficial, community, workaround, or imperfectly authorized routes unless the issue affects feasibility, release conditions, or success.
- Do not routinely say “official policy was not checked” unless the user asked for policy verification or the answer is about policy.
- For personal research, internal evaluation, non-commercial drafts, inspiration gathering, and workflow exploration, do not apply commercial release standards by default.
- For public release, commercial delivery, real transactions, regulated contexts, or high-impact consequences, add the necessary conditions that directly affect execution.
- Do not make risk warnings a routine output section. State costs, prerequisites, failure conditions, or unsuitable scenarios in neutral operational language only when they change the path.
- Prefer repeated patterns, long-term experience, failure cases, forum threads, and follow-up comments over viral posts or promotional copy.
- Include key links or source descriptions when live research or user-provided sources materially affected the answer.

### Project structure

```text
pavedpath/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── evidence-rubric.md
│   ├── output-modes.md
│   └── research-routing.md
├── examples/
│   ├── quick-path-humidity.md
│   ├── decision-brief-creator-tools.md
│   ├── decision-brief-apple-hk-cn.md
│   ├── decision-brief-internal-reference-pack.md
│   └── project-playbook-content-workflow.md
└── .gitignore
```

### Security

- Use public internet material or sources explicitly provided by the user.
- Do not store tokens, cookies, passwords, API keys, private repository contents, internal context, sensitive logs, production data, or credentials.
- Do not pass private content, sensitive logs, secrets, production data, or credentials to retrieval tools or subagents.
- Do not recommend fraud, theft, malicious intrusion, credential theft, impersonation, privacy trafficking, malicious security-control bypass, or clearly illegal conduct.
- Do not check policy by default just to prove a route is acceptable; check policy/rules/tax/customs/official requirements when the user asks for them.
- Do not copy long third-party content. Summarize paths, patterns, limits, and executable steps.

### Roadmap

Currently included:

- Skill entrypoint: `SKILL.md`
- Agent metadata: `agents/openai.yaml`
- Evidence rubric, research routing, and output-mode references: `references/`
- Quick Path, Decision Brief, and Project Playbook examples: `examples/`
- Agent Reach as an optional installation dependency that becomes the first-choice retrieval layer for live public-internet evidence when present
- Clear boundary with PavedPath Code

Possible improvements:

- More examples for learning methods, career preparation, local services, and creator workflows.
- Source-pack templates for agents that cannot browse live.
- Backend notes for Agent Reach, browser tools, and search APIs.
- Lightweight evaluation prompts for checking whether agents prioritize lived-practice-first paths.

Non-goals:

- Making the final decision for the user.
- Guaranteeing that every problem has a mature public path.
- Replacing search tools, browsers, or fact-checking.
- Covering code, engineering, debugging, build, deploy, dependency, or API integration problems.
- Recommending illegal routes or storing sensitive credentials.

## License

No license has been selected yet. Add a `LICENSE` file before treating this repository as an open-source distribution.
