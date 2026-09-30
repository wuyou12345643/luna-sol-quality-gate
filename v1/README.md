# Luna Worker 与 Sol 质量门禁

为 Codex 提供范围明确的 Luna Worker，以及由 Sol 主控检查实际产物后交付的协作 Skill。

## 文件

- `agents/luna-worker.toml`：命名 Agent `luna_worker`，使用 `gpt-5.6-luna`，推理强度 `max`。
- `skills/luna-sol-quality-gate/SKILL.md`：委派任务、主控验收和质量门禁流程。

## 安装

把 `agents/luna-worker.toml` 复制到 `~/.codex/agents/luna-worker.toml`。
把 `skills/luna-sol-quality-gate` 文件夹复制到 `~/.codex/skills/luna-sol-quality-gate`。
如目标已存在，请先比较内容并保留原有自定义设置。新建 Codex 对话，使其发现新增文件。

## 使用

在模型选择器中手动选择 Sol 作为主控，再输入：

```text
$luna-sol-quality-gate 帮我完成：[你的任务]
```

主控按需委派边界清晰的独立子任务给 `luna_worker`，读取实际产物并运行适用检查；失败或必要证据缺失时不得宣称完成。
简单任务由主控直接完成。Worker 不修改整体目标，不扩大范围，也不创建更多代理。

## 兼容性与限制

Agent 使用 `name`、`description`、`developer_instructions`、`model`、`model_reasoning_effort` 字段。
本地配置格式曾在 Codex CLI `0.158.0-alpha.2.1` 检查，内置目录列出 `gpt-5.6-luna` 支持 `max`；实际模型访问和子代理能力取决于当前账号及运行环境。

这是指令层面的质量门禁，不会自动切换主控模型，也不替代 CI 或权限控制。无法确认 Sol 主控完成验收时，状态应为“待 Sol 验收”。
