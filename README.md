# Luna Worker 与 Sol 质量门禁

`luna_worker` 是一个处理边界清晰的独立子任务的 Codex Agent（模型 `gpt-5.6-luna`，推理强度 `max`），配合 Sol 主控验收的 Skill 使用。

## 版本说明

- **[v1](v1/)** —— 原始版本：把 Agent 和 Skill 安装到个人 Codex 目录（`~/.codex/`）后使用。
- **[v2](v2/)** —— 直接使用版本：仓库根目录即 Codex 项目，`.codex/` 自带 Agent 配置，在 Codex 中打开仓库就能用；另附“1 个主脑 + 3 个工作者”协作示意图。

两个版本共用同一份 `luna-worker.toml` 和 Skill 内容，差别在安装/使用方式与 README 说明。具体用法见各版本目录下的 README。
