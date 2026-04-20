---
name: git-commit-zh
description: Generate concise, structured Chinese git commit messages from repository changes. Use when the user asks to commit code, write or rewrite a commit message, summarize staged changes or diffs for a commit, or improve overly simple commit logs. For each commit, first write one sentence summarizing the overall change, then list the most important details as short bullet points. Keep the content focused, brief, and highlight meaningful behavior, interface, data, configuration, compatibility, or risk changes.
---

# Git Commit 中文总结

## Overview

在处理 `git commit`、提交说明重写、根据 diff 生成提交信息、优化过于简单的提交日志时使用这个 skill。

目标输出固定为中文：

```text
<一句话总结本次修改>

- <重要修改点 1>
- <重要修改点 2>
- <必要时补充影响范围、兼容性、配置或风险>
```

## Workflow

1. 先检查变更范围，优先看已暂存内容：
   - `git status --short`
   - `git diff --cached --stat`
   - `git diff --cached`
2. 如果没有暂存，但用户仍要求生成提交信息或直接提交，再看工作区变更：
   - `git diff --stat`
   - `git diff`
3. 提炼一个主线主题，再补充 2 到 4 个最重要的细节。
4. 如果用户要求实际执行 `git commit`，直接把生成的中文内容作为提交信息使用。

## Writing Rules

- 第一行必须是完整的一句话，直接概括“改了什么，以及主要目的/结果是什么”。
- 不要写空泛表达，例如“更新代码”“一些修复”“调整细节”。
- 优先突出这些高价值信息：
  - 用户可见行为变化
  - 接口、数据结构、配置项、默认值变化
  - 兼容性、迁移、回滚、风险控制
  - 关键 bug 修复
  - 性能、稳定性、可维护性改进
- 要点列表保持简洁、具体、去重，通常 2 到 4 条即可。
- 不要机械地按文件逐个罗列；要按“功能主题”组织。
- 纯格式化、重命名、生成文件噪音通常不写，除非它们就是本次提交主体。
- 如果有重要删除、降级兼容、兜底逻辑、默认行为调整，需要明确写出。
- 全部内容使用中文。

## Commit Message Form

默认使用下面这种结构：

```text
优化 xxx，补齐 xxx 的提交流程与说明质量

- 将本次改动归纳为单一主题，避免提交标题过于空泛
- 补充关键实现细节、兼容性或风险点，便于后续回溯
- 保持描述简洁，只保留对评审和排查有价值的信息
```

## Response Style

- 如果用户只是要提交说明，直接返回可用的提交内容，不要加额外铺垫。
- 如果用户要求你执行提交，先生成上述格式的内容，再用于 `git commit`。
- 如果改动明显混杂多个主题，仍要先找主线；只有在高风险歧义下才提示用户拆分提交。

## Typical Triggers

- “帮我提交这些改动”
- “给这次改动写个 commit message”
- “这个提交日志太简单了，重写一下”
- “根据当前 diff 生成中文提交信息”
- “直接提交，说明写详细一点但要简洁”
