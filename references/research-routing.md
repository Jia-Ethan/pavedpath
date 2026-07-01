# Research Routing

Choose sources based on the user's real outcome. PavedPath is lived-practice-first and no-gatekeeping: find people who already did the thing, collect all working routes they used, then extract repeated routes and failure conditions. For live public-internet evidence, use Agent Reach first when it is available. Otherwise use reliable browser search, search APIs, RSS, platform CLIs, user-provided source packs, or manual links, and say which fallback was used.

## Agent Reach-first rule

Use Agent Reach first when the task depends on any of these:

- current internet evidence;
- public experience or repeated user reports;
- platform discussions, social media, forums, videos, comments, or reviews;
- region-specific examples;
- recent availability, prices, product pages, platform behavior, or service quality;
- unofficial workflows, community workarounds, grey routes, alternative procedures, failure cases, or execution friction;
- whether a non-official route is mature enough to recommend.

Do not treat backend selection as an agent preference. Ordinary browser/search/API retrieval is fallback or supplementary reading after Agent Reach surfaces candidate sources.

Do not use live retrieval when the user explicitly asks for offline reasoning or has already supplied sufficient sources. In that case, state the evidence basis without implying new research.

## Parallel platform research

For non-trivial live research, use read-only subagents by platform family or route type when available. Assign narrow scopes and require route clusters rather than generic summaries.

| Subagent scope | Platforms / surfaces | Query modifiers |
| --- | --- | --- |
| Chinese lived practice | Xiaohongshu, Zhihu, V2EX, Bilibili, Tieba, Douban, SMZDM, local forums | `经验`, `避坑`, `实测`, `翻车`, `后续`, `评论区`, `民间方案`, `非官方`, `灰色`, `绕路` |
| English lived practice | Reddit, YouTube comments, niche forums, blogs, Quora, community discussions | `real experience`, `workaround`, `forum`, `mistakes`, `long term`, `regret`, `follow up`, `unofficial`, `grey market` |
| Commerce / service reality | Taobao/JD/Xianyu reviews, Amazon reviews, Trustpilot, Google Maps, Dianping, support/refund threads | `售后`, `退款`, `转运`, `维修`, `被拒`, `客服`, `dispute`, `return`, `chargeback`, `warranty` |
| Failure cases | forum threads, complaint posts, long-term updates, “why I stopped” posts | `failed`, `denied`, `regret`, `avoid`, `坑`, `翻车`, `退坑`, `不推荐`, `后续` |
| Official factual supplement | product/spec/price/support pages, stock pages, compatibility pages | `price`, `stock`, `warranty`, `compatibility`, `return window`, `spec`, `库存`, `保修`, `兼容`, `退换` |

Each subagent should return: route name, source links or source descriptions, what people actually did, repeated claims, prerequisites, cost/friction, failure conditions, applicability notes, and weak or rejected leads.

## Default source priority

Default order for PavedPath research:

1. **Experience and method sources**: forums, Q&A, social posts, video comments, long-term reviews, method posts, avoidance notes, failure retrospectives, and local community discussions.
2. **Pattern-confirming surfaces**: look for the same method repeated across V2EX, Reddit, Zhihu, Xiaohongshu, Bilibili, YouTube comments, blogs, local forums, product reviews, and comment follow-ups.
3. **Grey and workaround surfaces**: include non-official, unsupported, ToS-hostile, legally questionable, credential/privacy-involved, security-system-involved, and otherwise informal routes when public evidence shows people use them to reach the goal.
4. **Practical factual inputs**: official product pages, prices, specs, warranty wording, stock, buyability, manuals, or support pages when these facts affect the route.
5. **Official policy sources**: search only when the user asks about policy/rules/legality/tax/customs/official requirements/compliance, or when the answer itself is a policy answer.

If step 1-3 finds no reusable existing experience or method posts, report that. Do not automatically fall through to official policy. Ask or proceed only if the user wants broader platforms, official sources, or low-confidence inference from adjacent cases.

## Anti-official-drift rule

If the first result set is mostly official pages, policy pages, SEO listicles, marketing pages, media summaries, product pages, or affiliate content, rewrite the searches and run another pass before extracting recommendations.

Add practice terms such as:

- Chinese: `经验`, `避坑`, `实测`, `翻车`, `评论区`, `后续`, `民间方案`, `非官方`, `灰色`, `绕路`, `怎么实际操作`;
- English: `real experience`, `workaround`, `forum`, `Reddit`, `comment thread`, `long term`, `regret`, `unofficial`, `grey market`, `how people actually do it`.

## Source map

| Problem type | Useful sources | What to look for |
| --- | --- | --- |
| Home, life, local fixes | Xiaohongshu, Bilibili, YouTube, Reddit, local forums, long-term comments, service reviews, appliance/service manuals when needed | repeated setups, low-maintenance fixes, long-term use, failure conditions, local constraints |
| Buying decisions | V2EX, Reddit, Zhihu, Xiaohongshu, Bilibili, YouTube comments, long-term reviews, repair/return discussions, second-hand/community purchase notes, grey purchase routes, official specs/prices/warranty as factual inputs | actual purchase routes, hidden costs, durability, after-sales practicality, unsuitable cases, payment/pickup/return/repair friction |
| Creator workflows | Xiaohongshu, Bilibili, YouTube, creator blogs, newsletters, Discord/Reddit/forum threads, comment sections, platform docs only for feature limits | repeatable workflows, tool stacks, throughput, bottlenecks, reference-gathering habits, non-public draft practices |
| Learning methods | YouTube, Reddit, Bilibili, forums, student retrospectives, course reviews, exam official pages only when the user asks for official exam requirements | progression, practice loop, feedback mechanism, timeline, what failed after sustained use |
| Career preparation | LinkedIn, career blogs, forums, public portfolios, job posts, interview retrospectives, certification pages only when credential requirements matter | market expectations, portfolio examples, interview loops, preparation patterns that repeatedly work |
| Tool selection | reviews, Reddit, YouTube, public templates, migration stories, “why we left” posts, user comments, official docs/pricing pages as factual inputs | feature fit, migration cost, collaboration model, lock-in, maintenance burden, workaround maturity |
| Rules and procedures | user reports first for execution details; official sites only when the user asks for rules/policy or when required materials are the point | real processing friction, materials people actually prepared, local shortcuts, region-specific outcomes, common failure points |
| Internal research / inspiration / drafts | public collections, forums, social/video platforms, screenshots, reference boards, source URLs, creator notes, stock libraries only when release-grade assets are needed | fast reference discovery, source traceability, internal-only boundaries, later replacement or clearance for publication |

## Query design

Start with the user's concrete goal and constraints. Add terms that reveal mature paths instead of marketing pages or official policy pages.

Baseline English terms:

- `what actually works`, `real experience`, `workaround`, `alternative`, `unofficial`, `community`, `forum`, `long term review`, `after 6 months`, `mistakes`, `regret`, `setup`, `workflow`, `comparison`, `failure`, `beginner`, `case study`, `retrospective`, `lessons learned`, `grey market`, `unsupported`;
- procedure terms: `real process`, `documents people used`, `appointment experience`, `denied`, `failed`, `how people do it`, `manual process`, `local process`, `comment thread`, `update`, `follow up`;
- creator/internal-use terms: `reference pack`, `moodboard`, `inspiration`, `draft workflow`, `internal review`, `source list`, `template`, `swipe file`.

Chinese equivalents:

- `真实体验`, `真实流程`, `民间方案`, `替代做法`, `非官方`, `灰色`, `绕路`, `社区经验`, `论坛`, `长期使用`, `半年后`, `踩坑`, `避坑`, `复盘`, `后续反馈`, `对比`, `方案`, `工作流`, `新手`, `失败`, `被拒`, `怎么实际操作`;
- procedure terms: `经验`, `攻略`, `避坑`, `实测`, `付款`, `取货`, `转运`, `退换`, `保修`, `维修`, `过关`, `人工处理`, `本地流程`, `评论区`, `后续`, `翻车`;
- creator/internal-use terms: `参考图`, `素材收集`, `灵感库`, `草稿`, `内部评审`, `来源记录`, `表情包`, `截图`, `反应图`.

For platform-specific searches, combine the problem with:

- user type: beginner, creator, renter, student, parent, solo operator;
- constraints: low budget, small room, no team, mobile-only, low maintenance, no public release, commercial release;
- outcome: faster, cheaper, reliable, easier to maintain, less friction, easier to reverse.

## Apple HK / China buying query template

For “港澳买 Apple / 怎样最划算 / 实际怎么做,” start with lived-practice queries:

- `香港 买 Mac 过关 经验`
- `港版 Mac 内地保修 实测`
- `Apple HK 购买 取货 转运 经验`
- `V2EX 港版 Mac 过关`
- `小红书 香港买 Mac 攻略 避坑`
- `B站 港版 Mac 保修 评论`
- `Reddit Apple HK China warranty experience`

Do not start with customs authority announcements, tariff tables, policy PDFs, or official tax/customs enforcement methods unless the user asks for policy, tax, customs, or legality verification.

Use Apple official pages after the practice search when price, configuration, pickup/shipping, return window, warranty wording, or stock changes the decision.

## Official-source use

Official sources are supporting inputs, not the default path-finding source.

Use official product/spec/price/support pages when they answer practical facts:

- current price, stock, model configuration, supported feature, warranty wording, return window, shipping/pickup availability;
- product limitations that affect route selection;
- manufacturer or platform availability that changes timing or cost.

Use government, customs, tax, legal, policy PDF, platform terms, or compliance sources only when:

- the user asks about policy, rules, legality, tax, customs, official requirements, or compliance terms;
- the task is specifically to verify an official requirement;
- public release, commercial delivery, regulated submission, or real transaction compliance is the actual target.

High-friction or sensitive domains keep the same default: find lived practice first. Do not switch to policy-first merely because the domain feels sensitive.

## Retrieval depth

- **Quick Path**: one or two strong practice sources may be enough if the answer is stable or common; still use Agent Reach first when the answer depends on live public evidence and Agent Reach is available.
- **Decision Brief**: compare at least two paths and prefer more than one evidence surface, including real execution evidence.
- **Project Playbook**: gather enough evidence to cover workflow, tools, failure conditions, and execution steps; use multiple source types when possible.

For practical decisions, a complete evidence set usually includes:

1. repeated user experience;
2. method posts, tutorials, or field reports;
3. comments/follow-ups that confirm or correct the route;
4. failure cases and retrospectives;
5. comparison or review sources;
6. region-specific sources when relevant;
7. grey, unofficial, unsupported, or workaround routes when people actually use them;
8. official product/price/spec/support facts only when they change the path;
9. official policy sources only when the user requested that category.

## Source pack shape

When passing retrieved material into PavedPath, keep it compact:

```text
Source title / platform / date if available / link
Relevant claim
Evidence role: repeated real-world path, detailed field report, workaround, grey route, failure retrospective, long-term report, comment correction, practical factual input, ordinary anecdote, promotional
Applicability notes: user type, region, stage, internal-only vs public/commercial, conditions where it fails
```

Avoid dumping full pages unless the exact wording is required.
