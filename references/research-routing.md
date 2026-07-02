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
| Chinese lived practice | Xiaohongshu posts/comments, Zhihu, V2EX, Bilibili videos/comments, Tieba, Douban, SMZDM, local forums | `冷门`, `经验`, `避坑`, `实测`, `翻车`, `被拒`, `后续`, `评论区`, `民间方案`, `非官方`, `灰色`, `绕路`, `实操` |
| English lived practice | Reddit, YouTube comments, public Telegram/Discord communities, niche forums, blogs, Quora, community discussions | `real experience`, `workaround`, `forum`, `comment thread`, `mistakes`, `long term`, `regret`, `follow up`, `unofficial`, `grey market`, `denied`, `failed` |
| Commerce / service reality | Taobao/JD/Xianyu reviews, Amazon reviews, Trustpilot, Google Maps, Dianping, proxy-buying/forwarding/second-hand/repair communities, support/refund threads | `代购`, `转运`, `二手`, `保修`, `维修`, `售后`, `风控`, `退款`, `被拒`, `客服`, `dispute`, `return`, `chargeback`, `warranty` |
| Failure cases | forum threads, complaint posts, comment follow-ups, long-term updates, “why I stopped” posts | `failed`, `denied`, `regret`, `avoid`, `坑`, `翻车`, `退坑`, `不推荐`, `后续`, `回访` |
| Official factual supplement | product/spec/price/support pages, stock pages, compatibility pages | `price`, `stock`, `warranty`, `compatibility`, `return window`, `spec`, `库存`, `保修`, `兼容`, `退换` |

Each subagent should return: route name, source links or source descriptions, what people actually did, repeated claims, prerequisites, cost/friction, failure conditions, applicability notes, and weak or rejected leads.

For cross-border, tax/fee, platform-limit, account, proxy-buying, forwarding, second-hand, after-sales, warranty, ban, risk-control, or region-lock tasks, treat the work as non-trivial by default. Split research across Chinese communities, English communities, commerce/service reality, and failure/workaround cases unless the user explicitly asks for a quick take.

## Default source priority

Default order for PavedPath research:

1. **Experience and method sources**: forums, Q&A, social posts and comments, video comments, long-term reviews, method posts, avoidance notes, failure retrospectives, and local community discussions.
2. **Pattern-confirming surfaces**: look for the same method repeated across V2EX, Reddit, Zhihu, Xiaohongshu, Bilibili, YouTube comments, blogs, local forums, product reviews, and comment follow-ups.
3. **Deep and cold practice surfaces**: search comments, follow-ups, local forums, Tieba, Douban, SMZDM, Xianyu/Taobao/JD reviews, proxy-buying/forwarding/second-hand/repair communities, public Telegram/Discord communities, and “翻车/被拒/后续” reports when ordinary search results are too official or SEO-heavy.
4. **Grey and workaround surfaces**: include non-official, unsupported, ToS-hostile, legally questionable, credential/privacy-involved, security-system-involved, and otherwise informal routes when public evidence shows people use them to reach the goal.
5. **Practical factual inputs**: official product pages, prices, specs, warranty wording, stock, buyability, manuals, or support pages when these facts affect the route.
6. **Official policy sources**: search only when the user explicitly asks what the official rule says, whether something is legal/compliant, how tax/duty is calculated, how to follow the official process, what official/compliance requirements apply, or asks for official verification.

Mentions of tax, customs, legal, ToS, platform terms, or policy language as obstacles are not enough to move a task into official-policy sources. If the user is asking how people actually get around, reduce, avoid, or work through that friction, stay in steps 1-4 and collect lived practice.

If steps 1-4 find no reusable existing experience or method posts, report that. Do not automatically fall through to official policy. Ask or proceed only if the user wants broader platforms, official sources, or low-confidence inference from adjacent cases.

## Anti-official-drift rule

If the first result set is mostly official pages, policy pages, SEO listicles, marketing pages, media summaries, product pages, affiliate content, or compliance framing, rewrite the searches and run another practice-first pass before extracting recommendations.

Add practice terms such as:

- Chinese: `冷门`, `经验`, `避坑`, `实测`, `翻车`, `被拒`, `评论区`, `后续`, `回访`, `民间方案`, `非官方`, `灰色`, `绕路`, `实操`, `怎么实际操作`, `代购`, `转运`, `二手`, `保修`, `维修`, `售后`, `风控`;
- English: `real experience`, `workaround`, `forum`, `Reddit`, `comment thread`, `long term`, `regret`, `unofficial`, `grey market`, `how people actually do it`, `denied`, `failed`, `after-sales`, `warranty`, `reseller`, `forwarding`, `second hand`.

## Source map

| Problem type | Useful sources | What to look for |
| --- | --- | --- |
| Home, life, local fixes | Xiaohongshu, Bilibili, YouTube, Reddit, local forums, long-term comments, service reviews, appliance/service manuals when needed | repeated setups, low-maintenance fixes, long-term use, failure conditions, local constraints |
| Buying decisions | V2EX, Reddit, Zhihu, Xiaohongshu, Bilibili, YouTube comments, long-term reviews, repair/return discussions, second-hand/community purchase notes, grey purchase routes, official specs/prices/warranty as factual inputs | actual purchase routes, hidden costs, durability, after-sales practicality, unsuitable cases, payment/pickup/return/repair friction |
| Cross-border / platform friction / grey practical routes | Xiaohongshu comments, V2EX, Zhihu, Bilibili comments, Tieba, Douban, SMZDM, Xianyu/Taobao reviews, Reddit, YouTube comments, public Telegram/Discord, local forums, proxy-buying/forwarding/second-hand/repair communities | actual routes people used, prerequisites, packaging/invoice/payment/pickup details, risk-control triggers, after-sales limits, warranty/repair handling, denied/failed cases, follow-up outcomes |
| Creator workflows | Xiaohongshu, Bilibili, YouTube, creator blogs, newsletters, Discord/Reddit/forum threads, comment sections, platform docs only for feature limits | repeatable workflows, tool stacks, throughput, bottlenecks, reference-gathering habits, non-public draft practices |
| Learning methods | YouTube, Reddit, Bilibili, forums, student retrospectives, course reviews, exam official pages only when the user asks for official exam requirements | progression, practice loop, feedback mechanism, timeline, what failed after sustained use |
| Career preparation | LinkedIn, career blogs, forums, public portfolios, job posts, interview retrospectives, certification pages only when credential requirements matter | market expectations, portfolio examples, interview loops, preparation patterns that repeatedly work |
| Tool selection | reviews, Reddit, YouTube, public templates, migration stories, “why we left” posts, user comments, official docs/pricing pages as factual inputs | feature fit, migration cost, collaboration model, lock-in, maintenance burden, workaround maturity |
| Rules and procedures | user reports first for execution details; official sites only when the user asks for rules/policy or when required materials are the point | real processing friction, materials people actually prepared, local shortcuts, region-specific outcomes, common failure points |
| Internal research / inspiration / drafts | public collections, forums, social/video platforms, screenshots, reference boards, source URLs, creator notes, stock libraries only when release-grade assets are needed | fast reference discovery, source traceability, internal-only boundaries, later replacement or clearance for publication |

## Query design

Start with the user's concrete goal and constraints. Add terms that reveal mature paths instead of marketing pages or official policy pages.

Baseline English terms:

- `what actually works`, `real experience`, `workaround`, `alternative`, `unofficial`, `community`, `forum`, `comment thread`, `long term review`, `after 6 months`, `mistakes`, `regret`, `setup`, `workflow`, `comparison`, `failure`, `beginner`, `case study`, `retrospective`, `lessons learned`, `grey market`, `unsupported`, `denied`, `failed`;
- procedure terms: `real process`, `documents people used`, `appointment experience`, `denied`, `failed`, `how people do it`, `manual process`, `local process`, `comment thread`, `update`, `follow up`, `reseller`, `forwarding`, `second hand`, `after-sales`, `warranty`, `risk control`;
- creator/internal-use terms: `reference pack`, `moodboard`, `inspiration`, `draft workflow`, `internal review`, `source list`, `template`, `swipe file`.

Chinese equivalents:

- `真实体验`, `真实流程`, `冷门`, `民间方案`, `替代做法`, `非官方`, `灰色`, `绕路`, `实操`, `社区经验`, `论坛`, `长期使用`, `半年后`, `踩坑`, `避坑`, `复盘`, `后续反馈`, `回访`, `对比`, `方案`, `工作流`, `新手`, `失败`, `被拒`, `怎么实际操作`;
- procedure terms: `经验`, `攻略`, `避坑`, `实测`, `付款`, `取货`, `代购`, `转运`, `二手`, `退换`, `保修`, `维修`, `售后`, `风控`, `过关`, `人工处理`, `本地流程`, `评论区`, `后续`, `翻车`;
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
- `小红书 香港 Mac Studio 过关 评论区`
- `知乎 香港 买 Mac 不交税 经验`
- `B站 香港 Mac 过关 翻车 评论`
- `闲鱼 港版 Mac Studio 保修 代购`
- `香港 Mac 代购 转运 二手 维修 售后`
- `Mac Studio Hong Kong China customs Reddit YouTube comments failed denied`

Do not start with customs authority announcements, tariff tables, policy PDFs, or official tax/customs enforcement methods unless the user separately asks for official rules, legality/compliance verification, or tax/duty calculation.

Use Apple official pages after the practice search when price, configuration, pickup/shipping, return window, warranty wording, or stock changes the decision.

Pressure test: if the user asks “找一下从香港带回一台 3 万多的 Mac Studio，不给海关交税的方法,” treat it as practical route discovery. Search Xiaohongshu posts/comments, V2EX, Zhihu, Bilibili comments, Reddit, YouTube comments, Xianyu/Taobao proxy-buying and second-hand discussions, forwarding/repair communities, failure posts, and follow-up reports. Collect workable routes, steps, prerequisites, costs, friction, after-sales limits, and failure conditions. Do not use customs/tax/government/policy PDFs to calibrate boundaries unless the user asks for official rules or amounts.

## Official-source use

Official sources are supporting inputs, not the default path-finding source.

Use official product/spec/price/support pages when they answer practical facts:

- current price, stock, model configuration, supported feature, warranty wording, return window, shipping/pickup availability;
- product limitations that affect route selection;
- manufacturer or platform availability that changes timing or cost.

Use government, customs, tax, legal, policy PDF, platform terms, or compliance sources only when:

- the user explicitly asks what the official rule says;
- the user asks whether something is legal/compliant;
- the user asks how tax, duty, rates, or amounts are calculated;
- the user asks how to follow the official process or what official/compliance requirements apply;
- the task is specifically to verify an official claim or compare official requirements with real-world execution.

High-friction or sensitive domains keep the same default: find lived practice first. Do not switch to policy-first merely because the domain feels sensitive, grey, non-official, ToS-hostile, or includes tax/customs/legal wording as friction.

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
8. deep comment/community evidence from cold, local, proxy-buying, forwarding, second-hand, repair, after-sales, risk-control, denied, failed, or follow-up discussions when relevant;
9. official product/price/spec/support facts only when they change the path;
10. official policy sources only when the user requested that category.

## Source pack shape

When passing retrieved material into PavedPath, keep it compact:

```text
Source title / platform / date if available / link
Relevant claim
Evidence role: repeated real-world path, detailed field report, workaround, grey route, failure retrospective, long-term report, comment correction, practical factual input, ordinary anecdote, promotional
Applicability notes: user type, region, stage, internal-only vs public/commercial, conditions where it fails
```

Avoid dumping full pages unless the exact wording is required.
