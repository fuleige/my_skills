# My Skills

这是一个用于持续积累个人 Codex skills 的仓库。

### `write-opinion-article`

- 评论、专栏、观察文章
- 偏判断、偏作者声音

### `write-knowledge-article`

- 知识分享、教程、经验总结
- 偏讲解、偏专业、偏信息密度

当前主要是写作相关 skill，后续会继续扩展到其他类型。

## 目录结构

```text
.agents/skills/
├── <skill-name>/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
└── ...
```

## 使用方式

- 将 skill 放到 Codex 可发现的位置，例如 `.agents/skills/`
- 在对话中显式提到 skill 名称

示例：

- `使用 $write-opinion-article 写一篇评论稿`
- `使用 $write-knowledge-article 写一篇知识分享文章`

## 原则

- 一个 skill 尽量只做一类事情
- 边界清楚，减少误触发
- 先保证可用，再继续扩展
