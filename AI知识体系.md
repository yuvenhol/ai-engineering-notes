## Software in the Era of AI

### 发展历程 by [Andrej Karpathy](https://karpathy.ai/)

随着人工智能技术特别是大型语言模型（Large Language Models, LLMs）的成熟，软件开发范式正在经历重大变革。从最初的手写代码到神经网络权重驱动，再到自然语言提示控制输出，软件的“构建逻辑”与“控制接口”都在被重新定义。

### Software 1.0 — 代码驱动时代

**定义**
Software 1.0 指的是传统的软件开发模式：开发者使用编程语言（如 C/C++、Python、Java）编写明确规则和逻辑，让计算机按步骤执行。这一阶段的软件行为完全由人类编写的代码决定。

**典型特征**
- 以开发者为中心，需要精通语言语法与逻辑设计；
- 程序行为可预测、可解释；
- 软件功能由代码逐行定义。

![image.png](https://yuvenhol-1255563050.cos.ap-beijing.myqcloud.com/img/202512171033265.png)

### Software 2.0 — 权重驱动时代

**定义**  
Software 2.0 将软件核心从代码逻辑转向经过训练的神经网络权重。开发者不再直接写出所有逻辑，而是设计训练数据、模型架构和训练流程，让模型从数据中学习解决问题的方式。

**典型特征**
- 模型权重隐式表达行为逻辑；
- 依赖大量数据和迭代优化；
- 提升了模型的泛化能力与任务自动处理能力。

Software 2.0 是深度学习技术兴起的产物，广泛应用于图像识别、语音识别、自然语言处理等领域。

![image.png](https://yuvenhol-1255563050.cos.ap-beijing.myqcloud.com/img/202512171033231.png)


### Software 3.0 — 提示词驱动时代

**定义**  
Software 3.0 指的是以大型语言模型为核心的软件构建方式，其控制接口不再是传统代码或训练权重，而是自然语言提示词（prompts）。开发者通过设计提示文本和上下文示例，引导 LLM 生成期望的行为与输出。

**核心特点**
- 提示词（prompt）成为程序的核心接口；
- 编程语言从特定语言转向自然语言；
- 软件逻辑更侧重于“意图表达”而非“实现细节”。

在这一阶段，提示词设计与上下文管理成为新的工程技能，系统行为由模型和提示共同驱动。


### 三阶段比较总结

![image.png](https://yuvenhol-1255563050.cos.ap-beijing.myqcloud.com/img/202512171039876.png)

| 维度     | Software 1.0 | Software 2.0 | Software 3.0         |
| ------ | ------------ | ------------ | -------------------- |
| 核心逻辑表达 | 手写代码         | 模型权重         | 自然语言提示               |
| 主体控制接口 | 程序语言         | 训练与推理        | Prompt 与上下文          |
| 开发者角色  | 工程师          | 数据与训练专家      | Prompt 设计师 / LLM 协作者 |
| 泛化能力   | 受限           | 中等至强         | 高（依赖上下文与提示设计）        |
| 可解释性   | 高            | 中等           | 较低                   |


## 案例：以“情绪分类”为例

为了更直观地理解三个阶段的区别，我们以一个“文本情绪分类”的任务为例。

### Software 1.0

使用规则或关键词来判断情绪：

```
if contains("happy") then sentiment = positive

```

这种方法简单直接，但难以捕捉语言中的复杂语义和上下文关系。

### Software 2.0

通过标注语料训练神经网络模型，让模型学习不同情绪类别的分布模式。例如训练一个深度学习文本分类模型。

这种方法依赖大量数据与训练流程，能够获得更高准确率，但需要专业训练与调参。

### Software 3.0

直接用提示词让大型语言模型执行分类：

```
请判断下列句子的情绪是正面、负面还是中性：
句子: “这部电影让我感到失望。”
```

模型根据提示理解任务并输出分类结果，不需训练新的模型。

这种方式降低了开发门槛，更强调提示设计和上下文质量。

![image.png](https://yuvenhol-1255563050.cos.ap-beijing.myqcloud.com/img/202512171036145.png)

### 新时代的软件重写浪潮

随着 Software 3.0 概念的普及，大量遗留系统将因为无法充分利用智能化能力而需要重构或替换。传统的软件功能将逐步被提示驱动的系统替代，因为提示驱动方式在很多任务中能够以更少的工程投入实现更高的通用性与可扩展性。

![image.png](https://yuvenhol-1255563050.cos.ap-beijing.myqcloud.com/img/202512171044642.png)

## LLMs as an OS

在 Software 3.0 的语境中，大型语言模型以及相关配套技术（LLMs）不仅仅是一个调用接口，而是逐步演化为新的软件运行平台，其角色类似**操作系统（Operating System）**。这一类比指向一个新的理解维度：LLM 是CPU，上下文窗口类似 RAM，而工具与插件则类似于传统系统中的应用程序。

![image.png](https://yuvenhol-1255563050.cos.ap-beijing.myqcloud.com/img/202512170030250.png)

就像在冯诺伊曼架构下，CPU只能和 RAM交互一样。在LLMs中LLM也是只能直接和prompt交互。而如何写好prompt以及写好prompt 所需的依赖前置工作，将会LLM新时代的开发者的主要工作。

## prompt Engineering
它是一种通过试验和错误来发现、提炼最佳短语、格式和语序的艺术，旨在诱导出模型最具表现力的响应 。

高质量的提示词并非随机组合，而是遵循特定的逻辑结构。
### 几种框架：

#### CO-STAR 
框架被认为是目前功能最全的系统化方案之一，通过六个维度的联结确保输出的精准度 。

| **组件**           | **核心职能**                  | **业务影响**          |
| ---------------- | ------------------------- | ----------------- |
| **C (Context)**  | 背景设定，提供任务相关的事实与环境         | 减少无关输出，提升决策相关性    |
| **O(Objective)** | 目标清晰化，定义任务的最终产出物          | 防止任务漂移，确保执行的一致性   |
| **S (Style)**    | 风格规定，模拟特定的文体或品牌声调         | 增强品牌认同感，减少后期修改    |
| **T (Tone)**     | 语气设定，控制沟通的情感质量            | 优化客户服务体验，适配不同情绪场景 |
| **A (Audience)** | 受众识别，根据读者背景调整复杂程度         | 确保信息传达的有效性        |
| **R (Response)** | 格式定义，指定输出的物理结构（如CSV/JSON） | 便于下游系统直接集成        |
#### ICOC

- **I - 指令 (Instruction)：** 这是提示词的中枢，明确告知模型需要执行的具体任务。例如“总结以下文章”、“将文本分类”或“将这段代码翻译成 Python”。
    
- **C - 背景 (Context)：** 为模型提供外部知识、历史对话或行业背景，帮助模型在特定的语境下生成更具相关性的回答。例如，在金融分析中提供“当前的经济周期”作为背景，能让模型的回答更专业 。
    
- **I - 输入数据 (Input Data)：** 提示词中需要模型进行处理的原始信息或具体问题。例如，一段待总结的文本或一个待解答的数学题。
    
- **O - 输出指示器 (Output Indicator)：** 规定模型输出的格式、风格或类型。例如，要求模型输出为“JSON 格式”、“Markdown 表格”或在结果前增加特定的前缀词（如“Sentiment:”）。
#### CARE
CARE 框架（Context, Action, Result, Example）强调了“示例”在提示工程中的战略地位 。通过提供一个成功的案例研究，CARE 能够激发模型的类比推理能力，这在战略分析和教育内容生成中尤为有效 。

#### RTF 
RTF 框架（Role, Task, Format）则通过极致的简化，为快速原型设计和简单自动化任务提供了极佳的响应速度 。角色（Role）的设定不仅是为了赋予AI某种语气，更重要的是通过激活神经网络中特定的权重路径，使其能够访问该领域内更专业的术语和逻辑模式 。

### 实用技巧

#### 合理使用消息角色（Message Roles）
| **职能**   | **OpenAI**             | **Anthropic** | **Google Gemini**    | **核心用途**          |
| -------- | ---------------------- | ------------- | -------------------- | ----------------- |
| **全局规则** | `system` / `developer` | `system` 参数   | `system_instruction` | 设定人格与防御注入         |
| **用户请求** | `user`                 | `user`        | `user`               | 交互起点与数据输入         |
| **模型响应** | `assistant`            | `assistant`   | `model`              | 存储历史与 Few-shot 示例 |
| **外部反馈** | `tool`                 | `tool_result` | `function_response`  | 接入实时数据或计算结果       |

通过将全局规则放在 `System` 或 `Developer` 角色，将用户请求放在 `User` 角色，可以建立一种**权限等级**：

- **防御注入：** 模型被训练为优先服从 `Developer/System` 指令。如果攻击者在 `User` 角色中输入“忽略之前的所有指令”，模型会因为该指令来源于低优先级的用户层而予以拒绝。
    
- **逻辑分离：** 这种做法类似于编程中的“函数定义”与“参数输入” 。`System` 定义函数逻辑（如何处理），`User` 提供具体参数（处理什么），极大提升了复杂任务的稳定性 。

- **Persona 稳定性：** 模型对不同角色位置的信息敏感度不同,在 `System` 消息中设定角色（如“你是一名资深医学研究员”）比在对话正文中描述角色更持久，不容易在多轮对话中因为上下文过长而“破功”。
    
- **防止降级：** 在处理极长文本时，通过在对话间隙定期插入 `Developer` 消息来强化约束（Reinforcement），是防止模型逻辑在长程推理中产生偏移的有效技巧。

对于涉及工具调用（Tool Use）的复杂场景，消息角色是不可或缺的组件：

- **Tool/Function 角色：** 专门用于传递 API 调用的结果。这种角色化的处理让模型能够明确区分哪些是“它的思考”，哪些是“外部世界的真实反馈”，从而实现闭环的自主推理（ReAct）。
#### 使用分隔符（Delimiters）优化结构

分隔符能帮助模型明确区分“指令”、“背景资料”和“用户输入”，从而减少语义混淆。

- **XML 标签：** 对于 Claude 和 Gemini 等模型，使用如 `<context>`、`<instructions>`、`<example>` 等标签具有极佳的效果。XML 的闭合结构（如 `<task>内容</task>`）比 Markdown 更有助于模型准确解析复杂提示词，减少错误率。此外通过将不可信的用户输入包裹在特定标签（如 `<user_input>`）中，可以向模型发出信号：该部分内容应视为待处理数据，而非覆盖系统设置的新指令。
    
- **视觉分隔符：** 使用 `###`、`"""` 或 `---` 来划分不同部分。研究表明，这种视觉分隔能使模型的理解能力提升约 31%。

通常来说，实用 XML与markdown结合方式较好。

#### 精准的角色扮演（Role Prompting）

角色设定不仅是赋予 AI 一个“名字”，更重要的是锚定其知识领域和语气。

- **添加“志向性”描述：** 仅仅说“你是一位作家”是不够的，更好的做法是“你是一位资深作家，擅长简洁、无废话且不使用行业术语的文风” 。
- **限制知识域：** 将模型锚定为特定角色（如“肿瘤学医学研究员”），可以减少其生成无关信息的倾向，使其输出更符合特定领域的逻辑。
- **优先位置：** 角色定义应放置在“system message”中或提示词的最前端，以便模型在处理后续指令前先建立行为准则 。

#### 从零样本（Zero-Shot）转向少样本（Few-Shot）

提供示例（Demonstrations）是确保格式一致性和逻辑准确性的最有效手段。

- **3-5 个示例：** 给模型提供 3 到 5 个“输入-输出”对作为示范，其成功率通常比纯指令高出 58%。
- **展示正向模式：** 比起告诉模型“不要做什么”，展示“做正确的样子”对模型更有引导价值。
#### 逻辑推理与思维引导

- **思维链（CoT）：** 在处理复杂逻辑或数学问题时，加入“请逐步思考”或“详细说明你的推理步骤”等触发词。这不仅能减少逻辑断层，还能方便人类审计其推导路径 3。
- **思维验证（Chain-of-Verification）：** 要求模型在给出答案后，先生成几个验证问题，自行核实答案的准确性，这在减少事实性幻觉方面非常有效。
- **递归自我改进（Recursive Self-Improvement）：** 让模型先生成初稿，然后要求它“批评自己的输出并列出 3 个弱点”，最后再根据这些弱点生成终稿。

#### 指令与约束的精细化
 
- **处理长文本时的“末尾指令”：** 对于支持长上下文的模型（如 Gemini 2.0 或 Claude 3.5），建议先提供大量背景资料，而将具体的查询或指令放在提示词的最末尾，以增强模型对指令的注意力。
    
- **否定约束：** 明确告诉模型严禁执行的操作，例如“如果无法从提供的资料中找到答案，请直接回答‘不知道’，严禁基于外部知识库虚构”。

### 补充
openAI介绍 https://platform.openai.com/docs/guides/prompt-engineering?api-mode=chat
## Context Engineering

### 定义

**上下文工程**是指以 **_正确的格式_** 提供 **_正确的信息和工具_** ，使 LLM 能够完成任务。

**_感性版本定义_**

> 上下文工程是将上下文窗口填充恰当信息以供LLM下一步使用的精妙艺术。

### Prompt Engineering VS Context Engineering

通常来说 提示词工程 被认为是 上下文工程的一部分。
![image.png](https://yuvenhol-1255563050.cos.ap-beijing.myqcloud.com/img/202512171634828.png)

| **维度**   | **提示工程 (Prompt Engineering)** | **上下文工程 (Context Engineering)** |
| -------- | ----------------------------- | ------------------------------- |
| **核心目标** | 优化**指令**（怎么问最有效）。             | 优化**环境**（AI 应该知道哪些背景）。          |
| **关注点**  | 措辞、格式、角色设定、思维链。               | 数据检索 (RAG)、长期记忆、动态信息注入。         |
| **技术手段** | 写出更好的文字、设置 Delimiters。        | 向量数据库、API 调用、窗口管理、数据清洗。         |
| **生命周期** | 通常是单次或短期的对话。                  | 支撑整个系统的长期稳定运行。                  |
| **比喻**   | 厨师的**烹饪手法**。                  | 厨房里**备好的食材**。                   |

### LLM 应用程序中常用的上下文类型

在构建 LLM 应用程序时，我们需要管理哪些类型的上下文？上下文工程作为一个[概括性概念](https://x.com/dexhorthy/status/1933283008863482067?ref=blog.langchain.com)，适用于以下几种不同的上下文类型：

- **指令** – 提示词、记忆、少样本示例、工具描述等
- **知识** – 事实、记忆等
- **工具** – 工具调用的反馈

  ![](https://blog.langchain.com/content/images/size/w600/2025/07/image-1.png)

### 长上下文可能导致的问题

#### 上下文分心

积累的上下文（历史记录）过于庞大，导致模型倾向于**重复历史行为**，而非合成新计划，没有跟紧核心的目标。

#### 上下文混淆

模型被迫**关注无关或无用的信息**（例如过多的工具描述），导致认知过载。
根源在于：如果你把某些内容放入语境中，模型就必须关注它。这些内容可能是无关信息或不必要的工具定义，但模型会将其纳入考虑范围。

#### 上下文冲突

新积累的信息或工具与上下文中已有的信息发生**直接冲突**
![image.png](https://yuvenhol-1255563050.cos.ap-beijing.myqcloud.com/img/202512171806512.png)
左侧提示中的所有信息都包含在右侧的几条消息中，这些消息将在多轮聊天中呈现出来。
分片提示产生的结果明显更差，平均下降了 39%。该团队测试了一系列模型——OpenAI 备受赞誉的 o3 的得分从 98.1 降至 64.1。
大型语言模型（LLMs）往往会在对话初期就做出假设，并过早地尝试生成最终解决方案，且会过度依赖这些方案。简单来说，我们发现当大型语言模型在对话中走入误区时，它们会迷失方向且无法恢复。

### 面向 Agent 的上下文工程

随着 LLM 在[推理](https://platform.openai.com/docs/guides/reasoning?api-mode=responses&ref=blog.langchain.com)和[工具调用](https://www.anthropic.com/engineering/building-effective-agents?ref=blog.langchain.com)方面的能力不断增强，业界对[agent](https://www.anthropic.com/engineering/building-effective-agents?ref=blog.langchain.com)的兴趣也急剧增长。[智能体](https://www.anthropic.com/engineering/building-effective-agents?ref=blog.langchain.com)会交错进行[LLM 调用和工具调用](https://www.anthropic.com/engineering/building-effective-agents?ref=blog.langchain.com)，通常是为了完成长期运行的任务。智能体交错进行 LLM 调用和工具调用，利用工具反馈来决定下一步行动。

![](https://blog.langchain.com/content/images/size/w600/2025/07/image-2.png)

智能体交错进行 LLM 调用和工具调用，利用工具反馈来决定下一步行动

然而，长期运行的任务和工具调用反馈的累积意味着智能体通常会消耗大量 token。这可能导致许多问题：可能[超出上下文窗口的大小](https://cognition.ai/blog/kevin-32b?ref=blog.langchain.com)，导致成本/延迟激增，或降低智能体性能。
![](https://blog.langchain.com/content/images/size/w600/2025/07/image-3.png)


[Anthropic](https://www.anthropic.com/engineering/built-multi-agent-research-system?ref=blog.langchain.com)也明确指出了这一点：

> _智能体经常进行长达数百个回合的对话，需要精心管理上下文策略。_

那么，人们现在是如何应对这一挑战的呢？智能体上下文工程的常见策略分为四个类别——**写入、选择、压缩和隔离**，通过回顾一些流行智能体产品和论文来举例说明每种策略。

![](https://blog.langchain.com/content/images/size/w600/2025/07/image-4.png)

上下文工程的通用类别

### 写入上下文

_写入上下文意味着将其保存在上下文窗口之外，以帮助智能体完成任务。_

**暂存区**

人类在解决问题时，会做笔记并记住一些信息以备将来相关任务使用。智能体也正在获得这些能力！通过"[暂存区](https://www.anthropic.com/engineering/claude-think-tool?ref=blog.langchain.com)"做笔记是一种在智能体执行任务时持久保存信息的方法。其思路是将信息保存在上下文窗口之外，以便智能体随时可用。[Anthropic 的多智能体研究系统](https://www.anthropic.com/engineering/built-multi-agent-research-system?ref=blog.langchain.com)提供了一个清晰的例子：

> _LeadResearcher 首先思考方法，并将其计划保存到 Memory 中以持久化上下文，因为如果上下文窗口超过 200,000 个 token，它将被截断，而保留计划非常重要。_

暂存区可以通过几种不同的方式实现。它们可以是一个简单的[工具调用](https://www.anthropic.com/engineering/claude-think-tool?ref=blog.langchain.com)，将内容[写入文件](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem?ref=blog.langchain.com)。它们也可以是会话期间持续存在的运行时[状态对象](https://langchain-ai.github.io/langgraph/concepts/low_level/?ref=blog.langchain.com#state)中的一个字段。无论哪种方式，暂存区都让智能体能够保存有用的信息来帮助完成任务。

**记忆**

暂存区帮助智能体在给定会话内完成任务，但有时智能体需要记住*多个*会话之间的信息！[Reflexion](https://arxiv.org/abs/2303.11366?ref=blog.langchain.com)引入了在每个智能体回合后进行反思并重用这些自生成记忆的概念。[Generative Agents](https://ar5iv.labs.arxiv.org/html/2304.03442?ref=blog.langchain.com)则根据过去的智能体反馈集合定期合成记忆。

![](https://blog.langchain.com/content/images/size/w600/2025/07/image-5.png)

LLM 可用于更新或创建记忆

这些概念已经融入到流行的产品中，如 [ChatGPT](https://help.openai.com/en/articles/8590148-memory-faq?ref=blog.langchain.com)、[Cursor](https://forum.cursor.com/t/0-51-memories-feature/98509?ref=blog.langchain.com) 和 [Windsurf](https://docs.windsurf.com/windsurf/cascade/memories?ref=blog.langchain.com)，它们都有基于用户与智能体交互自动生成可跨会话持久化的长期记忆的机制。

### 选择上下文

_选择上下文意味着将其拉入上下文窗口，以帮助智能体完成任务。_

**暂存区**

从暂存区中选择上下文的机制取决于暂存区的实现方式。如果它是一个[工具](https://www.anthropic.com/engineering/claude-think-tool?ref=blog.langchain.com)，那么智能体只需通过工具调用即可读取它。如果它是智能体运行时状态的一部分，那么开发者可以选择在每一步向智能体暴露状态的哪些部分。这提供了精细的控制，可以在后续回合中将暂存区上下文暴露给 LLM。

**记忆**

如果智能体能够保存记忆，它们也需要能够选择与正在执行的任务相关的记忆。这有几个原因：智能体可能会选择少样本示例（[情景性](https://langchain-ai.github.io/langgraph/concepts/memory/?ref=blog.langchain.com#memory-types)[记忆](https://arxiv.org/pdf/2309.02427?ref=blog.langchain.com)）作为期望行为的示例，选择指令（[程序性](https://langchain-ai.github.io/langgraph/concepts/memory/?ref=blog.langchain.com#memory-types)[记忆](https://arxiv.org/pdf/2309.02427?ref=blog.langchain.com)）来引导行为，或选择事实（[语义性](https://langchain-ai.github.io/langgraph/concepts/memory/?ref=blog.langchain.com#memory-types)[记忆](https://arxiv.org/pdf/2309.02427?ref=blog.langchain.com)）作为任务相关的上下文。

![](https://blog.langchain.com/content/images/size/w600/2025/07/image-6.png)

可以应用摘要的几个场景

一个挑战是确保选择相关的记忆。一些流行的智能体只是使用一组*始终*被拉入上下文的特定文件。例如，许多代码智能体使用特定文件来保存指令（"程序性"记忆），或者在某些情况下保存示例（"情景性"记忆）。Claude Code 使用 [`CLAUDE.md`](http://claude.md/?ref=blog.langchain.com)。[Cursor](https://docs.cursor.com/context/rules?ref=blog.langchain.com) 和 [Windsurf](https://windsurf.com/editor/directory?ref=blog.langchain.com) 使用规则文件。

但是，如果智能体存储了大量事实和/或关系（例如，[语义性](https://langchain-ai.github.io/langgraph/concepts/memory/?ref=blog.langchain.com#memory-types)记忆），选择就更加困难。[ChatGPT](https://help.openai.com/en/articles/8590148-memory-faq?ref=blog.langchain.com) 是一个很好的例子，它是一个流行的产品，可以存储并从大量用户特定记忆中进行选择。

嵌入和/或用于内存索引的[知识图](https://neo4j.com/blog/developer/graphiti-knowledge-graph-memory/?ref=blog.langchain.com#:~:text=changes%20since%20updates%20can%20trigger,and%20holistic%20memory%20for%20agentic)常用于辅助选择。尽管如此，记忆选择仍然具有挑战性。在 AIEngineer World's Fair 上，[Simon Willison 分享了一个](https://simonwillison.net/2025/Jun/6/six-months-in-llms/?ref=blog.langchain.com)选择出错的例子：ChatGPT 从他的记忆中获取了位置信息，并意外地将其注入到请求的图像中。这种意外或非期望的记忆检索可能会让一些用户感觉上下文窗口"_不再属于他们_"！

**工具**

智能体使用工具，但如果提供太多工具，它们可能会不堪重负。这通常是因为工具描述重叠，导致模型混淆该使用哪个工具。一种方法是[对工具描述应用 RAG（检索增强生成）](https://arxiv.org/abs/2410.14594?ref=blog.langchain.com)，以便仅为任务提取最相关的工具。一些[最近的论文](https://arxiv.org/abs/2505.03275?ref=blog.langchain.com)表明，这可以将工具选择的准确性提高 3 倍。

**知识**

[RAG](https://github.com/langchain-ai/rag-from-scratch?ref=blog.langchain.com) 是一个丰富的话题，它[可能是上下文工程的核心挑战](https://x.com/_mohansolo/status/1899630246862966837?ref=blog.langchain.com)。代码智能体是大规模生产中 RAG 的最佳示例之一。Windsurf 的 Varun 很好地捕捉了其中一些挑战：

> _索引代码 ≠ 上下文检索…… \[我们正在进行索引和嵌入搜索…… \[利用\] AST 解析代码并根据语义上有意义的边界进行分块……随着代码库规模的增大，嵌入搜索作为检索启发式方法变得不可靠……我们必须依赖 grep/文件搜索、基于知识图的检索和……一个重新排序步骤的组合，其中\[上下文\]按照相关性排序。_

### 压缩上下文

_压缩上下文涉及仅保留完成任务所需的 token。_

**上下文摘要**

智能体交互可能持续[数百个回合](https://www.anthropic.com/engineering/built-multi-agent-research-system?ref=blog.langchain.com)并使用大量 token 的工具调用。摘要是管理这些挑战的一种常见方式。如果你使用过 Claude Code，你已经见过这种情况。Claude Code 在你超过上下文窗口的 95% 后会运行"[自动压缩](https://docs.anthropic.com/en/docs/claude-code/costs?ref=blog.langchain.com)"，它将总结用户与智能体交互的完整轨迹。这种跨[智能体轨迹](https://langchain-ai.github.io/langgraph/concepts/memory/?ref=blog.langchain.com#manage-short-term-memory)的压缩可以使用各种策略，例如[递归](https://arxiv.org/pdf/2308.15022?ref=blog.langchain.com#:~:text=the%20retrieved%20utterances%20capture%20the,based%203)或[分层](https://alignment.anthropic.com/2025/summarization-for-monitoring/?ref=blog.langchain.com#:~:text=We%20addressed%20these%20issues%20by,of%20our%20computer%20use%20capability)摘要。

![](https://blog.langchain.com/content/images/size/w600/2025/07/image-7.png)

可以应用摘要的几个场景

在智能体设计中的特定点[添加摘要](https://github.com/langchain-ai/open_deep_research/blob/e5a5160a398a3699857d00d8569cb7fd0ac48a4f/src/open_deep_research/utils.py?ref=blog.langchain.com#L1407)也很有用。例如，它可以用于后处理某些工具调用（例如，消耗大量 token 的搜索工具）。第二个例子是，[Cognition](https://cognition.ai/blog/dont-build-multi-agents?ref=blog.langchain.com#a-theory-of-building-long-running-agents)提到了在智能体-智能体边界处使用摘要，以减少知识传递过程中的 token 消耗。如果需要捕获特定事件或决策，摘要可能具有挑战性。[Cognition](https://cognition.ai/blog/dont-build-multi-agents?ref=blog.langchain.com#a-theory-of-building-long-running-agents)为此使用了一个经过微调的模型，这突显了在这一步骤上可能需要投入多少工作。

**上下文修剪**

虽然摘要通常使用 LLM 来提取上下文中最相关的部分，但修剪通常可以过滤，或者正如 Drew Breunig 指出的，可以"[修剪](https://www.dbreunig.com/2025/06/26/how-to-fix-your-context.html?ref=blog.langchain.com)"上下文。这可以使用硬编码的启发式方法，例如从列表中删除[较旧的消息](https://python.langchain.com/docs/how_to/trim_messages/?ref=blog.langchain.com)。Drew 还提到了 [Provence](https://arxiv.org/abs/2501.16214?ref=blog.langchain.com)，一个针对问答训练过的上下文修剪器。

### 隔离上下文

_隔离上下文涉及将其拆分以帮助智能体完成任务。_

**多智能体**

隔离上下文最流行的方法之一是在子智能体之间拆分它。OpenAI [Swarm](https://github.com/openai/swarm?ref=blog.langchain.com) 库的一个动机是[关注点分离](https://openai.github.io/openai-agents-python/ref/agent/?ref=blog.langchain.com)，即一个智能体团队可以处理特定的子任务。每个智能体都有一套特定的工具、指令和自己的上下文窗口。

![](https://blog.langchain.com/content/images/size/w600/2025/07/image-8.png)

在多个智能体之间拆分上下文

Anthropic 的[多智能体研究系统](https://www.anthropic.com/engineering/built-multi-agent-research-system?ref=blog.langchain.com)为此提供了一个案例：许多具有隔离上下文的智能体优于单智能体，主要是因为每个子智能体的上下文窗口可以分配给更狭窄的子任务。正如博客所说：

> _\[子智能体并行运行\]，拥有各自的上下文窗口，同时探索问题的不同方面。_

当然，多智能体的挑战包括 token 使用（例如，据 Anthropic 报告，[比聊天多消耗高达 15 倍的 token](https://www.anthropic.com/engineering/built-multi-agent-research-system?ref=blog.langchain.com)），需要仔细的[提示工程](https://www.anthropic.com/engineering/built-multi-agent-research-system?ref=blog.langchain.com)来规划子智能体的工作，以及协调子智能体。

**使用环境进行上下文隔离**

HuggingFace 的[深度研究系统](https://huggingface.co/blog/open-deep-research#:~:text=From%20building%20,it%20can%20still%20use%20it)展示了上下文隔离的另一个有趣例子。大多数智能体使用[工具调用 API](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview?ref=blog.langchain.com)，该 API 返回可以传递给工具（例如搜索 API）以获取工具反馈（例如搜索结果）的 JSON 对象（工具参数）。HuggingFace 使用一个 [CodeAgent](https://huggingface.co/papers/2402.01030?ref=blog.langchain.com)，它输出包含所需工具调用的代码。然后代码在[沙箱](https://e2b.dev/?ref=blog.langchain.com)中运行。从工具调用中选择的上下文（例如返回值）然后被传递回 LLM。

![](https://blog.langchain.com/content/images/size/w600/2025/07/image-9.png)

沙箱可以将上下文与 LLM 隔离。

这使得上下文可以在环境中与 LLM 隔离。Hugging Face 指出，这特别适用于隔离消耗大量 token 的对象：

> _\[代码智能体允许\]更好地处理状态……需要存储这个图像/音频/其他内容以供以后使用？没问题，只需将其赋值给_ [_你的状态中的一个变量，然后你\[稍后使用它\]_](https://deepwiki.com/search/i-am-wondering-if-state-that-i_0e153539-282a-437c-b2b0-d2d68e51b873?ref=blog.langchain.com)_。_

**状态**

值得指出的是，智能体的运行时[状态对象](https://langchain-ai.github.io/langgraph/concepts/low_level/?ref=blog.langchain.com#state)也是一种隔离上下文的好方法。这可以起到与沙箱相同的作用。状态对象可以用一个具有多个字段的[模式](https://langchain-ai.github.io/langgraph/concepts/low_level/?ref=blog.langchain.com#schema)来设计，以便将上下文写入其中。模式的某个字段（例如 `messages`）可以在智能体的每个回合暴露给 LLM，但模式可以将其他字段中的信息隔离开，以供更选择性使用。

### Context Caching

#### 公式
$$\text{Result} = \text{Softmax}([Q_{old}, Q_{new}] \cdot [K_{old}, K_{new}]^T) \cdot [V_{cached}, V_{new}]$$

$$\text{Result}_{with-cache} = \text{Softmax}(Q_{new} \cdot [K_{cached}, K_{new}]^T) \cdot [V_{cached}, V_{new}]$$


####  Prompt 数据结构拆解

我们将 Prompt 分为 **Static（静态前缀，可缓存）** 和 **Dynamic（动态后缀，不可缓存）** 两部分。

##### **Part A: 静态前缀 (Static Prefix)**

> _这部分是所有请求共用的，长度很大。_

JSON

```
{
  "system_instruction": "你是一名资深的华尔街金融分析师。请基于下方的财务报告回答用户问题，不要编造数据。",
  "context_document": "...(此处省略 5000 字的财报正文)... 
   [2024 Q3 Report]
   - 总营收: 890亿美元
   - 净利润: 230亿美元
   - 服务业务增长: 15%
   - iPhone 销量: 下滑 2%
   ... (大量细节数据) ... "
}
```

- **Token 数量**: 假设共 **2000 Tokens**。
    
- **计算代价**: 高（$2000^2$ 级别的复杂度）。
    

##### **Part B: 动态后缀 (Dynamic Suffix)**

> _这部分是用户每次不一样的问题。_

- **User Query 1**: "这份财报中，服务业务的表现如何？" (20 Tokens)
    
- **User Query 2**: "相比上一季度，净利润主要受什么影响？" (25 Tokens)
    

####  真实计算过程对比

**请求 1 (Cold Start - 无缓存 / 首次建立缓存)**

用户发送：`[Static Prefix] + [User Query 1]`

1. **输入检查**：系统计算 `Hash(Static Prefix)`，发现缓存库里没有。
    
2. **Prefill 计算 (预填充)**：
    
    - 模型必须计算全部 **2020 Tokens** (2000 Prefix + 20 Query) 的 $Q, K, V$。
        
    - 这非常慢，显存占用瞬间飙升。
        
3. **写入缓存 (Cache Write)**：
    
    - 系统将前 **2000 Tokens** 对应的 $K, V$ 矩阵提取出来。
        
    - 存入显存/高速缓存，Key 为 `Hash(Static Prefix)`。
        
4. **生成回答**：输出 "服务业务增长了 15%..."。
    

- **耗时 (TTFT)**: **500 ms** (假设)
    
- **计算量**: 100%
    


(Warm Start - 缓存命中)**

用户发送：`[Static Prefix] + [User Query 2]`

1. **输入检查**：
    
    - 系统扫描输入，发现前 2000 Tokens 的哈希值与缓存库匹配！
        
    - **命中 (Cache Hit)!**
        
2. **KV 加载 (Memory Load)**：
    
    - **直接跳过**前 2000 Tokens 的计算。
        
    - 从显存中直接把 $K_{cached}$ 和 $V_{cached}$ (对应那 5000 字财报的理解) 拿出来。
        
3. **增量计算 (Incremental)**：
    
    - 模型**只计算**后面新的 25 Tokens (`[User Query 2]`)。
        
    - 计算 $Q_{new}$ (25个)。
        
    - 执行 拼接与注意力：
        
        $$\text{Attn} = \text{Softmax}(Q_{new} \cdot [K_{cached}, K_{new}]^T) \dots$$
        
4. **生成回答**：输出 "净利润受汇率波动影响..."。
    

- **耗时 (TTFT)**: **50 ms** (快了 10 倍)
    
- **计算量**: 仅约为原来的 1.2%
    



####  显存中的数据视角 (可视化 KV Tensor)

为了让你理解“水平拼接”，我们看看显存里存的 Tensor 形状（假设 Hidden Size = 4096, 2 Layers）。

**在请求 2 处理时，显存里的状态：**

|**数据来源**|**Tensor 名称**|**形状 (Batch, Seq_Len, Dim)**|**状态**|
|---|---|---|---|
|**缓存库**|`K_cached`|`(1, 2000, 4096)`|**直接读取 (Copy)**|
|**新输入**|`K_new`|`(1, 25, 4096)`|**实时计算 (Compute)**|
|**拼接后**|`K_full`|`(1, 2025, 4096)`|**用于 Attention**|

- **如果不用缓存**：你需要用 GPU 里的矩阵乘法单元（Tensor Cores）硬算出一个 `(1, 2025, 4096)` 的矩阵，这需要大量的 FLOPs（浮点运算次数）。
    
- **用了缓存**：你只需要算那个小小的 `(1, 25, 4096)`，剩下的 2000 长度直接通过内存带宽搬运。
    

####  商业价值总结

如果我们使用类似 Anthropic 的 Claude 3.5 Sonnet API (支持 Prompt Caching)：

|**指标**|**请求 1 (写入缓存)**|**请求 2 (读取缓存)**|**提升/节省**|
|---|---|---|---|
|**输入 Tokens**|2020|2025|-|
|**计费价格**|$3.00 / MTok|$0.30 / MTok|**便宜 90%**|
|**首字延迟 (TTFT)**|~1.5 秒|~0.2 秒|**快 7-8 倍**|
|**适用场景**|初始化|多轮对话、长文分析|体验质变|

这个案例说明了：只要你的应用场景中有**“重复出现的长背景”**（比如上传一本书聊很久，或者固定的复杂 System Prompt），Prompt Caching 就能把原本昂贵的 AI 推理变成“查字典”一样的低成本操作。

## Agents vs Workflows
Agentic Systems 是当前人工智能领域的核心范式，它标志着大型语言模型（LLMs）的能力已从简单的单次提示响应，演变为能够展现动态规划、工具使用和记忆存储等特性的一定程度的自主化系。

Agentic Systems 的实现，目前主流方案有两个：Agent 派和 Workflow 派。在构建系统时需要熟悉，挑选合适的基础方案。


AI 智能体 (AI Agents) 和 AI 工作流 (AI Workflows) 在智能体系统和架构中代表了两种根本不同的自动化范式，而选择哪种方法是一项关键的战略决策，其核心在于对 **确定性** (Determinism) 和 **自主性** (Autonomy) 之间的权衡。
## Agent Engineering
如果你构建过智能体，就会知道「在我的机器上能运行」和「能在生产环境运行」之间的差距可能非常巨大。传统软件假设你大多了解输入并能定义输出。智能体两者都不给你：用户可以说任何话，而可能的行为空间是敞开的。这就是它们强大的原因——也是它们可能以你意想不到的方式出岔子的原因。

过去3年，我们目睹了成千上万的团队在这个现实面前挣扎。那些成功将可靠产品部署到生产环境的团队——如 Clay、Vanta、LinkedIn 和 Cloudflare 等公司——并没有遵循传统的软件开发手册。他们正在开创某种新事物：**智能体工程（agent engineering）。**

### 什么是智能体工程？

智能体工程是将非确定性的大语言模型系统迭代优化为可靠生产体验的过程。这是一个循环过程：**构建、测试、部署、观察、优化、重复。**

![](https://blog.langchain.com/content/images/2025/12/Frame-1--2--1.png)

这里的关键是，部署不是最终目标。它只是你持续前进以获得新见解并改进智能体的方式。要做出有意义的改进，你需要理解生产环境中正在发生什么。你在这个循环中移动得越快，你的智能体就越可靠。

我们将智能体工程视为一门结合了3种技能组合协同工作的新学科：

- **产品思维**定义范围并塑造智能体行为。这涉及：
  - 编写驱动智能体行为的提示词（通常是数百或数千行）。良好的沟通和写作能力在这里至关重要。
  - 深入理解智能体要复现的「待完成工作」
  - 定义评估标准，测试智能体是否按照「待完成工作」的意图执行
- **工程**构建使智能体具备生产就绪性的基础设施。这涉及：
  - 为智能体编写可使用的工具
  - 开发智能体交互的UI/UX（包含流式传输、中断处理等）
  - 创建健壮运行时，处理持久执行、人机协同暂停和内存管理。
- **数据科学**衡量并随着时间改进智能体性能。这涉及：
  - 构建系统（评估、A/B测试、监控等）以衡量智能体性能和可靠性
  - 分析使用模式和错误分析（因为智能体相比传统软件有更广泛的用户使用方式）

### 智能体工程出现在哪里

智能体工程不是一个新的职位头衔。相反，它是现有团队在构建能够推理、适应和不可预测行为的系统时所承担的一系列职责。如今正在部署可靠智能体的组织正在扩展工程、产品和数据团队的技能，以满足非确定性系统的需求。

这种实践通常出现在以下场景：

- **软件工程师和机器学习工程师**编写提示词并为智能体构建工具，追踪智能体为何进行特定工具调用，并改进底层模型
- **平台工程师**构建处理持久执行和人机协同工作流的智能体基础设施
- **产品经理**编写提示词，定义智能体范围，并确保智能体解决正确的问题
- **数据科学家**衡量智能体可靠性并识别改进机会

这些团队拥抱快速迭代，你会经常看到软件工程师追踪错误并将洞察移交给产品经理以调整提示词，或者产品经理识别需要工程师提供新工具的范围问题。每方都认识到，强化智能体的真正工作是通过观察生产行为并基于所学进行系统性优化的循环来完成的。

### 为什么需要智能体工程，为什么是现在？

两个根本性的转变使得智能体工程变得必要。

首先，大语言模型已经足够强大，能够处理复杂的多步骤工作流。我们已经看到智能体承担整个工作，而不仅仅是任务。Clay 使用智能体处理从潜在客户研究到个性化推广和CRM更新的所有事务。LinkedIn 使用智能体扫描庞大的候选人池进行招聘，即时排名候选人并呈现最匹配的人选。我们开始跨越智能体在生产环境中提供实质性业务价值的门槛。

其次，这种能力伴随着真实的不确定性。简单的大语言模型应用虽然是非确定性的，但往往有更受约束的行为。智能体则不同。它们在多个步骤中进行推理、调用工具，并根据上下文进行适应。使智能体有用的那些因素也使它们的行为与传统软件不同。这通常意味着：

- **每个输入都是边缘情况。** 当用户可以用自然语言询问任何内容时，不存在所谓的「正常」输入。当你输入「让它脱颖而出」或「像上次那样做但要不同」时，智能体（就像人类一样）可能会以不同的方式解释提示词。
- **你无法用旧方式调试。** 因为太多逻辑存在于模型内部，你必须检查每个决策和工具调用。微小的提示词或配置调整可能导致行为发生巨大变化。
- **「正常工作」不是二元的。** 智能体可能拥有99.99%的正常运行时间，同时仍然偏离轨道并出故障。对于重要问题，比如：智能体是否做出了正确的调用？是否正确使用工具？是否遵循了你的指令意图？并不总是有简单的「是/否」答案。

当你将这一切放在一起——智能体运行真实、高影响的工作流，但其行为方式是传统软件无法解决的——就出现了新学科的机会和需求。智能体工程让你能够利用大语言模型的力量，同时构建你真正可以在生产中信任的系统。

### 智能体工程在实践中是什么样子？

智能体工程遵循与传统软件开发不同的原则。要实现可靠的智能体系统，部署是你学习的方式，而不是你在学习之后做的事情。

我们看到成功的工程团队遵循类似以下的智能体开发节奏：

- **构建智能体的基础。** 从设计智能体的基础开始，无论是简单的带工具的大语言模型调用，还是复杂的多智能体系统。你的架构取决于你需要多少工作流（确定性的逐步流程）与多少代理能力（大语言模型驱动的决策）。
- **基于你能想象的场景进行测试。** 针对示例场景测试你的智能体，捕捉提示词、工具定义和工作流中的明显问题。与传统软件可以规划用户流程不同，你无法预测用户与自然语言输入交互的每种方式。将思维从「详尽测试，然后部署」转变为「合理测试，部署以了解真正重要的是什么」。
- **部署以观察真实世界行为。** 一旦部署，你立即开始看到你未曾考虑过的输入，每个生产跟踪都显示你的智能体实际需要处理什么。
- **观察。** 跟踪每次交互以查看完整对话、每次工具调用，以及影响智能体每个决策的确切上下文。对你的生产数据运行评估，以衡量智能体质量，无论你关心的是准确性、延迟、用户满意度还是其他标准。
- **优化。** 一旦识别出失败模式，通过编辑提示词和修改工具定义进行优化。这一切都是连续的，因为你可以将有问题的情况添加回你的示例场景集中进行回归测试。
- **重复。** 部署你的改进并观察生产环境中的变化。每个循环都会教你关于用户如何与你的智能体交互，以及可靠性在你具体上下文中实际意味着什么的新知识。

### 工程的新标准

如今部署可靠智能体的团队有一个共同点：他们已经停止尝试在启动前完善智能体，开始将生产环境视为主要教师。换句话说，追踪每个决策，大规模评估，并在数天内而非季度内部署改进。

智能体工程正在兴起，因为机会需要它。智能体现在可以处理以前需要人类判断的工作流，但前提是你能使它们足够可靠以赢得信任。没有捷径，只有系统性的迭代工作。问题不在于智能体工程是否会成为标准实践，而在于你的团队能以多快的速度采纳它，以解锁智能体的能力。

### 工作流 (AI Workflows)

AI 工作流是遵循 **预定义代码路径** 和规则的结构化系统，旨在通过固定序列的步骤自动化常规、重复性任务。工作流的重点在于==可预测性==和==一致性==。路径是 **确定性的**。在给定相同输入的情况下，每次运行都遵循相同的分支和预定逻辑。

价值：工作流提供了透明度、可预算的成本和高可靠性。它们易于审计，并为高容量、日常运营任务（如发票处理、座位查询）提供了 **治理就绪**（ “先搭好‘管理框架’，再启动具体工作”） 的解决方案。

### 自主智能体 (Autonomous AI Agents)

AI 智能体是由大型语言模型 (LLMs) 驱动的软件系统，能够 **自主地** 做出决策、适应新信息，并==动态地朝着预定目标工作==。智能体在运行时 **动态地指导** 自己的流程和工具使用。

**价值：** 智能体提供了 **战略价值**，适用于动态、复杂、模糊不清的任务，在这些任务中，解决问题的路径无法被硬编码，需要独立的判断力。例如，复杂的投资研究或诊断支持工单。

### 混合方案：智能体工作流 (Agentic Workflows)

为了兼顾结构和灵活性，很多场景下可以使用 混合方法——智能体工作流，它允许智能体在预定义的、结构化步骤中进行推理和行动。这种方法 **脚本化** 了流程的 **核心逻辑** (spine)，以确保强制性步骤得到遵守，同时允许模型在流程的“边缘”进行即兴创作和适应，从而在处理歧义和可变性的同时保持整体治理。

## 多智能体（multi-agent systems）
## attention is all your need
## LLM 进展

Thinking in Tool-Use

## Vibe Coding & Spec Coding

## langchain1.0


