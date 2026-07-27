# AI-4U

## 不懂提示词、不懂代码，也能轻松使用 AI

**AI-4U 专为 AI 新手设计。你只管说人话，AI 会主动引导你、理解你，再帮你做事。**

你是否也遇到过这些情况：

- 知道 AI 很强，却不知道它到底能帮自己做什么。
- 脑中有一个模糊想法，却不知道该怎样告诉 AI。
- 不懂提示词、代码和专业术语，担心自己不会用。
- 只说了一句话，AI 就直接开始写代码，最后做出来的东西并不是自己想要的。
- 和 AI 反复修改很多次，浪费了时间和额度，项目还是越来越乱。

AI-4U 就是为这些情况准备的。

你不需要先学习怎么使用 AI，也不需要把需求想得很完整。像平时聊天一样，说出你的处境、烦恼或一个模糊念头就可以。

AI 会用大白话和你交流，一步步帮你发现方向、说明想法、补齐真正重要的信息。等它真正理解你想要什么以后，再开始做事。

**先让新手能够轻松开口，再让 AI 真正听懂用户——这就是 AI-4U。**

### 当你没有想法时

AI 不会反复追问“你想做什么”，也不会丢给你一大堆看不懂的固定菜单。它会从你的工作、生活、兴趣、经验和烦恼出发，帮你发现 AI 可能真正帮得上忙的方向。

### 当你已经有想法时

AI 不会只听到“做一个网站”就马上开工。它会先弄明白你想达到什么结果、目前有什么条件、有哪些限制，以及怎样才算完成，减少做错方向和反复返工。

### 一个简单例子

没有 AI-4U：

> 你：我想做一个赚钱的小工具。
>
> AI：好的，我现在开始创建项目……

使用 AI-4U：

> 你：我想做一个赚钱的小工具。
>
> AI：可以。你不需要先想好做什么，我们先从你熟悉的事情开始。你平时最常接触什么？有哪些事情让你觉得麻烦、重复，或者别人也经常抱怨？

**AI-4U 不要求你先学会 AI，也不替你决定，而是帮助你从“我不知道”走到“我知道下一步该做什么”。**

## 下载

- [下载完整项目 ZIP](https://github.com/yuanlalaini-bit/ai-4u/archive/refs/heads/main.zip)
- [下载可直接导入 WorkBuddy 的 Skill 包](https://github.com/yuanlalaini-bit/ai-4u/releases/download/v0.1.0/ai-4u-skill-v0.1.0.zip)

本项目采用 MIT 许可证，任何人都可以免费下载、使用、修改和分享。

## 它是怎样做到的

AI-4U 使用 OpenAI 为 Codex 推荐的四部分任务公式：

- **Goal**：想达到什么结果
- **Context pointers**：相关文件、资料、环境和背景
- **Constraints**：必须遵守、避免或保留什么
- **Done when**：怎样才算完成

你不需要记住或按格式填写。AI 会从对话和现有资料中提取已知信息，只补问真正影响结果的缺口。

AI-4U 不是一个新的 AI，也不会替换你正在使用的模型。它是一套可以安装到 Codex、Claude Code、Cursor、WorkBuddy 等 Agent 中的协作规则，让原来的 AI 更懂得怎样帮助你。

## 它会做什么

- 有想法：通过自然交流补全任务，再开始执行。
- 没想法：了解你的情况，动态推荐 3–7 个大方向。
- 新手：默认大白话，必要术语随手解释。
- 熟练用户：减少基础说明，直接讨论方案。
- 开发任务：四部分足够明确前，不开始代码或文件修改。
- 完成任务：按 Constraints 和 Done when 验证，不虚报完成。

## 为什么同时提供 Skill 和全局规则

`SKILL.md` 通常按需加载，不能保证每个新对话都自动生效。要让 AI-4U 持续作为基础规则，需要使用对应平台的全局适配文件。

本仓库只有一个 Skill；`adapters/` 只是同一套规则在不同平台的常驻安装版本，不是多个 Skill。

## 安装

### 核心 Skill

如果平台支持 Agent Skills，将 [`skills/ai-4u`](skills/ai-4u) 复制到该平台的个人 Skill 目录。

如果平台只支持全局规则、不支持 Skill，直接使用下方对应的全局适配文件即可。

### 全局常驻规则

| 平台 | 使用文件 | 全局位置或入口 |
|---|---|---|
| OpenAI Codex | [`AGENTS.md`](adapters/codex/AGENTS.md) | `~/.codex/AGENTS.md` |
| Claude Code | [`CLAUDE.md`](adapters/claude-code/CLAUDE.md) | `~/.claude/CLAUDE.md` |
| Cursor | [`USER_RULES.txt`](adapters/cursor/USER_RULES.txt) | Cursor Settings → Rules → User Rules |
| Gemini CLI | [`GEMINI.md`](adapters/gemini/GEMINI.md) | `~/.gemini/GEMINI.md` |
| Google Antigravity | [`GEMINI.md`](adapters/gemini/GEMINI.md) | Customizations → Rules → Global |
| GitHub Copilot CLI | [`copilot-instructions.md`](adapters/github-copilot/copilot-instructions.md) | `~/.copilot/copilot-instructions.md` |
| 腾讯 WorkBuddy / CodeBuddy | [`ai-4u.md`](adapters/workbuddy/ai-4u.md) | `~/.codebuddy/rules/ai-4u.md` |

如果目标文件已有内容，请合并，不要直接覆盖。

### WorkBuddy 安装

- **全局常驻规则（推荐）**：将 [`adapters/workbuddy/ai-4u.md`](adapters/workbuddy/ai-4u.md) 复制到 `~/.codebuddy/rules/ai-4u.md`。`alwaysApply: true` 会让规则在所有项目中自动加载。
- **WorkBuddy Skill**：在“技能 → 添加技能 → 上传技能”中导入 `skills/ai-4u` 的压缩包。Skill 会在相关任务中自动调用，但不等同于全局常驻规则。

## 重要边界

- AI-4U 不控制推理程度，完全尊重用户在平台中的选择。
- “四部分明确”是理解门槛，不是固定问卷；简单且清楚的任务可以直接执行。
- 全局规则属于持久提示，不是技术上的强制拦截。平台系统规则、权限和安全限制始终优先。
- Goal / Context pointers / Constraints / Done when 是 OpenAI 对 Codex 的推荐公式；AI-4U 将它作为跨平台任务理解框架，不声称其他厂商也官方推荐同一名称。

## 官方依据

- [OpenAI Codex Prompt Formula](https://academy.openai.com/public/clubs/higher-education-05x4z/resources/codex-for-faculty-and-researchers-follow-along-guide-2026-06-09)
- [Codex：AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [Claude Code：CLAUDE.md](https://code.claude.com/docs/en/memory)
- [Cursor：Rules](https://docs.cursor.com/context/rules)
- [Gemini CLI：GEMINI.md](https://google-gemini.github.io/gemini-cli/docs/cli/gemini-md.html)
- [GitHub Copilot：Custom instructions](https://docs.github.com/en/copilot/reference/custom-instructions-support)
- [Google Antigravity：Rules](https://antigravity.google/docs/rules-workflows)
- [WorkBuddy：技能](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [CodeBuddy：Skills](https://www.codebuddy.cn/docs/cli/skills)
- [CodeBuddy：全局规则目录](https://www.codebuddy.cn/docs/cli/codebuddy-dir)

## License

[MIT](LICENSE)
