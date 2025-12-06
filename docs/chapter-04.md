---
layout: default
title: AI Coding开发实践
nav_order: 5
---
## 前端/Web应用开发

现代 Web 开发的生态系统庞杂且快速演化，往往令人望而生畏。无论是 JavaScript/TypeScript 框架，还是 CSS/UI 框架，都让人很难决定从哪里开始、又该选择哪一个。经过几周的前端开发实践，我最终总结出以下几种值得尝试的方案：

- Next.js：如果你希望与 Vercel 的生态系统紧密结合，Next.js 是一个极佳的选择。它提供了良好的开发体验和丰富的功能集。但要注意，随着项目规模增长，Vercel 的费用可能会很快变得昂贵。
- Vanilla React + React Router：如果你希望拥有更强的部署灵活性，可以选择最基础的 React，并结合 React Router 实现路由功能。这样你几乎可以将应用部署到任意平台，而不依赖特定的生态系统。
- Remix：Remix 在路由处理方面具有出色的特性，同时也能像 React Router 一样自由部署。它非常适合需要良好 SEO、服务端渲染和渐进增强的项目。
- FastHTML：如果你更倾向于 Python 生态，并且关注的是暴露后端核心功能（如数据分析或 AI/ML 管道），而非复杂的 UI，那么 FastHTML 是一个轻量化但实用的选择。

在实际案例中，像 Lovable 这样的基于 Web 的 AI 编程平台选择了 React，而 v0 则构建在 Next.js 之上。
一个实用的小技巧是：你可以先在 Lovable 上启动项目（它的免费计划每天提供最多 5 条消息），并将输出直接同步到 GitHub 仓库。随后，你只需在本地机器上克隆该仓库，就能切换到 Cursor 等编辑器继续 AI 编程，然后再将成品部署到 Render、Fly.io、Cloudflare 等任意平台。这种工作流没有任何绑定或限制，尤其适合在后端包含复杂逻辑时使用。

如果你同时在开发前端和后端，建议：

- 将后端和前端分别放置在 Git 仓库的独立子目录；
- 或者为后端和前端建立单独的仓库，然后将它们一起导入到 Cursor 的同一工作区。
    
    这样，你在前端代理中就能轻松引用后端代码，反之亦然，避免了跨目录引用的麻烦。
    

另外，前期不要过早集成前端和后端。更好的做法是指示 AI 代理在开发前端时使用 模拟数据（mock data） 或 虚拟 API，等后端功能完善后再替换为真实数据源。

一个进阶的技巧是：借助优秀的 MCP 工具，将编程代理集成到 Playwright 或 browser-use 中。这样，AI 代理可以自动控制浏览器、捕捉错误和截图，而无需你手动复制粘贴浏览器报错信息回到 AI 循环中，极大地减少调试的摩擦。

如果你希望在 Web 应用中加入 3D 内容，且使用的是 React，那么建议使用 React Three Fiber (R3F)，而不是直接使用 three.js。R3F 将 three.js 对象封装为 React 组件，使得状态管理与 React 的数据流保持一致，更容易构建复杂的 3D 交互。

### 仅仅想让界面变好看？

如果您既不是一个专业的UI设计师，又不是一个专业的前端开发程序员，那么想一下子设计一个界面好看的前端展示，似乎不是一个很简单的事情。甚至可以说很难，想象一下，入门一些乱糟糟的前端开发的语言或框架就足够占用你大部分精力了。

幸运的是，这里有一些方法，让您可以既不懂设计又不懂开发，依然可以帮你开发出足够美观优雅的界面。下面我将用一个简单的示例来说明。

👉 **[示例]**  一种通常效果良好的方法/策略/工作流程

首先，寻找主题相关的 UI 网站。

注意，我们要找的可不是那种”艺术展”风格的设计网站，也不是随便一个「画廊」，你需要的是 —— **UI 组件网站（UI Component Library Sites）**。这些网站不仅展示了各种组件样式（Components Style），还会直接提供**可复制的代码示例**。对 LLM 来说，这一点超级关键。例如：

![UI组件网站示例]({{ "/img/UI-example.png" | relative_url }})

之后，直接将下面的Prompts放入Agent中就好。

```
你不仅是一个资深的软件工程师，还是一个UI设计师。
请修改本项目的UI界面为[新粗野主义(Neo-Brutalism)]，完全参考https://www.neobrutalism.dev，遵循其设计原则、视觉风格和交互模式。
```

下面是一些常用的UI组件风格和网站的信息：
| **风格** | **核心理念** | **提示关键词** | **网站** |
| --- | --- | --- | --- |
| 扁平化设计 (Flat Design) | 极致简约，去除所有装饰性元素（阴影、渐变、纹理） | Flat design, no shadows, no gradients, solid colors, simple icons, clean typography, minimalist. | 
[Button | Semantic UI](https://semantic-ui.com/elements/button.html) |
| 材料设计 (Material Design） | 模仿物理世界的纸张和墨水，有逻辑的层级和深度 | Material design, subtle shadows, logical layers, floating action button, Roboto font, bold color palettes. | 
[Material UI](https://mui.com/material-ui/)
[MDUI](https://www.mdui.org/en/)
[Angular Material](https://material.angular.dev/) |
| 极简主义 (Minimalism) | “少即是多”，只保留最核心的功能和元素 | Minimalist, monochromatic or limited color palette, heavy use of whitespace, uncluttered, typography-focused. | 
[Geist UI](https://geist-ui.dev/en-us) 
[Preline UI](https://www.preline.co/) |
| 玻璃拟态 (Glassmorphism) | 模仿磨砂玻璃的效果，创造出半透明的层次感 | Glassmorphism, frosted glass effect, blurry background, semi-transparent, subtle border, vibrant background colors. | 
[Liquid Glass UI](https://liquidglass.liqueai.com/)
[Glasscn UI](https://allshadcn.com/components/glasscn-ui) |
| 极光 UI (Aurora UI) | 模仿北极光的模糊、多彩的背景光效 | Aurora UI, colorful mesh gradients, blurry color blobs, soft, ethereal, often used in dark mode. | 
[Aurora UI](https://auroraui.netlify.app)
[Aceternity UI](https://ui.aceternity.com/components/aurora-background) |
| 孟菲斯设计 (Memphis Design) | 80年代风格，大胆、古怪、好玩，打破常规 | Memphis design style, geometric shapes, clashing colors, playful patterns, squiggles and dots, asymmetrical. | 
[Memphi UI](https://www.memphi.dev/docs)
[Memphis Design](https://dribbble.com/tags/memphis-design)
[Pinterest-Memphis UI](https://www.pinterest.com/faz654/memphis-ui) |
| 瑞士风格 / 国际主义 (Swiss Design) | 极其注重网格、结构和清晰的排版，功能性强 | Swiss style, grid-based layout, sans-serif typography (like Helvetica), asymmetrical balance, objective, clean. | 
[Swiss Post Design System](https://styles.design-system.post.ch)
[Swiss Post Web Components](https://www.npmjs.com/package/@swisspost/design-system-components) |
| 新拟物化 (Neumorphism) | 淡阴影 + 浮雕效果 + 柔和色彩 | Neumorphism, soft shadows, concave/convex shapes, light source simulation, subtle gradients. | 
[Neumorphism](https://neumorphism.io/#e0e0e0) |
| 新粗野主义(Neo-Brutalism) | 高对比度 + 粗黑边框 + 鲜艳纯色，刻意营造“未加工”的原始感，反主流精致，强调大胆排版 | Neo-brutalism, thick black outlines, high contrast, raw aesthetic, bold typography, flat colors, unpolished, retro computer interface. | [https://www.neobrutalism.dev](https://www.neobrutalism.dev/) |

> 🌕 建议-5
>
>很多人第一次用 Vibe Coding 生成或修改 UI 时，都会踩这个坑。以为只要截一张图，用红框圈一圈或者做一个GIF，让 LLM 看懂交互就能让 AI “明白你想要的样子”，其实不然。AI不可能一次就写出完美 UI，而你提供的信息质量，决定了它能走多远。图片可以“展示”，但文字才能“解释”。即使你有再清晰的截图，也请继续用语言描述。包括布局逻辑、交互节奏、风格偏好、视觉层次……



## 后端开发

与前端不同，后端开发在 Lovable 等基于 Web 的工具中并不理想。因此你可能需要转向更专业的工具，比如 Cursor、Windsurf、aider 等本地开发环境。

推荐的后端技术栈：

- Python + FastAPI：轻量化、文档生成优雅、性能良好，非常适合快速构建 RESTful API 或 AI 服务接口。
- Node.js + Express / NestJS：如果你更希望与前端保持统一语言（JavaScript/TypeScript），那么 Express 或更结构化的 NestJS 是不错的选择。

后端开发的一个关键是 端到端测试（E2E）。你可以引导 AI 在为每个新功能或子任务编写实现的同时，自动生成对应的测试并运行它们，从而保证稳定性。

在完成后端开发后，可以将后端的 API 文档（特别是 HTTP 端点说明） 提供给前端代理。这样，前端就可以从使用虚拟数据逐渐切换到真实的后端接口，保证迭代的平滑过渡。

## 游戏

对于小型游戏项目，可以采取极简主义的方式：

- 使用一个独立的 `.js` 文件完成全部逻辑。
- 如果是 3D 游戏，选用 three.js；如果是 2D 游戏，则推荐 pixi.js。

在游戏开发中，优质的素材（assets） 往往比引擎本身更重要。因此你可以使用 Tripo AI、Anything World 等服务生成 3D 资产，并自动完成绑定与动画，大幅提升开发效率。