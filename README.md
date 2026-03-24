# 🎙️ YouTube Briefing Skill

AI 播客周报生成器 — 自动追踪顶级科技/创投播客，生成结构化简报。

## ✨ 特性

- **一周榜 + 三周榜** — 严格近10天滚动窗口，综合热度与相关度
- **固定字段模板** — 栏目名、标题、嘉宾、发布时间、播放量、链接、摘要、3条推荐理由
- **智能过滤** — 排除 Shorts、纯 benchmark、非 AI 相关内容
- **朋友圈友好** — 适合直接转发的风格

## 📺 默认频道池

| 频道 | 定位 |
|------|------|
| Y Combinator | 创业者访谈、Demo Day |
| 20VC with Harry Stebbings | VC 视角、融资故事 |
| Lenny's Podcast | 产品增长、PM 实操 |
| The Peel with Turner Novak | 创始人深度访谈 |
| BG2Pod | Brad Gerstner & Bill Gurley 行业洞察 |

## 🚀 使用方法

### 触发词
```
跑 YouTube 简报
```

### 输出示例

```markdown
## 📺 一周榜（2026.03.18-03.24）

### 1. Lenny's Podcast
**标题**: How Figma's CEO thinks about AI, design, and building for the long term
**嘉宾**: Dylan Field (Figma CEO)
**发布时间**: 2026-03-20
**播放量**: 125,000
**链接**: https://youtube.com/...

**摘要**: Dylan 分享了 Figma 如何在 AI 时代保持产品力...

**推荐理由**:
• 首次公开分享 Figma AI 产品路线图
• 设计工具如何与 AI 深度融合的实战思考
• 对 Adobe 收购失败后公司战略调整的复盘
```

## 📦 安装

```bash
# 克隆到本地 skills 目录
cd ~/.openclaw/skills
git clone https://github.com/galengao-clawly/youtube-briefing-skill.git youtube-briefing
```

或通过 ClawdHub:
```bash
clawdhub install youtube-briefing
```

## 🎯 适合谁用

- **内容创作者** — 找选题、追热点
- **运营/增长** — 了解行业动态
- **投资人/FA** — 追踪 founder 访谈
- **独立开发者** — 产品灵感来源

## 📝 选题优先级

1. 🔥 新且火的 AI 公司创始人/高管访谈
2. 🛠️ AI 产品/设计/增长/运营实操
3. 💬 Agent / SaaS 争议话题

## 🤝 贡献

欢迎 PR 添加新频道或优化过滤规则！

## 📄 License

MIT
