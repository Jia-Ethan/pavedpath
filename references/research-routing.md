# Research Routing

Choose sources based on the user's real outcome. For live public-internet evidence, use Agent Reach first when it is available. Otherwise use reliable browser search, search APIs, RSS, platform CLIs, user-provided source packs, or manual links, and say which fallback was used.

## Agent Reach-first rule

Use Agent Reach first when the task depends on any of these:

- current internet evidence;
- public experience or repeated user reports;
- platform discussions, social media, forums, videos, comments, or reviews;
- region-specific examples;
- recent availability, prices, rules, platform behavior, or service quality;
- unofficial but lawful workflows, community workarounds, alternative procedures, failure cases, or execution friction;
- whether a non-official route is mature enough to recommend.

Do not treat backend selection as an agent preference. Ordinary browser/search/API retrieval is fallback or supplementary reading after Agent Reach surfaces candidate sources.

Do not use live retrieval when the user explicitly asks for offline reasoning or has already supplied sufficient sources. In that case, state the evidence basis without implying new research.

## Source map

| Problem type | Useful sources | What to look for |
| --- | --- | --- |
| Home, life, local fixes | Xiaohongshu, Bilibili, YouTube, Reddit, local forums, appliance/service manuals, official service pages | repeated setups, low-maintenance fixes, long-term use, failure conditions, local constraints |
| Buying decisions | official specs/prices/warranty, long-term reviews, comparison videos, product manuals, user comments, return/repair discussions, second-hand/community purchase notes | constraints, hidden costs, durability, after-sales practicality, unsuitable cases, non-official but lawful purchase routes |
| Creator workflows | Xiaohongshu, Bilibili, YouTube, creator blogs, newsletters, Discord/Reddit/forum threads, platform docs | repeatable workflows, tool stacks, throughput, bottlenecks, reference-gathering habits, non-public draft practices |
| Learning methods | YouTube, Reddit, Bilibili, forums, course reviews, exam official pages, student retrospectives | progression, practice loop, feedback mechanism, timeline, what failed after sustained use |
| Career preparation | LinkedIn, career blogs, forums, public portfolios, job posts, official certification pages, interview retrospectives | market expectations, portfolio examples, interview loops, unofficial preparation patterns that repeatedly work |
| Tool selection | official docs, pricing pages, reviews, Reddit, YouTube, public templates, migration stories, “why we left” posts | feature fit, migration cost, collaboration model, lock-in, maintenance burden, workaround maturity |
| Rules and procedures | official sites for hard constraints, then user reports for execution details | required materials, real processing friction, local shortcuts that remain lawful, region-specific outcomes, common failure points |
| Internal research / inspiration / drafts | public collections, forums, social/video platforms, screenshots, reference boards, source URLs, creator notes, stock libraries only when release-grade assets are needed | fast reference discovery, source traceability, internal-only boundaries, later replacement or clearance for publication |

## Query design

Start with the user's concrete goal and constraints. Add terms that reveal mature paths instead of marketing pages.

Baseline English terms:

- `what actually works`, `real experience`, `workaround`, `alternative`, `unofficial`, `community`, `forum`, `long term review`, `after 6 months`, `mistakes`, `regret`, `setup`, `workflow`, `comparison`, `failure`, `beginner`, `case study`, `retrospective`, `lessons learned`;
- procedure terms: `real process`, `documents`, `appointment`, `denied`, `failed`, `how people do it`, `not official`, `manual process`, `local process`;
- creator/internal-use terms: `reference pack`, `moodboard`, `inspiration`, `draft workflow`, `internal review`, `source list`, `template`, `swipe file`.

Chinese equivalents:

- `真实体验`, `真实流程`, `民间方案`, `替代做法`, `非官方`, `社区经验`, `论坛`, `长期使用`, `半年后`, `踩坑`, `避坑`, `复盘`, `后续反馈`, `对比`, `方案`, `工作流`, `新手`, `失败`, `被拒`, `怎么实际操作`;
- procedure terms: `材料`, `预约`, `付款`, `取货`, `转运`, `退换`, `保修`, `维修`, `海关`, `过关`, `人工处理`, `本地流程`;
- creator/internal-use terms: `参考图`, `素材收集`, `灵感库`, `草稿`, `内部评审`, `来源记录`, `表情包`, `截图`, `反应图`.

For platform-specific searches, combine the problem with:

- user type: beginner, creator, renter, student, parent, solo operator;
- constraints: low budget, small room, no team, mobile-only, low maintenance, no public release, commercial release;
- outcome: faster, cheaper, reliable, easier to maintain, less friction, easier to reverse.

## Legality and hard-boundary checks

Do not use official sources as the only path-finding source. Use them when they answer a hard-boundary question:

- Is this route legal in the relevant jurisdiction?
- Does this transaction, publication, submission, or regulated use require specific materials or permissions?
- Has a platform rule, price, availability, warranty, or eligibility condition changed recently?
- Would the route require deception, impersonation, stolen credentials, private data, or malicious bypass of security controls?

When a candidate route is effective but legality is unclear and legality determines feasibility, search current authoritative sources before recommending it. If legality still cannot be confirmed, do not make it the primary path; choose a lawful alternative or explain the condition that must be checked.

## Retrieval depth

- **Quick Path**: one or two strong sources may be enough if the answer is stable or common; still use Agent Reach first when the answer depends on live public evidence and Agent Reach is available.
- **Decision Brief**: compare at least two paths and prefer more than one evidence surface, including real execution evidence.
- **Project Playbook**: gather enough evidence to cover workflow, tools, failure conditions, and execution steps; use multiple source types when possible.

For practical decisions, a complete evidence set usually includes:

1. hard-boundary sources when needed;
2. repeated user experience;
3. unofficial/community workflows when they may be more effective;
4. failure cases and retrospectives;
5. comparison or review sources;
6. region-specific sources when relevant;
7. recent availability/prices only when they change the path.

## Source pack shape

When passing retrieved material into PavedPath, keep it compact:

```text
Source title / platform / date if available / link
Relevant claim
Evidence role: hard-boundary constraint, repeated real-world path, detailed field report, workaround, failure retrospective, ordinary anecdote, promotional
Applicability notes: user type, region, stage, internal-only vs public/commercial, conditions where it fails
```

Avoid dumping full pages unless the exact wording is required.
