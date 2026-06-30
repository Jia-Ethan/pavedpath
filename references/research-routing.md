# Research Routing

Choose sources based on the user's problem. For live public-internet evidence, use Agent Reach first when it is available. Otherwise use reliable browser search, search APIs, RSS, platform CLIs, user-provided source packs, or manual links, and say which fallback was used.

## Agent Reach-first rule

Use Agent Reach first when the task depends on any of these:

- current internet evidence;
- public experience or repeated user reports;
- platform discussions, social media, forums, videos, comments, or reviews;
- region-specific examples;
- recent availability, prices, rules, platform behavior, or service quality;
- practical workarounds, failure cases, or execution friction.

Do not treat backend selection as an agent preference. Ordinary browser/search/API retrieval is fallback or supplementary reading after Agent Reach surfaces candidate sources.

Do not use live retrieval when the user explicitly asks for offline reasoning or has already supplied sufficient sources. In that case, state the evidence basis without implying new research.

## Source map

| Problem type | Useful sources | What to look for |
| --- | --- | --- |
| Home, life, local fixes | Xiaohongshu, Bilibili, YouTube, Reddit, local forums, official service pages | repeated setups, long-term use, failure cases, local constraints |
| Buying decisions | official specs/prices/warranty, long-term reviews, comparison videos, product manuals, user comments, return/repair discussions | constraints, hidden costs, maintenance, durability, unsuitable cases |
| Creator workflows | Xiaohongshu, Bilibili, YouTube, creator blogs, newsletters, platform docs | repeatable workflows, tool stacks, throughput, bottlenecks |
| Learning methods | YouTube, Reddit, Bilibili, forums, course reviews, exam official pages | progression, practice loop, feedback mechanism, timeline |
| Career preparation | LinkedIn, career blogs, forums, public portfolios, job posts, official certification pages | market expectations, portfolio examples, interview loops |
| Tool selection | official docs, pricing pages, reviews, Reddit, YouTube, public templates | feature fit, migration cost, collaboration model, lock-in |
| Rules and procedures | official sites for constraints, then user reports for execution details | required materials, real processing friction, region-specific outcomes, common failure points |

## Query design

Start with the user's concrete goal and constraints. Add terms that reveal mature paths instead of marketing pages:

- `long term review`, `after 6 months`, `mistakes`, `regret`, `setup`, `workflow`, `comparison`, `alternatives`, `failure`, `beginner`, `case study`;
- Chinese equivalents such as `长期使用`, `踩坑`, `避坑`, `复盘`, `对比`, `方案`, `工作流`, `新手`, `半年后`, `真实体验`.

For platform-specific searches, combine the problem with:

- user type: beginner, creator, renter, student, parent, solo operator;
- constraints: low budget, small room, no team, mobile-only, low maintenance;
- outcome: faster, cheaper, reliable, easier to maintain, less risk.

For rules/procedure/buying tasks, add execution terms instead of stopping at official pages:

- `payment`, `pickup`, `shipping`, `forwarding`, `refund`, `warranty`, `repair`, `customs`, `border`, `transfer`, `appointment`, `documents`, `failed`, `denied`, `real experience`;
- Chinese equivalents such as `付款`, `取货`, `转运`, `退换`, `保修`, `维修`, `海关`, `过关`, `预约`, `材料`, `失败`, `被拒`, `真实经历`.

## Retrieval depth

- **Quick Path**: one or two strong sources may be enough if the answer is stable or common; still use Agent Reach first when the answer depends on live public evidence and Agent Reach is available.
- **Decision Brief**: compare at least two paths and prefer more than one evidence surface.
- **Project Playbook**: gather enough evidence to cover workflow, tools, failure modes, and execution steps; use multiple source types when possible.

For practical decisions, a complete evidence set usually includes:

1. official constraints;
2. repeated user experience;
3. failure cases;
4. comparison or review sources;
5. region-specific sources when relevant;
6. recent availability/prices only when they change the path.

## Source pack shape

When passing retrieved material into PavedPath, keep it compact:

```text
Source title / platform / date if available / link
Relevant claim
Evidence type: official constraint, long-term experience, deep review, failure report, ordinary anecdote, promotional
Applicability notes
```

Avoid dumping full pages unless the exact wording is required.
