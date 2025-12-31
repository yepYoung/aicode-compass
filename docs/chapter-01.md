---
layout: default
title: AI Coding
nav_order: 2
---

## 从 AI coding 到 Vibe coding 
这些术语非常相似，本质上也并没有太大区别。

AI 编程 (AI Coding) 是指使用 AI 模型及其所有相关工具来帮助您编写软件。在学术界，他们通常被划分为不同的子任务，例如 AI 代码生成 (或简称为代码生成，以下同样省略 AI)，代码摘要，自动修复，自动测试。

这是一个迷人的研究领域，它在学术界正在被如火如荼地研究。

---
📚 Resources —— 学术界的热点关注

- <https://www.swebench.com/> —— SWE-bench Team (Princeton University, University of Chicago, Stanford University)
- <https://www.tbench.ai/> —— Terminal-Bench Team (Laude, Microsoft, Anthropic)
- ...

---

但是，本文章主要关注实践中的 AI 编程：如果您正在使用 Cursor 并通过不断地“tab-tab-tab”来获取补全，您就是在AI 编程；如果您完全使用 Cursor 的代理模式，您也是在 AI 编程。总而言之：它是任何利用 AI 模型帮助您生成代码的方式。

Vibe coding是 AI 编程的升级版 → 在这里，您不太关心生成的代码，您只需提供一个提示，并期望 AI 为您编写所有代码。这个术语由卡帕西 (Karpathy) 在 2025 年创造，并且越来越受欢迎。

恕我直言，vibe coding正在帮助那些从未考虑过编程的人普及编程！总而言之，无论您是使用 AI 来讨论您的软件想法，还是仅仅帮助修改您现有代码库的一部分，或者您是完全采用vibe coding，您都在使用 AI 来帮助您生成代码。我们称之为 AI coding。

相信您在各个网站或论坛（例如Github、小红书、X等）都或多或少看到过介绍 AI 编程使用的建议，但总而言之，它们都可以被归结为两个 high-level 的方式：

- **AI 是您的驾驶员：**顾名思义，在这种情况下由AI主导你的开发。这里是 Vide coding 发生的地方。您打开 Cursor 的 Agent 模式，并接受代理所做的一切来生成您的代码。这是一种非常强大的自我自动化方式，但它要求在如何设计系统、驯服代理以及跳入您实际上不了解的意大利面条式代码（特别是为了解决错误）方面，需要一些良好的实践。
- **AI 是副驾驶：** 您使用 AI 模型来增强自己，提高您的生产力。无论是启动 ChatGPT 来帮助您为您的 SaaS 进行头脑风暴，还是使用 Cursor 帮您构建你代码库的整体架构。这有很多好处，特别是对于创意探索和自动化您工作中无聊的部分。

*值得注意的是*，随着项目复杂性的增加，我们大多都会回归副驾驶模式，并远离纯粹的 Yolo Vibe coding。如果未来有另一个人（或者三个月后的你自己）需要维护代码的可能性越大，这一点就越重要。