# My Skills

这是一个用于保存个人 Codex 写作 skill 的仓库，当前主要放中文长文写作相关的两个 skill。

## 当前技能

### `write-opinion-article`

位置：`.agents/skills/write-opinion-article`

适合写带明确判断的评论、专栏、观察文章。这个 skill 会强调作者立场、段落推进和评论感，不适合拿来写以信息讲解为主的教程或知识分享。

典型场景：

- 写评论稿
- 写专栏稿
- 基于文档、现象或事件写观察文章
- 需要保留作者判断和观点锋芒的长文

### `write-knowledge-article`

位置：`.agents/skills/write-knowledge-article`

适合写朴实、专业、信息密度高的知识分享文章。这个 skill 更强调讲清楚、讲具体、保留关键操作细节，适合教程、经验总结、概念解释和专业解读。

典型场景：

- 写公众号知识分享
- 写教程或经验总结
- 基于官方文档写专业解读
- 需要少空话、少姿态、更多方法和边界条件的文章

## 两个 skill 的分工

- `write-opinion-article`：偏评论、偏判断、偏作者声音
- `write-knowledge-article`：偏讲解、偏专业、偏信息密度

如果一篇文章的重点是“我怎么看”，优先用 `write-opinion-article`。  
如果重点是“把事情讲清楚”，优先用 `write-knowledge-article`。

## 目录结构

```text
.agents/skills/
├── write-opinion-article/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
└── write-knowledge-article/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
```

## 使用方式

把本仓库中的 skill 目录放到 Codex 可发现的位置即可使用。当前仓库按项目内 skill 结构组织，主要面向：

- 仓库内共享 skill：`.agents/skills/`
- 随项目一起版本管理和迭代

在实际对话里，可以显式提到 skill 名称，例如：

- `使用 $write-opinion-article 写一篇评论稿`
- `使用 $write-knowledge-article 写一篇知识分享文章`

## 维护原则

- 评论型写作和知识型写作分开维护，避免一个 skill 过宽
- 参考文档只保留真正能提高结果质量的约束和检查项
- 优先收敛触发边界，减少误用和误触发
