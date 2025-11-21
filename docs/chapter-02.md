---
layout: default
title: Vibe Coding - AI 作为驾驶员
nav_order: 3
---
## 开始

如果您不会编程，但想尝试一下，我们建议从一些Web工具开始，如 Bolt、Replit、v0 或 Lovable。

如果您已经会编程，最推荐的是 Cursor 或 Windsurf。您可以从免费计划开始，然后升级到每月 20 美元的计划。如果您将使用大量的token用于最新的LLM，那么 Cursor 相当不错且便宜。VSCode 最近也推出了自己的代理模式。它与 Github Copilot 配合使用，重点是学生有教育免费。其他编辑器也在迅速添加代理功能，我们将在最后总结它们。

如果您已经会编程并且是一个终端狂人，请尝试CLI工具，例如aider、Claude Code 、 OpenAI Codex 或 Gemini CLI。对于这些工具，您需要为 Anthropic Claude、OpenAI GPT 或 OpenRouter 设置 API 密钥。

如果您已经会编程，喜欢终端和 VSCode 的风格，并且真的想体验让子代理并行运行的强大功能，并且不关心成本，只关心完成任务，请尝试 Amp。

如果您想要一个更开源的替代方案，请尝试 OpenHands。

{: .note }
>🌕建议-1
>我们强烈建议您在类似 OpenRouter、硅基流动、ChatAnyWhere 等LLM集成调用网站中创建一个账户。这非常简单，您将获得最新 LLM 模型的访问权限，甚至是它们的免费版本。
>注：硅基流动和ChatAnyWhere对国内友好，但是前者只能访问国内LLM。
>🌕建议-2
>我们建议你先从Cursor开始，因为它不仅强大、操作友好，更重要的是，提供了便宜的套餐来使用类似Claude-4.5、GPT-5系列等昂贵的模型

---
📚 Resources —— 推荐的 AI Code 工具
- <https://bolt.new/>
- <https://replit.com/>
- <https://v0.app/>
- <https://cursor.com/cn>
- <https://windsurf.com/>
- <https://docs.all-hands.dev/>
- <https://arxiv.org/pdf/2407.16741?>
- <https://aider.chat/>
- <https://code.claude.com/docs/zh-CN/overview>
- <https://openai.com/index/openai-codex/>
- <https://github.com/google-gemini/gemini-cli>
---

## 如何为 Vibe Coding 提供 prompt？

在您安装并使用这些工具一段时间后，您会注意到它们会出现幻觉、陷入无限循环尝试修复可能存在的错误等。重要的是要知道如何写好提示。以下是一些提示：

- **不要在一个提示中问所有问题。** 仅仅提示“嘿，给我为我的宠物店建一个应用程序”对软件工程师和 AI 都没有多大帮助 →了解您的项目，先与 LLM 进行头脑风暴，创建一个 PRD（Production Requirement Document, 产品需求文档），制定计划并将其分解为任务。
事实证明，如果您让您心爱的 LLM 自由发挥，没有太多上下文，它会很快产生相当狂野的幻觉。您需要驯服这头野兽，而 PRD 是一个很好的方法。
下面即将提供一个如何使用 ChatGPT 为您创建一个 PRD 的方法。
- **提供详细信息。** 如果您知道自己想要什么，就说出来。如果您知道自己想要哪种编程语言、哪种技术栈、哪种受众类型，请将其添加到您的提示中。正如这篇长达60页的关于程序修复的综述论文 (Yang et al. <https://dl.acm.org/doi/pdf/10.1145/3764584>) 里提到的，你提供什么样的信息将直接决定着你获得的效果以及成本。
- **Markdown 对于 LLM 来说很友好。**为了强调提示的特定部分，建议使用一些符号，如 ##，**。
- **将您的项目分解为任务和子任务。**
- **针对不同的目标尝试不同的模型。**
- **尝试不同的模型来确认和验证其他模型的输出。**

👉**[示例]**  一种通常效果良好的方法/程序/策略/工作流程

使用 ChatGPT 4.5、4o 或 o3 并使用以下提示：

```
你是一位资深软件工程师。我们将一起构建一个项目的 PRD。

重要：
- 一次只提一个问题
- 每个问题都应基于之前的答案
- 深入探讨每个重要的所需细节

想法：
<在这里输出你的想法>
```

您将进入一个问答循环几分钟。尽量详细地回答您能回答的所有问题。完成后（或当您觉得足够时），发送此提示以引导模型将其编辑为 PRD：

```
将这些发现编辑成一个 PRD。使用 Markdown 格式。它应该包含以下部分：

- 项目概述
- 核心需求
- 核心功能
- 核心组件
- 应用程序/用户流程
- 技术栈
- 实施计划
```

将此文件复制并保存到您的项目文件夹中的 `docs/specs.md`。

现在让我们为您的项目创建任务列表。询问以下问题：

```
根据生成的 PRD，创建一个详细的分步计划来构建此项目。
然后将其分解为相互依赖的小任务。
根据这些任务，将其分解为更小的子任务。
确保步骤足够小，以便一步实现，但又足够大，以便成功完成项目。
使用软件开发和项目管理的最佳实践，避免大的复杂性跳跃。
将任务相互关联，创建依赖列表。不应有孤立任务。

重要：
- 使用 markdown
- 每个任务和子任务都应该是一个清单项
- 为每个任务提供足够的上下文，以便开发人员能够实现它
- 每个任务都应有一个数字 ID
- 每个任务应列出依赖任务 ID
```

将其保存为您的项目文件夹中的 `docs/todo.md`。

这是一个使用 ChatGPT 4o 为一个简单的 CLI/IDE 工具进行的头脑风暴/规划会话的示例，可以作为您的灵感。

有了以上这些，您就可以打开 Cursor（或其他 AI 代码编辑器），将其指向这些文件并询问：

```
你是一位资深软件工程师。研究 @docs/specs.md 并实现 @docs/todo.md 中
仍缺少的部分。每次实现一个任务，并尊重任务和子任务的依赖关系。
完成一个任务后，在列表中勾选它，然后进行下一个。
```

当 Cursor Agent 第一次执行命令时启用 YOLO 模式，然后继续在提示中接受或请求继续。

在使用 Cursor 的情况下，有时 LLM 会达到某些限制并要求重试。只需重试并继续即可。是的，您正在vibe coding！

> 🌕建议-3
>
>尽管vibe coding非常酷，但了解您在做什么也同样有趣 → 审查代理生成的代码会在出现错误时（它们一定会发生！）对您有很大帮助，并提高您代码审查的技能。
>Note：*如果您关心AICoding，相信您一定看过类似的话：未来的程序员将更少关心编程实现，取而代之的，他们将成为一个设计师（关心软件架构和顶层设计）和代码审查员（审查代码以解决AI出现的错误）。这非常正确！*
>注：硅基流动和ChatAnyWhere对国内友好，但是前者只能访问国内LLM。


## 我应该使用哪种模型？

LLM 经过不同的目标训练和微调将适应不同的任务，这里列出了您可能拥有的目标/用途以及应该使用哪种模型：

| **目标** | **模型（国外）** | 模型（国内） |
| --- | --- | --- |
| 头脑风暴 | GPT 5, Gemini 3.0, o3, Grok4 | GLM-4.5, DeepSeek-R1, KiMi-K2 |
| 编程 | Claude Sonnet 4.5, Gemini 3.0 Pro, Grok4, GPT 5, o3| Qwen3-Coder, Qwen 系列, DeepSeek-V3, KiMi-K2 |

鉴于 LLM 每天都在变化，此表格很快就会过时。请查看以下排行榜以获得更准确的比较：

---

📚 Resources —— LLM可信排行榜

- 通用排行榜
    - <https://lmarena.ai/leaderboard>
    - <https://models.dev/>
    - <https://openrouter.ai/models?categories=programming&fmt=table>
    - [Agent Leaderboard - a Hugging Face Space by galileo-ai](https://huggingface.co/spaces/galileo-ai/agent-leaderboard)
- 代码任务排行榜
- <https://www.swebench.com/>
- <https://swe-bench-live.github.io/>
- <https://aider.chat/docs/leaderboards/>
---

## 为你的项目设置规则

您可以通过将规则或约定“注入”LLM 的上下文来定义将应用于您项目的规则或约定。每个编辑器都有一些方法可以做到这一点：

- 在 Cursor 中，只需在 `.cursor/rules/` 文件夹中创建 Markdown 文件 或者 在Cursor Setting 的 Rules中编辑即可。Cursor 将确保将这些规则应用于与 LLM 的所有通信。
- 在 Aider 中，创建包含您要使用的规则/约定（如 `rules.md`）的 Markdown 文件，然后将以下内容添加到您的 `.aider.conf.yml` 文件中：`read: rules.md`。

此外，许多工具支持在您的主目录中配置一个规则/约定文件，以应用于您的所有项目。例如，在 Aider 中，您可以在名为 `~/.global_conventions.md` 的文件中添加全局约定，然后将其添加到 `.aider.conf.yml` 中，使用 `read: [~/.global_conventions.md, rules.md]`。

您可以将 PRD 的一部分作为规则添加，例如技术栈或一些代码格式和样式指南。

以下是一些规则指南，希望能给您带来启发：

👉**[示例]**  规则分类

1. 代码风格
    - 缩进方式（如 2 空格 / 4 空格 / Tab）
    - 命名约定（变量、函数、类、文件名）
    - 注释风格（是否要求 Javadoc / docstring / 注释语言统一为英文）
    - 空行与空格使用规则（操作符两侧是否空格、函数之间空行数）
2. 架构与技术栈约定
    - 指定技术框架（如 Spring Boot、React、Next.js）
    - 数据库与 ORM（MySQL + JPA / PostgreSQL + Prisma）
    - API 风格（REST / GraphQL / gRPC）
    - 日志规范（统一使用 slf4j / logback，日志分级策略）
    - 错误处理（统一异常封装类、返回码规范）
3. 代码安全与质量要求
    - 禁止硬编码（如 API key、密码）
    - 输入校验必须存在
    - 异常必须捕获或显式抛出，不允许吞异常
    - 必须添加单元测试 / 覆盖率要求（如 ≥ 80%）
    - 依赖安全检查（不使用过时库 / 存在 CVE 的库）
4. 文档与注释
    - 必须为公共 API、类、模块写文档注释
    - README 格式（项目介绍、安装步骤、运行方法、示例）
    - 代码中复杂逻辑必须有解释注释
    - 提交时要求附带变更说明
5. Git 工作流与提交规范
    - Git 分支策略（main/dev/feature/bugfix 命名规范）
    - Commit message 规范（如 Conventional Commits：`feat: xxx`, `fix: yyy`）
    - PR / MR 模板（必须写清楚修改内容、影响范围、测试方法）
6. 测试与 CI/CD 约定
    - 单元测试框架（JUnit、pytest、Jest）
    - Mock 策略（如统一用 Mockito）
    - 覆盖率检查规则
    - CI 工具（GitHub Actions / GitLab CI / Jenkins）
    - 自动化 lint & format 检查
7. 项目专属规则
    - 与 PRD 相关的专属约定（如“前端必须用 Tailwind CSS”，“接口响应时间需 <200ms”）
    - 特殊的业务逻辑约束（如“所有金额字段必须用 BigDecimal，而非 float/double”）
    - 团队内部习惯（如“类名前缀必须加 `App`”，“所有 API 接口返回统一的 JSON 包装格式”）

## 保留提示日志

记录您发送的每个提示，并（这一点很重要）附上您对思考过程的评论以及您遇到的任何意外情况。这个提示日志是您的设计意图记录；对于任何没有参与项目的人，包括您在六个月后忘记了自己当时在想什么，都将非常宝贵。

目前还没有关于此文件名称的约定，您可以使用 `history.md` 等名称，并在交互中及时更新这个文档。有了这个文件，您就可以在其中添加自己的想法。当您将来回顾项目时，您（和他人）可以学到很多东西，而且您可能会开始注意到一些模式和技巧，可以在下次会话中使用。

## 结构化设计与提示

LLM 在生成可用代码方面已经相当成熟，但在结构良好——即具有适当分层、关注点和职责分离的代码方面仍然不足。良好的结构直接关系到 **可读性、可维护性和缺陷率。**
> 🌕建议-4
>- 按层次逐步提示：在数据库驱动应用中，先定义数据模型 → 再构建数据访问层 → 最后编写业务逻辑。
>- 保持分层清晰：在项目规则中明确要求 LLM 不要打破分层。如果需要新方法，必须放入对应封装层，而不是直接侵入业务逻辑。
>- 核心优先：花时间确保主要功能得到实现并按照您想要的方式组织。您甚至可以编写类和函数骨架，然后让 LLM 填补空白。只有在您拥有良好的基础和良好的测试之后，您才能转向此核心库的消费者，例如将其作为 CLI 或 REST API 公开给未来的 Web 应用程序。

## 如何创建我自己的 AI Code Agent？

我们正在制作一些关于如何通过构建我们自己的工具来创建 AI 编程智能体的教程，所以请持续关注。
从一些既有的开源Agent及其论文里面学习是最好的方式，例如OpenHands、SWE-Agent…

[如果您有相关的启发或者讨论，可以随时联系我们：602025320022@smail.nju.edu.cn](mailto:如果您有相关的启发或者讨论，可以随时联系我们：602025320022@smail.nju.edu.cn)