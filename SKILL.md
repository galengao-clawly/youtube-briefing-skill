---
name: youtube-briefing
description: 生成 YouTube 播客完整简报（默认一周榜+三周榜）并按固定口径输出。用于用户要求“跑 YouTube 简报/跑 YouTube 播客简报/周榜/三周榜/编辑精选/播客筛选/适合朋友圈转发的推荐清单”时启用；凡是涉及 AI 播客候选筛选、周度推荐、三周综合榜单、固定字段模板输出，都应优先使用此 skill。
---

# YouTube Briefing

按以下固定规则生成简报。

## 触发词约定
- 用户说“跑 YouTube 简报”时，默认触发**完整简报**。

## 输出结构
0. 先输出《本周总览》（≤300字）
   - 总结本周播客集中讨论的话题、被频繁提及的公司、主要观点。
   - 末尾必须加一句“本周重点推荐频道”，点名 3-5 个优先看的频道与理由（简短）。
1. 再输出《一周榜 Top 3》
2. 最后输出《三周榜 Top 8》

## 时间口径
- 一周榜：近7-10天滚动窗口，避免因为机械日期边界漏掉高质量内容。
- 三周榜：最近3周综合比较（Top 8）。

## 选题优先级
1) 新且火的 AI 公司创始人/高管访谈
2) AI 产品/设计/增长/运营实操
3) Agent / SaaS 争议话题

## 加权上调规则
- 单一公司 founder/CEO/核心高管深访优先于宏观圆桌、新闻串烧或泛趋势评论，尤其是围绕一家公司、一个产品、一个新类别展开的对谈。
- 如果被访公司近期完成新一轮融资、估值跃迁、重大产品发布、收入/用户增长拐点，或成为新兴 AI 类别代表，应显著上调排序。
- 对 AI infra / agent infra / search for agents / vertical AI 这类新类别，如果同时满足“创始人对谈 + 公司近期融资或快速增长”，应优先进入三周榜，并可进入一周榜。
- 示例：Exa CEO Will Bryk 这类围绕单一 AI search/agent infra 公司展开的 founder 对谈，应高于普通宏观评论，因为它同时具备公司样本、类别判断和融资/市场信号。
- 公司知名度、嘉宾可信度、频道/source 信号强度也要进入排序。若公司不够知名，不能仅凭夸张 ARR/用户数压过 Lenny's Podcast、a16z、YC、First Round 等强信号源中的高质量嘉宾/框架型内容。
- 三周榜更偏“长期可复用判断”：能帮助形成 AI 时代商业模式、产品 taste、组织方式、价值分配、distribution moat 等框架的内容，应优先于短期新闻热度、政策事件或纯宏观圆桌。
- 示例：Benedict Evans 这类 AI 价值分配/平台周期判断、Tony Fadell 这类产品 taste 与 judgment 讨论、YC AI-native services 这类商业模式 playbook，应在三周榜中显著上调。

## 过滤规则
- 排除 Shorts。
- 避免纯 benchmark / evals 深挖。
- 只纳入 AI 相关公司/话题。
- 20VC 仅收录单个嘉宾对谈，排除多嘉宾拼盘节目。
- 正式榜单优先从下方频道池/source 池中选取。若外部搜索发现高质量候选但 source 不在池中，可以作为“新发现 source”破例进入榜单，但必须明确标注发现路径、source 名称和破例入选理由；用户确认后再加入 source 池。

## 频道池补充
- 纳入 The Peel with Turner Novak
- 纳入 BG2Pod with Brad Gerstner and Bill Gurley
- 纳入 moonshots 播放列表：https://www.youtube.com/playlist?list=PL1wpF5k0tdIve4idTp3-FX2ZY7ks_BKeU
- 纳入 a16z 频道：https://www.youtube.com/@a16z
- 纳入 Joe Lonsdale 频道：https://www.youtube.com/@Joe_Lonsdale
- 纳入 Subversive：https://www.youtube.com/@SubversivePodcast
- 纳入 Y Combinator：https://www.youtube.com/@ycombinator
- 纳入 Peter Yang：https://www.youtube.com/@peteryangyt
- 纳入 Lenny's Podcast：https://www.youtube.com/@lennyspodcast
- 纳入 Sequoia Training Data：https://youtube.com/playlist?list=PLOhHNjZItNnMm5tdW61JpnyxeYH5NDDx8
- 纳入 Long Strange Trip：https://www.youtube.com/playlist?list=PLOhHNjZItNnNu8wknSuVtcSJRs7Q4xqOE
- 纳入 Sub Club Podcast：https://www.youtube.com/@SubClubPodcast
- 纳入 Redpoint Unsupervised Learning：https://www.youtube.com/@RedpointAI
- 纳入 The Logan Bartlett Show：https://www.youtube.com/@theloganbartlettshow
- 纳入 Redpoint Vital Signs：https://vital-signs-e526bbac.simplecast.com
- 纳入 First Round In Depth：https://review.firstround.com/podcast
- 纳入 First Round Capital：https://www.youtube.com/@FirstRoundCapital
- 纳入 Bessemer This Is Series A：https://www.bvp.com/atlas/this-is-series-a
- 纳入 Bessemer Cloud Giants：https://www.bvp.com/cloudgiants
- 纳入 Bessemer Wish I Knew：https://www.youtube.com/@BessemerVenturePartners
- 纳入 Bessemer Heart of Healthcare：https://www.bvp.com/heart-of-healthcare
- 纳入 Bessemer A Healthy Dose：https://www.bvp.com/atlas/a-healthy-dose
- 纳入 Greylock Greymatter：https://greylock.com/greymatter/
- 纳入 Kleiner Perkins Grit：https://www.kleinerperkins.com/category/media/grit/
- 纳入 Lightspeed Generative Now：https://linktr.ee/generativenow
- 纳入 NFX Podcast：https://podcast.nfx.com/
- 纳入 Accel Spotlight On：https://www.accel.com/spotlight-on
- 纳入 Exposure Ninja：https://www.youtube.com/@ExposureNinja

## 排名与排序
- 先按“话题相关度”筛选与排序。
- 播放量仅用于同档位微调，不覆盖相关度优先级。

## 每条强制字段（不可省略）
- 标题（完整标题，不缩写；标题后面必须带播客栏目/频道/source 名，例如 `标题｜Lenny's Podcast`。不要在条目信息里额外添加“栏目名”字段）
- 嘉宾（必须写为：姓名｜公司｜Title）
- 发布时间（具体日期）
- 播放量
- 链接（必须给完整 URL；发 Slack 时使用 `<URL|YouTube 视频>` 这类可点击格式）
- 摘要（Description 摘要/翻译）
- 3条推荐理由（bullet points，不可只给标题或泛泛评价）

## 榜单硬性要求
- 一周榜：固定 Top 3，且每条都要有 3 条推荐理由。
- 三周榜：固定 Top 8，且每条都要有 3 条推荐理由（不可省略）。

## 风格要求
- 可加适当 emoji。
- 适合朋友圈转发。
- 理由要具体、可复用，避免空泛形容。

## 运行自检（简版）
输出前逐条检查：
1) 是否先有《本周总览》（≤300字）+“本周重点推荐频道”一句；
2) 是否同时包含《一周榜 Top 3》与《三周榜 Top 8》；
3) 是否严格排除了 shorts 与非 AI 主题；
4) 每条是否包含全部强制字段（尤其“姓名｜公司｜Title”，以及标题后面的真实播客栏目/source 名；条目信息里不要额外输出“栏目名”字段）；
5) 一周榜与三周榜是否每条都有 3 条推荐理由；
6) 是否给出具体日期（不是“几天前”）。

## 落盘要求
- 每次运行后将完整简报保存为本地 `.md` 文件（路径通常在 `notebook/`）。
