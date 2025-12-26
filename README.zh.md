<div align="center">
  <img src="https://i.imgur.com/v0Tx6am.png" alt="AI Code Guide" />
  <p align="center">
    By <a href="https://x.com/aut0mata">Vilson Vieira</a> and
       <a href="https://x.com/esrtweet">Eric S. Raymond</a>
  </p>
  <a href="https://discord.gg/NrDfXmtvw3">
     <img src="https://i.imgur.com/uqKVFHj.png" alt="Join our Discord" height="48" />
  </a>
</div>
<br/>

> 关于使用 AI 来帮助你编程和/或为你编程，你想知道的一切。

<div align="center" style="font-size: 30px">
  <a href="#vibe">TL;DR 直接告诉我如何 vibe code 😎！</a>
</div>
<br /><br />

## 简介

我们与计算机交互以及为它们编写代码的方式正在改变。这是一个深刻的变化：涉及我们使用的工具、我们编码的方式以及我们对软件产品和系统的思考方式。

而且变化非常快！新的 LLM 模型每周都在发布。新工具、新编辑器、新的 "vibe coding" 实践、新协议 MCP、A2A、SLOP……要跟上所有这些真的很难。一切都分散在不同的地方：网站、代码库、YouTube 视频等。

这就是我们决定编写本指南的原因。我们试图将所有内容整合在一起，以无障碍的形式为你呈现围绕 **AI coding** 或 **AI assisted code generation** 的实践和工具，一切都在一个地方，简单明了。

- **如果你是一名程序员但还没有使用 AI 代码助手**，本指南适合你：它介绍了最新的工具和最佳实践，帮助你充分利用它们来完成日常工作。无论是让 AI 成为你的 copilot，还是你成为 AI agent 的 copilot。

- **如果你从未编程过，但对这个新的 "vibe coding" 感兴趣，想用它来构建自己的 SaaS 和其他软件产品**，本指南绝对适合你：我们会尽力消除晦涩难懂的内容，为你提供开始旅程所需的一切，同时严格区分真正重要的内容和"只是炒作"的内容。

好的，让我们开始吧！

📚 资源：

- [The End of Programming as We Know It](https://www.oreilly.com/radar/the-end-of-programming-as-we-know-it) by Tim O'Reilly
- [How to prepare for the future of development and AI](https://www.youtube.com/watch?v=BP54GqVK3JA) by Santiago
- [The revenge of the junior developer](https://sourcegraph.com/blog/revenge-of-the-junior-developer) by Steve Yegge
- [Dear Student: Yes, AI is here, you're screwed unless you take action...](https://ghuntley.com/screwed/) by Geoffrey Huntley
- [How to Build an Agent](https://ampcode.com/how-to-build-an-agent) by Thorsten Ball
- [Using LLMs for code](https://simonwillison.net/2025/Mar/11/using-llms-for-code/) by Simon Willison
- [The 70% problem: Hard truths about AI-assisted coding](https://addyo.substack.com/p/the-70-problem-hard-truths-about) by Addy Osmani
- [Become an AI-augmented engineer](https://maryrosecook.com/blog/post/become-an-ai-augmented-engineer) by Mary Rose Cook
- [Raising an Agent podcast](https://ampcode.com/podcast) by Amp team
- [Software Is Changing (Again)](https://www.youtube.com/watch?v=LCEmiRjPEtQ) by Andrej Karpathy

## AI coding？Vibe coding？

这些术语都非常相似。但基本上，AI coding 是关于使用 AI 模型（特别是现在的 LLM）及其周围的工具来帮助你编写软件。它也被称为 "AI for code generation" 或简称为 "code gen"，这是一个迷人的研究和工程领域，可以追溯到 1950 年代我们使用 Lisp 生成代码的时候。现在我们有了 LLM 作为代码生成的主要引擎，还有一些关于神经符号混合方法的线索开始出现。AI coding 也是一种实践：如果你使用 Cursor 并通过 tab-tab-tab 的方式获得补全，你就是在 "AI coding"；如果你完全使用 Cursor 的 agent mode，你也是在 "AI coding"。总之：这是使用 AI 模型帮助你生成代码的任何方式。通常这个群体中的人已经知道如何编码。

Vibe coding 是 AI coding 的升级版 :-) 在这里，你不太关心生成的代码，你只是给出一个 prompt，期望 AI 为你编写所有代码。这个术语由 [Karpathy](https://x.com/karpathy/status/1886192184808149383) 在 2025 年创造，现在非常流行。在我看来，它正在帮助从未想过编程的每个人实现编程的民主化！

所以，总结一下，无论你是使用 AI 来讨论你的软件想法，还是只帮助编写现有代码库的部分代码，或者完全进行 vibe coding，你都在使用 AI 来帮助你生成代码。让我们称之为 AI coding，然后继续。

## 如何使用？

你可以通过多种不同的方式使用 AI coding，但总结如下：

- AI 是你的 copilot：你使用 AI 模型来增强自己，提高生产力。无论是启动 ChatGPT 来帮助你为 SaaS 进行头脑风暴，还是使用 Cursor 来自动补全你的 docstrings。这里有很多好处，特别是对于创意探索和自动化工作的无聊部分。

- AI 是 pilot：这里你是 copilot。这就是 "vibe coding" 发生的地方。你打开 Cursor Agent YOLO mode，信任 agent 所做的一切来生成你的代码。这是一种非常强大的自动化方式，但需要一些关于如何设计系统、驯服 agent 以及跳入你实际上不知道的代码混乱中的最佳实践，特别是在解决错误时。

你应该学习并实践这两种方式！

但随着项目复杂度的增加，应该更多地倾向于 copiloting，远离纯粹的 YOLO vibecoding。越有可能需要另一个人（或六个月后的你自己）来维护代码，这一点就越重要。

# 🗺️ 路线图

## 如何开始？

- 如果你不知道如何编程，想尝试一下，我们建议从一些基于 Web 的工具开始，如 [Bolt](https://bolt.new)、[Replit](https://replit.com)、[v0](https://v0.dev) 或 [Lovable](https://lovable.dev)。

- 如果你已经知道如何编程，安装 [Cursor](https://cursor.com/) 或 [Windsurf](https://windsurf.com/)。你可以从免费计划开始，然后升级到每月 $20 的计划。Cursor 非常好且便宜，因为你可以使用大量 tokens 来使用最新的 LLM 模型。VSCode 最近也推出了自己的 [Agent Mode](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode)。它与 Github Copilot 配对，使用 Agentic Workflow 来更改和编辑文件。其他编辑器也在快速添加 Agentic 功能，所以请查看你最喜欢的编辑器网站以获取更多信息。这些 agentic 功能通常只在 Beta 或 Insider builds 中启用。

- 如果你想要一个更开源的选择，试试 [OpenHands](https://github.com/All-Hands-AI/OpenHands)。你将其作为 Docker container 运行，暴露一个 webapp。你需要创建一个 [Anthropic API account](https://console.anthropic.com/) 来获取 API key，或使用 [OpenRouter](https://openrouter.ai/) 中可用的某些 LLM。

- 如果你已经知道如何编程，并且像我们一样是 terminal maniac，查看 [aider](https://aider.chat/)、[Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) 或 [OpenAI Codex](https://github.com/openai/codex)。对于这些，你需要为 Anthropic Claude、OpenAI GPT 或 OpenRouter 设置 API keys。

- 如果你已经知道如何编程，既喜欢 terminal 又喜欢 VSCode 风格，并且真的想尝试让 subagents 并行为你运行的强大功能，不关心成本但关心把事情做好，试试 [Amp](https://ampcode.com)。

> 建议：我们强烈建议在 OpenRouter 创建一个账户。这真的很简单，你可以访问最新的 LLM 模型，甚至免费版本。例如，我们这些天常用的 LLM 模型是 Gemini 2.5 Pro，可以通过 OpenRouter 免费运行（有每日 credits 配额，但对于使用 aider 和 OpenHands 进行实验来说，这仍然是一个有趣的选择）。

> 重要提示：Claude Code 现在非常昂贵！你很容易每天花费 $50。所以要小心，监控你的使用情况。这就是为什么建议从 Cursor 开始，这样你就不必担心这个问题。

📚 资源：

- [Vibe Coding 101 with Replit](https://www.deeplearning.ai/short-courses/vibe-coding-101-with-replit/)
- [Cursor AI Tutorial for Beginners [2025 Edition]](https://www.youtube.com/watch?v=3289vhOUdKA)

## 如何为编程编写 prompt？又名如何 vibe code？<a id='vibe'></a>

在你安装并稍微使用这些工具后，你会注意到它们会 hallucinate，进入无休止的循环来尝试修复可能的错误等。知道如何编写好的 prompt 很重要。一些提示：

- 不要在一个 prompt 中问所有问题。仅仅 prompt "嘿，为我构建一个宠物店应用" 对软件工程师没有帮助，对 AI 更是如此 :-) 理解你的项目，首先与 LLM 进行头脑风暴，创建 PRD（Product Requirements Document），制定计划并将其拆分为任务。你会在下面找到一个关于如何使用 ChatGPT 为你创建一个的配方。
- 给它详细信息。如果你知道你想要什么，说出来。如果你知道你想要哪种编程语言、哪种 tech stack、什么类型的受众，将其添加到你的 prompt 中。
- Markdown 或任何其他轻量级基于文本的格式（如 asciidoc）应该适合 LLM 解释。最终文本将被编码为 tokens。但是，为了强调 prompt 的特定部分，建议使用一些符号，如 [XML tags](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags)。
- 将你的项目分解为任务和子任务。
- 为不同的目标尝试不同的模型。
- 尝试不同的模型来确认和验证其他模型的输出。
- LLM 是 "yes machines"，所以要应用批判性思维。

在我们的其余示例中，我们将使用与 Markdown 关联的 .md 文件扩展名。如果你更喜欢 asciidoc（它对结构化文档有更好的支持），请使用它并在这些说明中替换 ".adoc"。LLM 不在乎，它们会处理 Markdown 或 asciidoc 或你扔给它们的任何其他纯文本格式。

这是一个通常效果很好的方法/程序/策略/工作流：

1. 使用 `ChatGPT 4.5`、`4o` 或 `o3` 并输入以下 prompt：

```
You're a senior software engineer. We're going to build the PRD of a project
together.

VERY IMPORTANT:
- Ask one question at a time
- Each question should be based on previous answers
- Go deeper on every important detail required

IDEA:
<paste here your idea>
```

2. 你将进入几分钟的问题/答案循环。尝试尽可能详细地回答。完成后（或当你认为足够时），发送此 prompt 来指导模型将其编译为 PRD：

```
Compile those findings into a PRD. Use markdown format. It should contain the
following sections:

- Project overview
- Core requirements
- Core features
- Core components
- App/user flow
- Techstack
- Implementation plan
```

3. 复制此文件并将其保存到项目文件夹内的 `docs/specs.md`
4. 现在让我们为你的项目创建任务列表。询问以下内容：
```
Based on the generated PRD, create a detailed step-by-step plan to build this project.
Then break it down into small tasks that build on each other.
Based on those tasks, break them into smaller subtasks.
Make sure the steps are small enough to be implemented in a step but big enough
to finish the project with success.
Use best practices of software development and project management, no big
complexity jumps. Wire tasks into others, creating a dependency list. There
should be no orphan tasks.

VERY IMPORTANT:
- Use markdown or asciidoc
- Each task and subtask should be a checklist item
- Provide context enough per task so a developer should be able to implement it
- Each task should have a number id
- Each task should list dependent task ids
```
5. 将其保存为项目文件夹内的 `docs/todo.md`

[这里有一个示例](https://chatgpt.com/share/67f8e8c6-c92c-8007-8fe0-76bdc73f9812)，展示了使用 ChatGPT 4o 为简单 CLI 工具完成的头脑风暴/规划会话，用它作为你的灵感。

现在为你的项目创建一个本地文件夹，记住在文件夹内安装并运行 `git init` 以将其置于 version control 下。

这应该为你提供构建项目的 PRD 和任务列表！有了这些，你可以打开 Cursor（或其他 AI 代码编辑器），指向这些文件并询问：

```
You're a senior software engineer. Study @docs/specs.md and implement what's
still missing in @docs/todo.md. Implement each task each time and respect task
and subtask dependencies. Once finished a task, check it in the list and move
to the next.
```

在 Cursor Agent 第一次执行命令时启用 YOLO mode，然后在 prompt 中继续接受或询问 `continue`。

在 Cursor 的情况下，有时 LLM 会达到某些限制并要求 retry。只需执行并继续。是的，你在 vibe coding :-)

这里你可以找到一个基于此工作流在 10 分钟内构建的 CLI 工具的 Git repos：https://github.com/automata/localbiz

> 重要提示：虽然 "vibe code" 非常酷，但了解你在做什么也真的很有趣 :-) 审查 agent 正在生成的代码也会在错误发生时（它们会发生！）对你帮助很大，并提高你的代码审查技能（不仅是由 AI 完成的，还有你自己和其他开发人员完成的）。

📚 资源：

- [You are using Cursor AI incorrectly...](https://ghuntley.com/stdlib/) by Geoffrey Huntley：Geoff 在这里介绍了他使用 Cursor rules 标准库的想法
- [From Design doc to code: the Groundhog AI coding assistant (and new Cursor vibecoding meta)](https://ghuntley.com/specs/) by Geoffrey Huntley：上一篇文章的第 2 部分，Geoff 建议使用 LLM 自动构建 specs（PRD）和 Cursor rules
- [My LLM codegen workflow atm](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/) by Harper Reed
- [An LLM Codegen Hero's Journey](https://harper.blog/2025/04/17/an-llm-codegen-heros-journey/) by Harper Reed
- [Claude Code: Best practices for agentic coding](https://www.anthropic.com/engineering/claude-code-best-practices) by Anthropic：这是针对他们的 Claude Code 工具的，但它有基于任何 LLM 模型的 AI coding 工作流的有趣提示
- [Prompt Engineering](https://www.kaggle.com/whitepaper-prompt-engineering) by Lee Boonstra from Google：这是一份 70 页的文档，包含关于如何 prompt engineer 的有趣提示，其中有一节关于 code generation
- [Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering) by Anthropic
- [GPT 4.1 Prompting Guide](https://cookbook.openai.com/examples/gpt4-1_prompting_guide) by OpenAI
- [RepoPrompt](https://repoprompt.com/) 是一个帮助从项目中组装 context 的工具。值得观看 [RepoPrompt Workflow](https://www.youtube.com/watch?v=fm3VreCt-5E) 的概述视频，了解如何轻松利用这些工具在你的 vibe coding prompts 中提供更多 context。
- [Not all AI-assisted programming is vibe coding (but vibe coding rocks)](https://simonwillison.net/2025/Mar/19/vibe-coding/) by Simon Willison

## 我应该使用哪个 LLM 模型？

LLM 针对不同的目标进行训练和微调，这里是一个全面的目标/用途列表以及应该使用哪个模型：

| 目标                 | 模型                                                        |
|----------------------|---------------------------------------------------------------|
| Brainstorming        | GPT 5, 4o, o3, Grok                                           |
| Coding               | Claude Sonnet 4, Gemini 2.5 Pro, Grok, GPT 5, o3, o4-mini     |

由于 LLM 每天都在变化，这个表很快就会过时。请查看以下排行榜以进行更准确的比较：

- [OpenRouter's Models](https://openrouter.ai/models?categories=programming&fmt=table)：将类别设置为 `programming` 并仅过滤支持 `tools` 的模型通常是选择用于 AI assisted coding 的模型的好方法
- [Models.dev](https://models.dev)：AI 模型的开源数据库
- [Agent Leaderboard](https://huggingface.co/spaces/galileo-ai/agent-leaderboard)

## 当可怕的 "rate limit" 消息出现时该怎么办

切换到不同的模型。

至少有两个不同的原因可能导致这种情况。你可能发出了一个超过模型 input/output token limit 的重请求。或者，如果运行它的 server cluster 遇到糟糕的一天，你可能会被 throttled 以减少负载。你收到的错误消息通常对此不透明。你可以在这里找到更详细的解释 [here](https://platform.openai.com/docs/guides/rate-limits)。

不同的模型有非常不同的 token limits。例如，在我写这篇文章的 2025 年 4 月下旬，gpt-4.1-mini 比 gpt-4.1 慷慨得多。在你的口袋里准备几个 API keys（这很便宜，因为你按需付费）并访问描述 rate limits 的页面。这里是 [Anthropic's](https://console.anthropic.com/settings/limits) 的一个示例。

## 如何设置项目范围的规则？

你可以通过在 LLM 的 context 中"注入"它们来定义将应用于项目的规则或约定。每个编辑器都有一些方法可以做到这一点：

- 在 Cursor 中，只需在 `.cursor/rules/` 文件夹内创建 markdown 文件。Cursor 将确保在与 LLM 的所有通信中应用这些文件。
- 在 Aider 中，创建包含你想要使用的 [rules/conventions](https://aider.chat/docs/usage/conventions.html) 的 markdown 文件（如 `rules.md`），并在 `.aider.conf.yml` 文件中添加以下内容：`read: rules.md`。

此外，许多工具支持在 home directory 中配置 rules/conventions 文件以应用于所有项目。例如，在 Aider 中，你基本上可以在名为 `~/.global_conventions.md` 的文件中添加全局约定，然后使用 `read: [~/.global_conventions.md, rules.md]` 将其添加到 `.aider.conf.yml`。

你可以将 PRD 的一部分添加为规则，例如 tech stack 或代码格式和样式的一些指南。

规则非常强大，你甚至可以使用 AI 本身为你创建规则！[查看 Geoff 的方法](https://ghuntley.com/specs/)。

📚 资源：

- [Cursor Rules Docs](https://docs.cursor.com/context/rules-for-ai)
- [Windsurf Rules Docs](https://windsurf.com/editor/directory)
- [Aider Conventions Docs](https://aider.chat/docs/usage/conventions.html)
- [Aider Conventions Collection](https://github.com/Aider-AI/conventions)：社区贡献的用于 Aider 的约定文件集合
- [Awesome Cursor Rules](https://github.com/PatrickJS/awesome-cursorrules)：用于增强 Cursor AI 体验的 awesome .cursorrules 文件的精选列表

## 如何避免 hallucination？什么是 PRD？

PRD。什么？！他们说解决工程问题的最佳方法是创建一个新首字母缩略词，这里也不例外 :-) 开玩笑的……PRD 是 Product Requirements Document 的缩写。基本上，它只是一堆文档（或只有一个文档），描述你的软件项目的要求和其他细节。

事实证明，如果你让你的 LLM 自由发挥，没有太多关于要做什么的 context，它会很快且非常疯狂地 hallucinate。你需要驯服这头野兽，PRD 是做到这一点的好方法。

我最喜欢 PRD 的地方是它们对任何人都非常有帮助，从从未编程过的人到高级 SWE 或产品经理。

你不需要任何背景就可以开始 PRD，你只需要你的应用想法就可以了。

查看 <a href="#vibe">这里</a> 了解如何使用 LLM 为你创建一个。

## 保留 prompt 日志

记录你发送的每个 prompt，并（这很重要）穿插你对你在想什么的评论以及你遇到的任何惊喜。这个 prompt 日志是你的设计意图记录；对于任何没有参与项目的人来说，包括六个月后忘记你在想什么的你自己，它都是无价的。

目前还没有这个文件名称的约定，你可以使用类似 `vibecode.adoc` 或 `history.md` 的名称。

有一些工具如 [aider](https://aider.chat/) 可以记录你与 LLM 的所有来回聊天。
所以一个选择是设置以下 env vars 并将所有这些 history files 置于 version control 下：

```bash
# History Files:

## Specify the chat input history file (default: .aider.input.history)
#AIDER_INPUT_HISTORY_FILE=.aider.input.history

## Specify the chat history file (default: .aider.chat.history.md)
#AIDER_CHAT_HISTORY_FILE=.aider.chat.history.md

## Log the conversation with the LLM to this file (for example, .aider.llm.history)
#AIDER_LLM_HISTORY_FILE=.aider.llm.history
```

有了这些文件，你就可以在继续时用你自己的想法对它们进行评论。
当你（和其他人）在未来重新访问项目时，你可以从中学到很多东西，并且你可能会开始注意到可以在下次会话中使用的模式和提示。

## 如何开始我的项目？

### Webapp (Frontend)

现代 Web 开发非常令人不知所措。有大量的 JavaScript/TypeScript 框架、CSS 框架等，所以真的很难开始并考虑使用哪一个。在花了最近几周构建前端之后，这是我最终使用的：

- Next.js，这样你可以部署到 Vercel 并拥抱他们的生态系统（可能很快变得昂贵）
- Vanilla React 并使用 React Router，这样你可以部署到任何地方
- Remix，这样你可以有良好的路由支持，仍然可以部署到任何地方
- FastHTML，如果你喜欢 Python 并且更关心暴露核心 backend 功能（例如一些数据分析或 AI/ML model pipeline）而不是超级漂亮的 UI

基于 Web 的 AI coding 平台如 Lovable 使用 React，而 v0 使用 Next.js。

你可以使用的一个技巧是在 Lovable 开始你的项目（你可以在他们的免费计划中每天获得最多 5 条消息），将其设置为将项目输出到 GitHub，然后只需在你的本地机器上克隆它并使用 Cursor 继续 AI coding 它。然后你可以将其部署到 Render、Fly.io、CloudFlare 等地方。没有附加条件。如果你在后端有特定的/更复杂的例程，这特别有趣。

如果你也在编写后端，请确保在 Git repos 的 root folder 中有一个 backend 文件夹和另一个 frontend 文件夹；或者为 backend 和 frontend 使用不同的 repos，然后将它们添加到 Cursor 中的同一 workspace（这样你可以在 frontend agent 中引用 backend 的文件，反之亦然）。

为了避免过早地将 frontend 集成到 backend，指示 AI agent 使用 mock/dummy data，这样你可以在实现 backend 后稍后更新它。

另一个有趣的提示是使用好的 MCP tools 将你的 coding agent 集成到 playwright 或 browser-use。这样你可以避免从 Web 浏览器到 AI agent 的 copy-paste cycle 错误，因为 AI 将控制浏览器并自行抓取 screenshots 和 errors messages。

如果你想在 webapp 中使用 3D content 并且你正在使用 React，使用 React Three Fiber 而不是尝试直接使用 three.js library 会很有趣。R3F 使处理 state 变得更容易，因为它将所有 three.js objects 包装为 React components。

### Backend

Backend 在基于 Web 的工具（如 Lovable）中做得不好。所以你可能需要使用 Cursor/Windsurf/aider 或任何其他非基于 Web 的工具。

使用 Python 和 FastAPI 是一个很好的选择。如果你更喜欢与 frontend 使用相同的语言（猜测大多数时候是 JavaScript 或 TypeScript），你可以使用 Nodejs 和 Express。

Backend 是 end-to-end tests 的绝佳目标，所以考虑指导 agent 编写测试并为每个新功能及其子任务运行它们。

一旦你完成了 backend，你可以使用其文档（特别是 HTTP endpoints）作为在 frontend 中工作的 agent 的输入。这样你将能够将 frontend 从使用 mock/dummy data 移动到来自 backend 的真实数据。

### Game

对于小型游戏，在单个 .js 文件中使用 vanilla JS，对于 3D 游戏使用 threejs，对于 2D 游戏使用 pixijs。

游戏都是关于好的 assets，所以考虑使用 Tripo AI 和 Anything World 等服务来生成 3D assets 并 rig/animate 它们。

## 如何处理错误和 bug？

关于编码和软件，你必须知道一件事：它们会失败。无论你如何尝试防止这种情况，它都会发生。所以让我们首先接受这一点，并与错误和 bug 成为朋友。

这里的第一个策略是模仿 SWE 的做法：查看 interpreter/compiler 给你的 error message 并尝试理解它。将错误复制并粘贴回 LLM 并要求它修复它。
另一个好主意是添加用于 debugging 的 MCP tools，如 [BrowserTools](https://browsertools.agentdesk.ai/)。

## 什么是 MCP、SLOP 和 A2A，我如何从中受益？

MCP 是 Model Context Protocol 的缩写。它由 Anthropic 开发，但开始被其他 LLM（如 OpenAI 的 GPT 和 Google 的 Gemini）考虑。这是一个强大的概念，它与另一个概念密切相关：function/tool calling。

Tool calling 是 LLM 调用工具或函数来执行某些操作的一种方式。这是一种用新信息更新 LLM 的 knowledge window（在来自过去的数据上训练）的方式，同时将其与 external tools 和 endpoints 集成。例如，如果你想在 Web 上搜索某些信息，你可以指示 LLM 使用执行此操作的工具（例如 `嘿，如果你需要在 Web 上搜索某些内容，请使用此工具：search(term)`）。然后，LLM 将调用工具，获取输出，并在为你生成新预测时使用它，而不是花费大量 tokens、iteration steps 和 parsing workloads。

MCP 通过为其创建标准来扩展这个想法。这样我们可以创建一个 MCP server，它将向 LLM 暴露某些资源（例如数据库）或工具（例如将计算某些内容并返回结果的特定软件）。

等等，但这不只是一个 API 吗？我不能只用 REST API server/client 和 LLM prompts 中的一些 parsing 来模拟相同的东西吗？有点，这就是 SLOP（Simple Language Open Protocol）提出的。但是，拥有像 MCP 这样的标准使确保 LLM 原生支持它而无需在 client side 进行额外 parsing 和技巧变得更容易。

A2A（Agent to Agent Protocol）在游戏中相当新。它由 Google 创建以"补充" MCP，专注于 multiagent communication，而 MCP 专注于 LLM-tools communications。

> 重要提示：有很多好的 MCP servers，像 Cursor 这样的编辑器支持它们。目前，只有 Anthropic Claude LLM 支持它们，所以当你想要使用 MCP tools 时，请确保使用 Claude。

Anthropic 在这里保留了一个更新的 MCP servers 列表：
https://github.com/modelcontextprotocol/servers

📚 资源：

- [MCP](https://modelcontextprotocol.io/)
- [SLOP](https://github.com/agnt-gg/slop)
- [Introducing SLOP](https://russell.ballestrini.net/introducing-slop/)
- [MCP vs SLOP](https://mcpslop.com/)
- [A2A](https://google.github.io/A2A/)

## 从头开始还是使用 boilerplate？

通常 LLM 从头开始效果更好。但你也可以从 boilerplate 开始（基本上是一个 starter kit：一个包含 minimal source files 和 configs 的初始 skeletons 的文件夹，需要为特定 tech stack 运行一个工作项目），并在 context window 中添加规则以确保它将尊重你的 starter kit。

另一个好主意是使用 Cursor 自己的 indexing feature 或使用 [repomix](https://repomix.com/) 或 [files-to-prompt](https://github.com/simonw/files-to-prompt) 等工具来索引你的项目（你刚刚使用 starter kit 创建的）。

## Greenfield/clean state/fresh project vs existing codebase

如果你有一个 existing codebase，一个好主意是使用 [repomix](https://repomix.com/) 或 [files-to-prompt](https://github.com/simonw/files-to-prompt) 将其打包到 context window 中。

另一个好提示是在 task level 而不是 project level 进行 prompt 更改。例如，专注于你想要实现的一个功能，并要求 Cursor Agent 实现它。为特定功能提供一个 mini-PRD。想象一下，你正在指导 junior developer 在特定的 GH ticket 中工作 :-)

📚 资源：

- [Karpathy's tweet about his way to use AI-assisted coding](https://x.com/karpathy/status/1915581920022585597)
- [How to work with large codebases in Cursor](https://docs.cursor.com/guides/advanced/large-codebases)

## 结构良好的 prompting 用于结构良好的设计

目前（2025 年 4 月），LLM 已经擅长生成工作代码，但它们不太擅长生成结构良好的代码——即具有适当的 layering 和 separation of concerns。良好的结构对于 readability 和 maintainability 很重要，并降低了你的 defect rate。

思考你的设计，然后以产生良好结构的顺序进行 prompt-engineer。例如，在 database-centered application 中，首先指定你的 record types，然后引导 LLM 构建一个 manager class 或 module 来封装对它们的访问。只有在那之后，你才应该开始 prompting business logic。

更一般地说，当你 prompt 时，考虑将 engine code 与 policy code 分离，并以引导 LLM 这样做的顺序发出你的 prompts。

你应该在项目规则中包含一条，告诉 LLM 不要违反 layering——如果它需要新的 engine method，它应该在 clean encapsulation layer 中添加一些东西，而不是让 low-level implementation details 与 business logic 纠缠在一起。

另一个有趣的实践是从项目的核心开始，花时间确保主要功能按照你想要的方式实现和组织。你甚至可以编写 classes 和 functions skeletons，然后让 LLM 填补空白。只有在你有了良好的基础并进行了良好的测试之后，你才能转向此核心库的消费者，例如将其暴露为 CLI 或 REST API 给未来的 webapp。

## 我应该使用 TDD 或任何其他类型的测试吗？

是的，测试比以往任何时候都更重要。在 2025 年的当前 state of the art 中，LLM 擅长生成干净和正确的代码，但它们有时会 hallucinate——更重要的是，它们可能无法理解 specifications 并生成正确的代码来做错误的事情。

即使我们获得完全等同于人类的 artificial general intelligence，这种情况也不太可能改变——毕竟，人类也会误解 specifications！语言的 ambiguity 是为什么测试在未来将继续重要。

使用 TDD 创建你想要的结果的 skeletons 确实可以帮助引导 LLM 实现你正在测试的目标代码片段。指示 LLM 创建测试并运行它们也是一个很好的实践：它将能够将可能破坏给定测试的错误添加到其 context 中并采取行动，试图使 test pass。

测试是与 LLM 一起增长代码库的基础，只有在所有当前测试通过时才向前推进。

Property-based tests 在与 LLM 一起工作时真的很有趣。测试整个 domain/range of values 而不是你指出的特定值将有助于确保 agent 生成的代码即使在后来的更改最终遇到你事先没有想到的 edge cases 时仍然有效。每种语言都有用于 property-based tests 的好 libraries，例如 Python 的 [hypothesis](https://hypothesis.readthedocs.io/en/latest/) 或 JavaScript/TypeScript 的 [fast-check](https://fast-check.dev/)。

在尝试编写或修复测试时，始终检查 LLM 生成的代码也很重要：有时它们甚至会尝试生成一些 hardcoded output 只是为了通过测试 :-)

## 如何使其安全？

与非 AI assisted coding 建议的完全相同的规则和最佳实践在这里也有效。研究更多关于它们的内容并将其应用到你的代码中。这里是一个初始 safe-check list：

- 不要信任 AI 生成的代码。始终验证。记住，AI 不会对你运行的代码负责，**你会**！
- 不要将任何 API keys 或其他 secrets 存储为 hardcoded strings，特别是在 frontend code 中。在 backend 上存储为 protected environment variables（例如 Vercel 等平台提供此选项）
- 查询 API endpoints 时，始终使用 HTTPS
- 创建 HTML forms 时，始终进行 input validation 和 sanitization
- 不要在 `localStorage`、`sessionStorage` 或 cookies 中存储 sensible data
- 在 package requirements 中运行 validators 和 security vulnerability scanners

## 如何在 Claude Code 中使用任何 LLM？

你只想在 Claude Code CLI 中尝试 Kimi K2 或其他 LLM？你可以使用 claude-code-router 使 Claude Code CLI 使用在本地机器上运行的 "proxy" 将其路由到 OpenRouter 上可用的任何模型！下面的说明适用于 Kimi K2，但你可以将其调整为任何其他你想要的 LLM。

首先在 OpenRouter 创建一个账户并获取你的 API key。

确保你已安装 Claude Code CLI：

```
npm install -g @anthropic-ai/claude-code
```

然后安装 claude-code-router：

```
npm install -g @musistudio/claude-code-router
```

将以下行添加到 `~/.claude-code-router/config.json` 文件中，将 `OPENROUTER_API_KEY` 替换为来自 OpenRouter 的 API key：

```
{
  "Providers": [
    {
      "name": "kimi-k2",
      "api_base_url": "https://openrouter.ai/api/v1/chat/completions",
      "api_key": "OPENROUTER_API_KEY",
      "models": [
        "moonshotai/kimi-k2"
      ],
      "transformer": {
        "use": ["openrouter"]
      }
    }
  ],
  "Router": {
    "default": "kimi-k2,moonshotai/kimi-k2"
  }
}
```

现在只需通过 router 运行 Claude Code：

```
ccr code
```

你应该看到 Claude Code `API Base URL: http://127.0.0.1:3456`，这意味着它正在使用 claude-code-router 创建的 local proxy。就是这样！

如果你只对 Kimi K2 或 Moonshot 的其他模型感兴趣，另一种选择是使用 Moonshot 本身提供的模型：
https://github.com/LLM-Red-Team/kimi-cc/blob/main/README_EN.md

## 如何创建我自己的 AI coding agent？

我们正在编写一些关于如何做到这一点的教程，同时构建我们自己的工具，所以请保持关注。
最好的介绍是 Thorsten 的 [this practical tutorial](https://ampcode.com/how-to-build-an-agent)，你在其中构建一个使用基本 minimal amount of tools（`list_files`、`read_file`、`edit_file`）的简单 agent，在 Go 中，逐步进行。

如果你想深入了解，Gerred 的 [this series of open source books](https://gerred.github.io/building-an-agentic-system) 绝对是一个很好的开始。

# ✨ 特定工具和 Agent 的技巧和窍门

## Claude Code

- [Claude Code Guide](https://github.com/zebbern/claude-code-guide)：涵盖每个可发现的 Claude Code command，包括许多在基本 tutorials 中不广为人知或未记录的功能

# 🛠️  工具

这里我们保留了一个围绕使用 AI 进行编码的主要工具的更新列表。我们测试了其中的大部分，你会找到我们在测试它们时的诚实意见。

## Editors / IDE

- [Cursor](https://cursor.com)
- [Windsurf](https://windsurf.com)
- [Cline](https://cline.bot/)
- [OpenHands](https://github.com/All-Hands-AI/OpenHands)
- [Devin](https://devin.ai)
- [VSCode + GitHub Copilot](https://code.visualstudio.com/docs/copilot/setup)
- [Amp](https://ampcode.com)
- [Kiro](https://kiro.dev)

## CLI

- [Claude Code](https://github.com/anthropics/claude-code)
- [Aider](http://aider.chat/)
- [Claude Engineer](https://github.com/Doriandarko/claude-engineer)
- [Roo Code](https://github.com/RooVetGit/Roo-Code)
- [OpenAI Codex CLI](https://github.com/openai/codex)
- [Codebuff](https://www.codebuff.com/)
- [opencode](https://github.com/opencode-ai/opencode)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)

## Webapps

- [Bolt](https://bolt.new)
- [v0](https://v0.dev)
- [Replit](https://replit.com)
- [Lovable](https://lovable.dev)
- [Firebase Studio](https://firebase.studio/)

## Background/remote Agents

- [ZenCoder](https://zencoder.ai/)
- [CodeRabbit](https://www.coderabbit.ai/)
- [Factory AI](https://www.factory.ai/)
- [OpenAI Codex](https://chatgpt.com/codex)

## Helpful Tools

- [Specstory](https://specstory.com/)
- [Claude Task master](https://github.com/eyaltoledano/claude-task-master)
- [CodeGuide](https://www.codeguide.dev/)
- [repomix](https://repomix.com/)
- [files-to-prompt](https://github.com/simonw/files-to-prompt)
- [repo2txt](https://github.com/donoceidon/repo2txt)
- [stakgraph](https://github.com/stakwork/stakgraph)
- [Repo Prompt](https://repoprompt.com/)
- [Uzi](http://uzi.sh/)
- [Claudia](https://claudia.asterisk.so/)

# 🤗 关注谁

一些非常有趣的人正在实现 AI coding models/tools 或在自己的项目中使用它。

- [Addy Osmani](https://x.com/addyosmani)
- [Andrej Karpathy](https://x.com/karpathy)
- [Beyang Liu](https://x.com/beyang) (Amp)
- [Cat Wu](https://x.com/_catwu) (Claude Code)
- [Eric S. Raymond](https://x.com/esrtweet)
- [Eyal Toledano](https://x.com/EyalToledano) (TaskMaster)
- [Geoffrey Huntley](https://x.com/GeoffreyHuntley)
- [Gerred Dillon](https://x.com/devgerred)
- [Harper Reed](https://x.com/harper)
- [Nathan Wilbanks](https://x.com/NathanWilbanks_) (agnt, SLOP)
- [Pietro Schirano](https://x.com/skirano)
- [Quinn Slack](https://x.com/sqs) (Amp)
- [Sandeep Pani](https://x.com/skcd42) (Aider, AgentFarm)
- [Simon Willison](https://x.com/simonw)
- [Vilson Vieira](https://x.com/aut0mata)
- [Thorsten Ball](https://x.com/thorstenball) (Amp)
- [Xingyao Wang](https://x.com/xingyaow_) (OpenHands, AllHands)

# 💖 致谢

本指南受到 Maxime Labonne 的精彩 [llm-course](https://github.com/mlabonne/llm-course) 的启发。

特别感谢：

- [Gabriela Thumé](https://github.com/gabithume) 的一切 ❤️
- [Albert Espín](https://github.com/albert-espin) 的深思熟虑的反馈和第一批错误更正
- [Geoffrey Huntley](https://x.com/GeoffreyHuntley) 向我指出 property-based tests 以及他所有关于 autonomous agents 的精彩教程和实验
- ChatGPT 4o 生成了你在顶部看到的横幅，灵感来自令人难以置信的艺术家 [Deathburger](https://citadel9.com/)

# ⭐ 贡献

如果你想贡献更正、反馈或一些缺失的工具或参考，请随时打开新的 PR、新的 issue 或与 [Eric](https://x.com/esrtweet) 或 [Vilson](https://x.com/aut0mata) 联系。

如果你喜欢本指南，请考虑给它一个 star ⭐ 并关注它以获取新更新！

# ⚖️ 许可证

MIT
