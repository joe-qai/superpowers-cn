# Superpowers

Superpowers 是一套完整的编码代理软件开发方法论，建立在一组可组合的技能和一些初始指令之上，确保您的代理能够正确使用这些技能。

## 工作原理

从您启动编码代理的那一刻开始。一旦它发现您正在构建某个项目，它*不会*直接跳入编写代码。相反，它会退一步，询问您真正想要实现的目标。

一旦从对话中提炼出规格说明，它会以足够短的片段展示给您，让您能够真正阅读和理解。

在您批准设计后，您的代理会制定一个清晰的实施计划，即使是一个热情但品味不佳、缺乏判断力、没有项目背景且厌恶测试的初级工程师也能遵循。它强调真正的红/绿 TDD（测试驱动开发）、YAGNI（You Aren't Gonna Need It）原则和 DRY（Don't Repeat Yourself）原则。

接下来，一旦您说"开始"，它会启动一个*子代理驱动开发*流程，让代理处理每个工程任务，检查和审查他们的工作，并继续前进。Claude 能够自主工作几个小时而不偏离您制定的计划，这并不罕见。

还有更多功能，但这是系统的核心。由于技能会自动触发，您不需要做任何特殊操作。您的编码代理就是拥有超级能力的。

## 赞助

如果 Superpowers 帮助您完成了赚钱的工作，并且您愿意的话，我将非常感激您考虑[赞助我的开源工作](https://github.com/sponsors/obra)。

谢谢！

- Jesse

## 安装

**注意：** 安装方式因平台而异。

### Claude Code 官方市场

Superpowers 可通过[官方 Claude 插件市场](https://claude.com/plugins/superpowers)获取

从 Anthropic 的官方市场安装插件：

```bash
/plugin install superpowers@claude-plugins-official
```

### Claude Code（Superpowers 市场）

Superpowers 市场提供 Superpowers 和其他一些相关插件供 Claude Code 使用。

在 Claude Code 中，首先注册市场：

```bash
/plugin marketplace add obra/superpowers-marketplace
```

然后从此市场安装插件：

```bash
/plugin install superpowers@superpowers-marketplace
```

### OpenAI Codex CLI

- 打开插件搜索界面

```bash
/plugins
```

搜索 Superpowers

```bash
superpowers
```

选择 `Install Plugin`

### OpenAI Codex 应用

- 在 Codex 应用中，点击侧边栏的插件。
- 您应该在编码部分看到 `Superpowers`。
- 点击 Superpowers 旁边的 `+` 并按照提示操作。

### Cursor（通过插件市场）

在 Cursor Agent 聊天中，从市场安装：

```text
/add-plugin superpowers
```

或者在插件市场中搜索 "superpowers"。

### OpenCode

告诉 OpenCode：

```
Fetch and follow instructions from https://raw.githubusercontent.com/obra/superpowers/refs/heads/main/.opencode/INSTALL.md
```

**详细文档：** [docs/README.opencode.md](docs/README.opencode.md)

### GitHub Copilot CLI

```bash
copilot plugin marketplace add obra/superpowers-marketplace
copilot plugin install superpowers@superpowers-marketplace
```

### Gemini CLI

```bash
gemini extensions install https://github.com/obra/superpowers
```

更新命令：

```bash
gemini extensions update superpowers
```

## 基本工作流程

1. **brainstorming（头脑风暴）** - 在编写代码前激活。通过问题完善粗略想法，探索替代方案，分节呈现设计供验证。保存设计文档。

2. **using-git-worktrees（使用 git worktrees）** - 在设计批准后激活。在新分支上创建隔离的工作空间，运行项目设置，验证干净的测试基线。

3. **writing-plans（编写计划）** - 在设计获得批准时激活。将工作分解为易于处理的任务（每项 2-5 分钟）。每个任务都有确切的文件路径、完整的代码和验证步骤。

4. **subagent-driven-development（子代理驱动开发）** 或 **executing-plans（执行计划）** - 在有计划时激活。为每个任务分派新的子代理，进行两阶段审查（规格合规性，然后是代码质量），或者分批执行并设置人工检查点。

5. **test-driven-development（测试驱动开发）** - 在实现过程中激活。强制 RED-GREEN-REFACTOR：编写失败的测试，观察它失败，编写最少的代码，观察它通过，提交。删除在测试之前编写的代码。

6. **requesting-code-review（请求代码审查）** - 在任务之间激活。对照计划进行审查，按严重程度报告问题。关键问题会阻止进度。

7. **finishing-a-development-branch（完成开发分支）** - 在任务完成时激活。验证测试，提供选项（合并/PR/保留/放弃），清理工作树。

**代理在执行任何任务前都会检查相关技能。** 这些是强制性工作流，而非建议。

## 内置内容

### 技能库

**测试**
- **test-driven-development** - RED-GREEN-REFACTOR 循环（包含测试反模式参考）

**调试**
- **systematic-debugging** - 4阶段根本原因流程（包含根本原因追踪、纵深防御、基于条件的等待技术）
- **verification-before-completion** - 确保问题真正被修复

**协作**
- **brainstorming** - 苏格拉底式设计完善
- **writing-plans** - 详细的实施计划
- **executing-plans** - 带检查点的批量执行
- **dispatching-parallel-agents** - 并发子代理工作流
- **requesting-code-review** - 审查前检查清单
- **receiving-code-review** - 响应反馈
- **using-git-worktrees** - 并行开发分支
- **finishing-a-development-branch** - 合并/PR 决策工作流
- **subagent-driven-development** - 快速迭代，两阶段审查（规格合规性，然后是代码质量）

**元技能**
- **writing-skills** - 按照最佳实践创建新技能（包含测试方法论）
- **using-superpowers** - 技能系统介绍

## 理念

- **测试驱动开发** - 始终先写测试
- **系统化而非临时** - 流程优先于猜测
- **减少复杂性** - 简洁是首要目标
- **证据优先于声明** - 在宣布成功前进行验证

阅读[原始发布公告](https://blog.fsck.com/2025/10/09/superpowers/)。

## 贡献

Superpowers 的一般贡献流程如下。请记住，我们通常不接受新技能的贡献，并且任何技能更新必须在我们支持的所有编码代理上都能工作。

1. Fork 仓库
2. 切换到 'dev' 分支
3. 为您的工作创建一个分支
4. 遵循 `writing-skills` 技能来创建和测试新技能或修改现有技能
5. 提交 PR，务必填写拉取请求模板。

完整指南请参阅 `skills/writing-skills/SKILL.md`。

## 更新

Superpowers 的更新在某种程度上取决于编码代理，但通常是自动的。

## 许可证

MIT 许可证 - 详见 LICENSE 文件

## 社区

Superpowers 由 [Jesse Vincent](https://blog.fsck.com) 和 [Prime Radiant](https://primeradiant.com) 的其他人员构建。

- **Discord**：[加入我们](https://discord.gg/35wsABTejz) 获取社区支持、提问并分享您使用 Superpowers 构建的内容
- **Issues**：https://github.com/obra/superpowers/issues
- **发布公告**：[注册](https://primeradiant.com/superpowers/) 以获取新版本通知