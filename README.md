# My Skills

用于整理和维护 Codex skills 的仓库。

## 目录

仓库按功能分类，分类目录直接放在根目录：

```text
AGENTS.md
dev-workflow/
└── git-commit-zh/

writing/
├── write-knowledge-article/
└── write-opinion-article/
```

## 使用

本仓库存放的是 skill 源文件。实际使用时，将目标 skill 放到 Codex 可发现的目录中，例如：

- `~/.codex/skills/<skill-name>/`
- `<project>/.agents/skills/<skill-name>/`

## AGENTS.md

- 全局约束：`~/.codex/AGENTS.md`
- 项目级约束：`<project>/AGENTS.md`

仓库根目录的 [AGENTS.md](AGENTS.md) 用来维护全局约束内容。

## 约定

- 目录按职责分类，不按来源分类
- 一个 skill 只解决一类问题
