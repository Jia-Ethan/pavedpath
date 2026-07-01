# Example: Decision Brief with Lived Practice First

## User request

Apple HK/CN 怎么买最划算、怎么操作？我想知道实际可行路径，不只是官方规则。

## Expected PavedPath behavior

Use Decision Brief. Because the answer depends on current prices, availability, payment/pickup/shipping options, warranty/repair reality, border/travel/forwarding friction, and recent user experience, use Agent Reach first when available.

Start with real-world experience and method queries, for example:

```text
香港 买 Mac 过关 经验
港版 Mac 内地保修 实测
Apple HK 购买 取货 转运 经验
V2EX 港版 Mac 过关
小红书 香港买 Mac 攻略 避坑
B站 港版 Mac 保修 评论
Reddit Apple HK China warranty experience
```

Do not start from customs authority announcements, tariff tables, policy PDFs, or official tax/customs enforcement methods unless the user asks for policy, tax, customs, or legality verification.

Expected evidence surfaces:

```text
Real-world execution evidence first:
- recent payment, pickup, forwarding, border crossing, return, repair, AppleCare, and regional warranty experiences
- repeated failure cases: card/payment rejection, stock mismatch, appointment/pickup issues, border friction, warranty misunderstanding, return inconvenience
- comment follow-ups and corrections from Xiaohongshu, Bilibili, Reddit, V2EX, Zhihu, local forums, YouTube, and comment threads
- region-specific examples matching the user's location and travel/forwarding options

Supporting factual inputs:
- Apple HK/CN price, stock, configuration, pickup/shipping, return window, warranty wording, and AppleCare availability when these facts change the route
```

Expected answer shape:

```text
Recommendation: The strongest path for your constraints is ...
Why this path wins: price difference, friction, warranty/repair practicality, reversibility, and failure condition.
Options:
- HK direct pickup / friend pickup: fit, steps, costs, when not to do it
- CN official purchase: fit, steps, costs, when it is actually better
- Forwarding / reseller / community-tested route: use only if repeated current experience supports authenticity and execution reliability; otherwise explain why to avoid or delay
Execution checklist: account, payment, stock check, pickup/shipping, invoice, warranty/AppleCare verification, return/repair fallback
Do not do this when: ...
Evidence notes: repeated public experience first; mention thin/conflicting evidence only if it changes the decision.
```
