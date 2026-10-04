# handoff · 项目交接

**核实项目状态，精简交接文档，让后续工作接得上。**

A small, instruction-only skill for evidence-based project handoffs.

项目做久了，交接文档会重复、版本会过期，旧待办也容易被当成当前任务。`handoff` 帮 Agent 从工作区的真实状态整理一个简洁入口，再按任务链接到权威材料。它服务于下一位 Agent，也服务于接手的人。

## 它做什么

- 核对当前版本、完成情况、下一步和需要人决定的事项。
- 把当前状态、稳定约束、证据索引与历史记录分开。
- 精简重复文本，按任务展开详细材料，保留可追溯的证据。
- 用户要求整理项目文件时，先核实引用、可再生性和独有内容，保护原始数据与冻结材料。

它不会自动创建或关闭对话、提交、发布或发送消息。交接请求也不代表授权清理文件。它不是应用运行内存优化工具，也不是整机磁盘清理工具。

## 安装

这是 GitHub 上的独立 skill 文件包，不是已经上架的插件。

在支持 `$skill-installer` 的 Codex 环境中发送：

```text
$skill-installer 从 https://github.com/jidekaixin2dian/handoff/tree/main/skills/handoff 安装 handoff。
```

也可以把本仓库的 [`skills/handoff`](skills/handoff/SKILL.md) 目录复制到项目的 `.agents/skills/handoff/`，或用户目录的 `.agents/skills/handoff/`。如已有同名 skill，先检查现有内容，避免覆盖。

目录位置与调用方式见 [OpenAI 的 skill 文档](https://learn.chatgpt.com/docs/build-skills)。它可能帮助其他支持 `SKILL.md` 的 Agent，但本次没有逐一验证其他客户端。

## 使用

```text
$handoff 我要换一个新对话继续这个项目。请核实当前状态，更新交接入口，保留关键证据和下一步。
```

```text
$handoff 帮我精简交接文档，减少重复内容，保留独有决策和证据链接。
```

```text
$handoff 只读审查当前交接文档，指出过期状态、断链和遗漏，不修改文件。
```

不要把未验证的结果写成已完成，也不要把技术检查通过写成人工接受。

## 交接前后

下面是虚构项目的结构示意，不是性能测试，也不涉及真实用户资料。

| 容易接错的交接 | 可继续工作的交接 |
| --- | --- |
| 多份文档重复完整实施历史 | 一个当前入口，按任务指向原始材料 |
| 旧清单写着“准备发布” | 当前候选版本已验证，人工验收仍待完成 |
| “可重新下载，所以删掉” | 核对引用、可再生性和唯一内容，再决定是否清理 |
| 为了复核覆盖上一轮评估 | 保留冻结结果，新评估使用新目录 |

## 检查与范围

发布前完成格式校验、边界审查和一次隔离文件演练，具体证据与局限见 [检查记录](docs/validation.md)。这是指导 Agent 工作的方法，效果取决于模型、工具权限和项目证据；本仓库没有宣称量化性能提升。

源码入口：[`SKILL.md`](skills/handoff/SKILL.md)。界面名称：**项目交接**。无需 API Key、额外依赖或配套服务即可读取技能；实际项目操作沿用用户已有环境。

## License

[MIT](LICENSE) · jidekaixin2dian
