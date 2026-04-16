# Producer Project Constraints

本文件为 `/root/codes/producer` 的项目级约束，只作用于当前项目。

## Python 虚拟环境

- 本项目的 Python 相关命令默认使用项目级虚拟环境 `/root/codes/producer/.venv`。
- 执行 Python、pip、pytest 或其他 Python 工具时，优先直接调用 `.venv/bin/python`、`.venv/bin/pip`、`.venv/bin/pytest`、`.venv/bin/<tool>`，不要默认使用系统解释器，也不要依赖 `source` 激活后的隐式路径。
- 若本项目缺少 Python 依赖，优先安装到 `.venv` 中，不要写入系统级 Python 环境。
- 当需要在回复、脚本或自动化命令中展示 Python 用法时，默认展示项目内虚拟环境的可执行路径。
- 若 `.venv` 缺失或损坏，可在项目根目录重新执行 `python3 -m venv .venv` 创建；该操作仍需遵守上层关于 Python 命令默认走沙箱外执行路径的全局约束。

## 约束优先级

- 本文件补充项目级规则，不覆盖更高优先级的系统、开发者或全局约束。
- 若项目级规则与上层约束冲突，以上层约束为准。
