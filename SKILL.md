---
name: youtube-briefing
description: 生成 YouTube 播客完整简报（默认一周榜+三周榜）并按固定口径输出。用于用户要求“跑 YouTube 简报/跑 YouTube 播客简报/周榜/三周榜/编辑精选/播客筛选/适合朋友圈转发的推荐清单”时启用；凡是涉及 AI 播客候选筛选、周度推荐、三周综合榜单、固定字段模板输出，都应优先使用此 skill。
---

# YouTube Briefing

按以下固定规则生成简报。

## 触发词约定
- 用户说“跑 YouTube 简报”时，默认触发**完整简报**。

## 输出结构
1. 先输出《一周榜》
2. 再输出《三周榜》

## 时间口径
- 一周榜：严格近10天滚动窗口。
- 三周榜：最近3周综合比较。

## 选题优先级
1) 新且火的 AI 公司创始人/高管访谈
2) AI 产品/设计/增长/运营实操
3) Agent / SaaS 争议话题

## 过滤规则
- 排除 Shorts。
- 避免纯 benchmark / evals 深挖。
- 只纳入 AI 相关公司/话题。
- 20VC 仅收录单个嘉宾对谈，排除多嘉宾拼盘节目。

## 频道池补充
- 纳入 The Peel with Turner Novak
- 纳入 BG2Pod with Brad Gerstner and Bill Gurley
- 纳入 moonshots 播放列表：https://www.youtube.com/playlist?list=PL1wpF5k0tdIve4idTp3-FX2ZY7ks_BKeU
- 纳入 a16z 频道：https://www.youtube.com/@a16z
- 纳入 Joe Lonsdale 频道：https://www.youtube.com/@Joe_Lonsdale

## 排名与排序
- 先按“话题相关度”筛选与排序。
- 播放量仅用于同档位微调，不覆盖相关度优先级。

## 每条强制字段（不可省略）
- 栏目名
- 标题（完整标题，不缩写）
- 嘉宾
- 发布时间（具体日期）
- 播放量
- 链接
- 摘要（Description 摘要/翻译）
- 3条推荐理由（bullet points）

## 风格要求
- 可加适当 emoji。
- 适合朋友圈转发。
- 理由要具体、可复用，避免空泛形容。

## 运行自检（简版）
输出前逐条检查：
1) 是否同时包含《一周榜》与《三周榜》；
2) 是否严格排除了 shorts 与非 AI 主题；
3) 每条是否包含全部强制字段；
4) 是否给出具体日期（不是“几天前”）。

## 落盘要求
- 每次运行后将完整简报保存为本地 `.md` 文件（路径通常在 `notebook/`）。
