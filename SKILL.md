---
name: rl-paper-finder
description: "Use when the user seeks reinforcement learning papers or journal-club recommendations under a control-engineering venue whitelist (TAC, Automatica, TRO, TPAMI, CDC, ACC, NeurIPS, ICML, ICLR), including RL theory, dexterous manipulation, filtering, and unmanned surface vessels. 适用于按个人讨论班标准查找强化学习论文、筛选汇报选题；不用于制作PPT或逐章精读。"
---

# 强化学习讨论班论文查找

为控制工程专业、强化学习方向的用户查找适合讨论班汇报的原创研究论文。先核验资格，再比较研究价值；以下是已经确认的个人默认设置，无需每次重新采访。

## 默认范围

| 项目 | 规则 |
| --- | --- |
| 研究主题 | RL 是主要方法或主要研究对象；仅在背景、相关工作、对比基线中出现不合格 |
| 应用范围 | 不限应用；同等条件下优先控制、灵巧手、滤波、无人艇，保留通用 RL 算法与理论 |
| 年份 | 以调用当天为终点，默认近三年；在开头写明实际日期范围，用户可指定其他范围 |
| 文章类型 | 只选原创研究；排除 review、survey 及其他以综述调查为主的文章 |
| 发表状态 | 正式发表、Early Access、在线优先发表，或能从官方来源核实已录用 |
| 会议类别 | 只选主会正式完整研究论文；排除 Workshop、仅有摘要的展示。主会完整论文以 Poster 展示仍合格 |
| 数量与语言 | 默认中文推荐 5 篇，并重点推荐其中 1 篇；不足则返回实际数量 |
| 代码 | 不检查开源情况，不因有无代码筛选、加减分或改变排序，默认输出不含代码项 |

硬性发表渠道白名单：

| 简称／用户别名 | 正式名称 |
| --- | --- |
| TAC | IEEE Transactions on Automatic Control |
| AUTO / Automatica | Automatica |
| TRO / T-RO | IEEE Transactions on Robotics |
| TPAMI / 用户原写 TPMI | IEEE Transactions on Pattern Analysis and Machine Intelligence |
| CDC | IEEE Conference on Decision and Control |
| ACC | American Control Conference |
| NeurIPS | Conference on Neural Information Processing Systems |
| ICML | International Conference on Machine Learning |
| ICLR | International Conference on Learning Representations |

Nature、Science 正刊及子刊，以及其他未列明渠道均不在默认范围。AAAI、IJCAI、CoRL、RSS、ICRA、IROS 和其他 Transactions 也不能因声誉或主题相关而自动纳入。白名单中的 TAC、TRO、TPAMI 本身是 Transactions，不要一概排除 Trans。

用户在当前调用中明确修改的设置优先；“找灵巧手论文”只缩小主题，不隐含放宽渠道。不要因为数量不足而自行放宽条件。

## 查找与核验

1. **读取本次条件。** 直接应用已有默认值，仅在缺失信息确实阻碍检索时提问。记录检索日与时间范围。不指定主题时同时检索通用 RL 和相关应用，不强行给主题或期刊分配名额。
2. **发现候选。** 用可用的联网检索、学术索引或浏览工具查找，结合 RL 术语、主题词、渠道和年份迭代查询。例如 `("reinforcement learning" OR "offline RL" OR "safe reinforcement learning") ("Automatica" OR "Transactions on Automatic Control")`；应用查询可加入 `dexterous manipulation`、`filtering`、`state estimation`、`unmanned surface vessel` 或 `USV`。可用 ADP、学习最优控制等词扩展召回，但必须回到文章证据确认 RL 确为主线。
3. **核验资格。** 检索摘要和二手索引只作发现线索。以 IEEE Xplore、出版社论文页、官方会议论文集或正式录用记录核实标题、作者、渠道、年份和状态。NeurIPS 查官方论文集；ICML 查官方会议／PMLR 对应卷；ICLR 查官方会议对应的 OpenReview 录用记录。OpenReview 上有投稿不等于已录用，PMLR 或会议域名下的页面也不自动等于指定主会。
4. **确认 RL 作用。** 阅读摘要与方法，必要时检查全文中的训练目标、策略／价值学习及其在方法中的作用。不能把任意“智能控制”“数据驱动”“ADP”“最优控制”当成 RL；也不要求标题一定含 reinforcement learning。使用现有 RL 算法解决问题的实质性原创研究同样可以入选。
5. **提炼并比较。** 理论、算法、系统应用均可。综合问题价值、贡献清晰度、论据扎实程度、用户相关性与讨论空间作定性排序，不以引用量、渠道名气或代码情况代替内容判断。理论工作关注假设、保证及适用边界；算法工作关注比较公平性与适用条件；应用工作关注任务难点、实验支撑及泛化限制。实机实验并非所有论文的必备条件。

arXiv 可以提供全文，但不能单独证明录用。“submitted to”“under review”“拟投”不合格；只有作者自述录用且官方不可核实的记录不进入正式候选。录用待发表论文标明状态与官方证据，不能编造卷期、页码或 DOI。

期刊用可核验的首次正式在线发表日期（含 Early Access）判断时间，不因后续卷期日期把旧论文算成新论文；会议通常按正式会议年份判断，尚未举行但已核实录用的本届主会论文可纳入并说明。边界日期无法确认时明确说明，不假装精确。

同一论文的预印本、录用版和正式版合并处理；实质相同的会议版与期刊扩展版避免重复占用名额。不要把同名 Workshop 当成主会。

## 输出

开头简要说明本次时间范围、主题和核验日期，然后给出候选对照表：序号、论文原始标题、主要作者、渠道与年份／发表状态、研究方向、简短推荐理由。每篇附可打开的官方论文或录用证据链接，以及能找到的全文链接；没有 DOI 就不填，不生成猜测链接。

每篇用简短中文说明：

- 解决什么具体问题，为什么有研究价值。
- RL 在方法或研究对象中承担什么核心作用。
- 主要贡献与关键证据；区分作者报告的结果和自己的判断。
- 与用户方向的联系，以及值得讨论的局限或假设。

尽可能基于正文形成判断，优先核读首选论文的全文。注明实际阅读依据为“全文”“摘要及官方页面”或其他可核实范围；仅有摘要时不能臆造实验数字、定理条件或深入局限，重点推荐也须说明判断受限。

最后重点推荐 1 篇，说明为何更适合本次汇报，并给出 2—3 个可讨论的问题。不自动制作 PPT、讲稿或复现方案。

符合条件不足 5 篇时如实报告，不用未核实或不合格文章凑数；没有合格论文时直接说明。需要补充经典基础时，可在主列表之外少量列出，保持渠道、RL 主线和原创研究要求，清楚标注“经典补充／超出默认年份”，不冒充近三年候选。

若无法联网或官方证据不可获得，说明核验限制；可处理用户提供的论文与官方材料，但不能把记忆中的题目当成刚查到的最新论文。默认在聊天中交付，不创建定时任务、不联系作者。

调用示例：`使用 $rl-paper-finder，找近三年安全强化学习用于控制的论文，推荐五篇并重点推荐一篇。`
