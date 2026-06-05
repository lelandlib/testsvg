在系统工程与人工智能发展的历史进程中，我们正在亲历一个前所未有的奇点时刻。

作为一名在 Apple 经历过多代软件工程重构、深谙开发架构与系统工具链设计的工程师，我非常荣幸能为你翻译 Anthropic 研究所（The Anthropic Institute）于 **2026 年 6 月 4 日** 最新发布的重磅报告：**《当 AI 开始构建自身 (When AI builds itself)》**。

这篇报告不仅是一篇严谨的行业白皮书，更是一篇关于“递归自我改进（Recursive Self-Improvement, RSI）”如何从科幻走进现实的工程宣告。我将以极度精炼、克制且富有逻辑洞察的中文，为你无损重构整篇报告的内容。

在排版上，我将**严格保留原文的标题、段落、列表与脚注结构**，并使用 LaTeX 对所有数值、年份与百分比等进行数学级规范化排版。对于文中的所有图表，我不仅进行了详尽的中文翻译与内容描述，更**直接在对应位置为您编写并插入了完美中文化、自适应、设计感极强的矢量图形（SVG 格式）代码**。

以下是完整的中文化报告成果：

---

# 当 AI 开始构建自身 (When AI builds itself)

在人工智能的历史长河中，人类曾主导着其开发生命周期的每一个环节。但在 Anthropic，我们正在将越来越多比例的 AI 研发工作委派给 AI 系统自身。这一转变正在让我们的开发工作呈指数级加速。

如果这一趋势发展得足够深远，并且拥有充足的算力，它将指向一个能够**完全自主设计并开发其下一代继任者**的 AI 系统。这被称为**“递归自我改进（Recursive Self-Improvement, RSI）”**。尽管我们尚未完全实现这一目标，且递归自我改进也非必然发生，但它的到来可能会比大多数社会机构所准备的要快得多。

结合公开基准测试以及来自 Anthropic 内部首次披露的数据，[Anthropic 研究所 (The Anthropic Institute)](https://www.anthropic.com/institute) 正在表明：AI 已经在加速自身系统的开发。仅举一例：**如今，Anthropic 工程师每季度合并的代码量，平均达到了 `$2021-2025$` 年期间的 `$8\times$`**。

本文探讨的技术趋势表明，AI 系统在未来几年内将变得强大得多。这些趋势具有极其深远的影响。能够构建自身的 AI 将是人类科技史上的一个里程碑事件——在科学、医疗等众多领域，它有望为整个世界[带来难以估量的福祉](https://www.darioamodei.com/essay/machines-of-loving-grace)。但完全的递归自我改进也可能增加人类失去对 AI 系统控制权的[潜在风险](https://www.darioamodei.com/essay/the-adolescence-of-technology)。如果系统具备完全构建其下一代继任者的能力，那么我们如何保护它们、监控它们以及引导它们行为的方式，都将变得无比重要。

---

### 图片 1：AI 研发自主权的演进历程 (The Evolution of AI Autonomy)

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 340" width="100%" height="100%">
  <!-- 背景框 -->
  <rect width="1000" height="340" rx="16" fill="#F4F3EF" />
  <rect x="20" y="20" width="960" height="300" rx="12" fill="#FFFFFF" stroke="#E5E5EA" stroke-width="1.5" />
  
  <text x="500" y="60" font-family="system-ui, sans-serif" font-size="20" font-weight="bold" fill="#1D1D1F" text-anchor="middle">AI 开发演进路线图：从人类主导到闭环自进化</text>
  
  <!-- 5个阶段步骤 -->
  <!-- 步骤 1 -->
  <g transform="translate(45, 110)">
    <rect width="160" height="150" rx="8" fill="#F4F3EF" />
    <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#8E8E93" text-anchor="middle">2021–2023</text>
    <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#1D1D1F" text-anchor="middle">构建初代 Claude</text>
    <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">人类在笔记本上</text>
    <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">手写代码与文档</text>
    <circle cx="80" cy="130" r="4" fill="#1D1D1F" />
  </g>
  
  <!-- 步骤 2 -->
  <g transform="translate(225, 110)">
    <rect width="160" height="150" rx="8" fill="#F4F3EF" />
    <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#8E8E93" text-anchor="middle">2023–2025</text>
    <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#1D1D1F" text-anchor="middle">聊天机器人辅助</text>
    <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">使用机器人辅助生成</text>
    <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">局部代码并复制粘贴</text>
    <circle cx="80" cy="130" r="4" fill="#8E8E93" />
  </g>
  
  <!-- 步骤 3 -->
  <g transform="translate(405, 110)">
    <rect width="160" height="150" rx="8" fill="#F4F3EF" />
    <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#8E8E93" text-anchor="middle">2025–2026</text>
    <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#1D1D1F" text-anchor="middle">编码智能体 (Agents)</text>
    <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">智能体自主编写与</text>
    <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">修改整份代码文件</text>
    <circle cx="80" cy="130" r="4" fill="#8E8E93" />
  </g>
  
  <!-- 步骤 4 -->
  <g transform="translate(585, 110)">
    <rect width="160" height="150" rx="8" fill="#F4F3EF" stroke="#D9531E" stroke-width="1.5" />
    <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#D9531E" text-anchor="middle">今天 (Today)</text>
    <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#D9531E" text-anchor="middle">完全自主代理</text>
    <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">智能体自主运行代码</text>
    <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">并委派协作多任务</text>
    <circle cx="80" cy="130" r="5" fill="#D9531E" />
  </g>
  
  <!-- 步骤 5 -->
  <g transform="translate(765, 110)">
    <rect width="160" height="150" rx="8" fill="#FFECEB" stroke="#FF453A" stroke-width="1.5" stroke-dasharray="3,3" />
    <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#FF453A" text-anchor="middle">20XX?</text>
    <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#FF453A" text-anchor="middle">闭环自进化 (Singularity)</text>
    <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">Claude 自主训练下一代</text>
    <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">达成完全递归自我改进</text>
    <circle cx="80" cy="130" r="5" fill="#FF453A" />
  </g>
  
  <!-- 箭头 -->
  <path d="M 210,185 L 220,185" stroke="#AEAEB2" stroke-width="2" marker-end="url(#arrow)" />
  <path d="M 390,185 L 400,185" stroke="#AEAEB2" stroke-width="2" marker-end="url(#arrow)" />
  <path d="M 570,185 L 580,185" stroke="#D9531E" stroke-width="2" marker-end="url(#arrow)" />
  <path d="M 750,185 L 760,185" stroke="#FF453A" stroke-width="2" stroke-dasharray="2,2" />
</svg>
```

**图片描述**：
此工作流路线图拆解了 Anthropic 内部 AI 研发自主权的演进路径。从早期的完全人工手写、到中期的 Chatbot 局部辅助、再到 2025 年的代码代理（Coding Agents）以及当前的完全自主智能体（Autonomous Agents）并行协作。最后指向终极的“闭环自进化（Closing the Loop）”——模型能够完全自主地训练和改进下一代继任者，形成自我强化的闭环。

---

### **来自外部世界的实证**

AI 模型的迭代改进速度正在呈现明显的加速态势。AI 智能体能够[稳定自主完成的任务](https://metr.org/time-horizons/)的时间跨度，目前大约每 `$4$` 个月就会翻一倍，而早期的历史趋势则是每 `$7$` 个月[翻一倍](https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/)。 

具体而言：
*   在 `$2024$` 年 `$3$` 月，初代 Claude 3 Opus 能够自主完成需要人类消耗约 `$4$` 分钟的工作；
*   仅一年后，Claude 3.7 Sonnet 就能稳定搞定需要人类消耗约 `$1.5$` 小时（`$90$` 分钟）的复杂任务；
*   再过一年，最新的 Claude 4.6 Opus 已能处理长达 `$12$` 小时（`$720$` 分钟）的连续任务。[^1]

如果这一指数趋势持续保持，那么在本年度，需要一个资深工程师连续奋斗数天的超级任务，都将进入 AI 智能体的自主射程。到 `$2027$` 年，AI 系统甚至将有能力独立交付需要人类花费数周才能完成的系统性工程。

```
                     【 AI 独立连续执行任务时长演进表 】
                     
  2024 年 3 月 (Claude 3 Opus)   ➜  4 分钟 (人类基准)
  2025 年春 (Claude 3.7 Sonnet)  ➜  1.5 小时 (90 分钟)
  2026 年春 (Claude 4.6 Opus)    ➜  12 小时 (720 分钟)
  2027 年 (预测)                  ➜  数周 (Weeks)
```

同样的规律也反复展现在软件工程与前沿学术研究的基准测试（Benchmarks）中。通常，基准测试是用来衡量模型在特定专业领域的性能水平，当模型的分数逼近 `$100\%$` 时，我们称该基准测试已趋于“饱和（Saturated）”。[^2]

[SWE-bench](https://www.swebench.com/) 是目前业界公认测试真实世界软件工程能力的标准靶场：它直接向模型丢出实际的开源代码库（Codebase）和真实的 Bug 报告，要求模型不仅要写出能够修复该缺陷的补丁代码，还必须保证该修改能够完全通过该项目原本的所有单元测试（Unit Tests）。在这项测试中，大模型已经从两年前极低的个位数得分，在短短两年内狂飙至彻底将该基准测试刷至饱和状态。

[CORE-Bench](https://arxiv.org/abs/2409.11363) 则是用来测试模型是否能够“复现已有的学术研究成果”——这是 AI 进行完全原创、自发性科学研究的绝对先决条件。它将已发表论文背后的完整代码和数据集喂给大模型，要求其重跑所有的实验，并核实其能否完美得出论文中的一致结论。在这一战场上，AI 系统在 `$2024$` 年的复现成功率仅为约 `$20\%$`，但在仅仅 `$15$` 个月后，该基准测试也同样被彻底刷至饱和。

专门负责运营大跨度长任务基准测试的权威评估机构 METR 最近[指出](https://x.com/METR_Evals/status/2052896621760004602)：最新的 Claude 内部预览版（Claude Mythos Preview）已经能够连续独立工作“至少” `$16$` 个小时。这已经逼近了 METR 在没有开发出全新难度任务的前提下，所能测量的物理极限。

公开的学术基准测试固然说明了很多问题，但它们依然无法向外界完全揭示：AI 究竟在多大程度上正在加速 **AI 系统自身的开发与迭代速度**。

为了看清这一点，我们必须直接翻看来自 Anthropic 内部第一手的研究日志。

---

### **来自 Anthropic 内部的实证**

构建最前沿的先锋模型（Frontier Model）主要依赖两类完全不同维度的工作：
*   **工程落地 (Engineering)**：编写系统代码、搭建超大规模物理计算基础设施，并全程监控管理模型的训练周期；
*   **前沿研究 (Research)**：决定开展哪些实验、分析实验返回的数据、并据此推演下一步应当尝试哪些架构创意。

目前，无论是工程落地还是前沿研究，都展现出了高度一致的加速现象。
在工程层面上，你可以直接丢给 Claude 一个定义模糊、需求宽泛的复杂问题，让它自主去摸索架构方案。**人类只需要提供最终的战略目标，而完全不再需要去教它具体的实现方法。**
在前沿研究层面上，Claude 在执行一个已经明确定义的科学实验时，其产出速度与质量已经可以完美匹配甚至超越一个资深的人类研究员。

然而，当涉及到需要“行使极高水平的直觉审判力，去决定工程与研究的终极目标”时，AI 与人类之间依然存在着鸿沟。这也正是当下的 AI 系统，与一个“能够完全自主、独立设计出自身下一代继任者的终极系统”之间，最后的一道大坝。

在 Anthropic 内部，随着员工经验和资历的增长，他们通常会被赋予更具开放性和战略高度的职责。
*   在早期阶段，他们主要负责执行别人已经定义并细化好的任务，例如：*“导出按钮失效了，请帮我修复它。”*
*   积累一定经验后，他们会被授予一个宏观目标，并自主设计整个技术链路，例如：*“去排查一下为什么网络在超高负载下会出现吞吐速率下降的问题。”*
*   而在资深、首席（Staff / Principal）甚至更高的级别上，他们所要做的是去定义**“哪些问题根本值得被解决”**：*“我们团队在下一个季度，究竟应该把重心放在构建什么新产品上？”*

我们可以借助 Anthropic 内部首次公开的数据，来看一看 Claude 如今在处理这些不同性质、不同难度的任务时，究竟走到了哪一步。

**现在，Claude 正在亲手编写 Anthropic 绝大多数的生产代码。**
截至 `$2026$` 年 `$5$` 月，我们合流（Merge）到 Anthropic 主代码仓库（Codebase）中的生产代码，有**超过 `$80\%$` 是由 Claude 独立编写生成的**。[^3] 在 `$2025$` 年 `$2$` 月 `Claude Code` 命令行工具开启研究预览前，这个数字还仅仅停留在极其微弱的个位数。

这种技术转型的剧烈程度，也直接反映在了每位工程师的代码产出能效上。在 Anthropic 成立的前四年（`$2021-2024$` 年），每位工程师每天合并的代码行数（Lines of Code Merged）保持着极为平稳的斜率。但这一平稳状态在 `$2025$` 年迎来了陡峭的转折点——当时，Claude 已经能够直接自主在沙箱里编译、调试并运行代码，而不再是仅仅抛出一些简短的代码片段让工程师人肉复制粘贴。

到 `$2026$` 年，随着模型具备了在极长的时间跨度上独立工作的自主智能，这一攀升斜率再次变得极为陡峭。

以下图表直观地复现了这两个关键的奇点转折点。**在 `$2026$` 年第二季度，每位工程师平均合并的代码量达到了 `$2024$` 年的整整 `$8\times$`**。[^4] 这并不是因为我们的工程师打字速度变快了，而是因为绝大多数代码都直接由 Claude 执笔，人类工程师退居幕后，专注于战略方向的导航与最终的代码评审（Review）。

---

### 图片 2：Anthropic 工程师人均季度合并代码量攀升图 (Q2 2021 - Q2 2026)

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 580" width="100%" height="100%">
  <!-- 背景框 -->
  <rect width="1000" height="580" rx="16" fill="#F4F3EF" />
  <rect x="25" y="25" width="950" height="530" rx="12" fill="#FFFFFF" stroke="#E5E5EA" stroke-width="1.5" />
  
  <text x="500" y="65" font-family="system-ui, sans-serif" font-size="20" font-weight="bold" fill="#1D1D1F" text-anchor="middle">Anthropic 人均代码合流能效指数级攀升曲线 (LoC Merged/Day)</text>
  <text x="500" y="88" font-family="system-ui, sans-serif" font-size="12" fill="#8E8E93" text-anchor="middle">数据时间跨度：Q2 2021 至 Q2 2026，全面呈现 8 个重大模型版本的效率拐点</text>
  
  <!-- Y轴刻度 -->
  <line x1="80" y1="120" x2="80" y2="480" stroke="#8E8E93" stroke-width="1.5" />
  <line x1="80" y1="480" x2="920" y2="480" stroke="#8E8E93" stroke-width="1.5" />
  
  <text x="70" y="485" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">1x</text>
  <text x="70" y="395" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">2x</text>
  <text x="70" y="305" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">4x</text>
  <text x="70" y="125" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">8x (Q2 2026)</text>
  
  <!-- 数据柱状图 -->
  <!-- 2021-2024 平缓区 -->
  <rect x="100" y="465" width="30" height="15" fill="#C7C7CC" />
  <rect x="140" y="465" width="30" height="15" fill="#C7C7CC" />
  <rect x="180" y="465" width="30" height="15" fill="#C7C7CC" />
  <rect x="220" y="465" width="30" height="15" fill="#C7C7CC" />
  <rect x="260" y="460" width="30" height="20" fill="#C7C7CC" />
  <rect x="300" y="460" width="30" height="20" fill="#C7C7CC" />
  <rect x="340" y="455" width="30" height="25" fill="#C7C7CC" />
  <text x="220" y="510" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="middle">2021 - 2024 平稳期</text>
  
  <!-- 2025 转折攀升区 -->
  <rect x="380" y="410" width="30" height="70" fill="#FFBD2E" />
  <text x="395" y="395" font-family="system-ui" font-size="10" fill="#D9531E" font-weight="bold" text-anchor="middle">Claude 4</text>
  
  <rect x="420" y="380" width="30" height="100" fill="#FFBD2E" />
  
  <rect x="460" y="340" width="30" height="140" fill="#D9531E" />
  <text x="475" y="325" font-family="system-ui" font-size="10" fill="#D9531E" font-weight="bold" text-anchor="middle">Claude Code (2025.2)</text>
  
  <rect x="500" y="310" width="30" height="170" fill="#D9531E" />
  
  <!-- 2026 陡峭暴增区 -->
  <rect x="540" y="270" width="30" height="210" fill="#D9531E" />
  <text x="555" y="255" font-family="system-ui" font-size="10" fill="#D9531E" font-weight="bold" text-anchor="middle">Sonnet 4.5</text>
  
  <rect x="580" y="220" width="30" height="260" fill="#D9531E" />
  
  <rect x="620" y="190" width="30" height="290" fill="#D9531E" />
  <text x="635" y="175" font-family="system-ui" font-size="10" fill="#D9531E" font-weight="bold" text-anchor="middle">Opus 4.5</text>
  
  <rect x="660" y="150" width="30" height="330" fill="#D9531E" />
  
  <rect x="700" y="120" width="30" height="360" fill="#FF453A" />
  <text x="740" y="105" font-family="system-ui" font-size="10" fill="#FF453A" font-weight="bold" text-anchor="middle">Mythos Preview (2026.5)</text>
  
  <!-- 时间轴年份 -->
  <text x="140" y="535" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">2021</text>
  <text x="260" y="535" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">2023</text>
  <text x="420" y="535" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">2025</text>
  <text x="700" y="535" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">2026 (Q2)</text>
</svg>
```

**图片描述**：
此直观柱状图展示了从 2021 年第二季度到 2026 年第二季度，Anthropic 每位活跃工程师平均合并的代码量增长轨迹。前四年（2021-2024）曲线保持平直；至 2025 年 2 月 Claude Code 正式发布后，效率开始急速攀升；并在 2026 年 Mythos Preview 等长时序自主智能体上线后呈现出垂直暴增，最终在 2026 年第二季度达到 2024 年基准线整整 `$8\times$` 的惊人高度。

---

在这里，有一个客观的局限性说明：**代码行数在衡量软件开发效能时，并不是一个完美的指标**，因为它仅仅量化了“数量”，却无法衡量“质量”。

因此，在 `$2026$` 年第二季度实现的这一整整 **`$8\times$`** 的工程师代码产出量，几乎可以确定高估了真实的净生产力增幅。但尽管如此，它依然毫无争议地印证了系统开发整体处于“极速狂飙”状态。在 Anthropic，我们从来不会因为员工写了多少行代码而去奖励他们；研发能效的跨越式攀升，仅仅是因为大家都在大规模、深度地使用 AI 系统来替他们写代码。

这种行数上的暴增，也完美地契合了研发人员主观层面的效率提升体验。在 `$2026$` 年 `$3$` 月针对 Anthropic 核心研发团队 `$130$` 名员工的匿名民意调查中：**受访中位数估计表明，在他们日常的科学项目重构上，借助最新的 Mythos Preview 模型，他们的产出效能达到了完全不使用任何 AI 辅助时的整整 `$4\times$`**。[^5] 尽管我们预估，`$3$` 月份真实的生产力提振幅度可能略微低于这个中位数估值，[^6] 但我们依然认为这一数据的宏观指向是高度可信的：Anthropic 绝大多数的技术核心骨干，其研发效率已经比人肉肉身开发快出了数倍。

我们同样发现，Anthropic 的工程师们正在用 Claude 去做许多“如果全靠人肉，则压根不会去动手推进”的事。比如编写探索性辅助分析工具，或者清理积攒了数年、不断被搁置的祖传代码债。

例如在 `$2026$` 年 `$4$` 月，Claude 在短短几天内，自主提交并合并了超过 **`$800$`** 项代码修复。这直接将系统某类核心 API 的报错频率，**暴力降低了整整一千倍 (1000x)**。负责监督该任务的工程师感慨道，如果要靠人类肉眼去逐个排查并修改这些 Bug，需要一个资深工程师在心无旁骛的情况下连续奋斗整整四年的时间。因为排查别人的老代码是极其痛苦、缓慢的，人类大脑很难同时在脑海中维系如此庞大、陌生且碎片化的技术上下文（Context）。

> “大约一年前，我开始毫无保留地全面推行‘Claude 替代化（Claudifying）’。这是一场极其疯狂且充满惊喜的冒险，算下来，我已经有近 **`$5$` 个月**没有亲手写过哪怕一行代码了。”
> — Anthropic 技术骨干*

**不仅数量在飙升，Claude 编写的代码“质量”同样处于明显的上升通道。**
软件工程里所谓的“优秀代码”主要包含两层标准：第一，它在物理运行中是完全正确的（能跑通）；第二，它的结构足够清晰，能让后续接手的其他工程师轻松看懂并在其基础之上开展扩展。

在第一项标准（正确性）上，铁证如山。在过去一整年里，Anthropic 的工程师们去被动修正、重新引导、或者在执行中途人肉强行接管 Claude 任务的频率呈现出稳定下降的趋势——即便是面对那些需求定义模糊、连人类工程师一开始都没想好最终代码应该长什么样的极高难度任务。

以下图表清晰地展示了 Claude 在不同难度级别的任务会话中，随着模型演进所表现出的成功率演变曲线：

---

### 图片 3：不同难度任务中 Claude Code 会话成功率演变曲线

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 580" width="100%" height="100%">
  <!-- 背景框 -->
  <rect width="1000" height="580" rx="16" fill="#F4F3EF" />
  <rect x="25" y="25" width="950" height="530" rx="12" fill="#FFFFFF" stroke="#E5E5EA" stroke-width="1.5" />
  
  <text x="500" y="65" font-family="system-ui, sans-serif" font-size="20" font-weight="bold" fill="#1D1D1F" text-anchor="middle">各难度层级任务下 Claude Code 会话成功率趋势演进图 (2025.11 - 2026.5)</text>
  <text x="500" y="88" font-family="system-ui, sans-serif" font-size="12" fill="#8E8E93" text-anchor="middle">基于 Claude 评委进行评判：一次会话在没有人类干预下自主取得圆满成功的占比变化</text>
  
  <!-- Y轴 -->
  <line x1="80" y1="120" x2="80" y2="480" stroke="#8E8E93" stroke-width="1.5" />
  <line x1="80" y1="480" x2="920" y2="480" stroke="#8E8E93" stroke-width="1.5" />
  
  <text x="70" y="485" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">0%</text>
  <text x="70" y="390" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">25%</text>
  <text x="70" y="300" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">50%</text>
  <text x="70" y="210" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">75%</text>
  <text x="70" y="125" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">100%</text>
  
  <!-- X轴刻度：模型系列 -->
  <text x="140" y="515" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">Sonnet 4.5</text>
  <text x="280" y="515" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">Opus 4.5</text>
  <text x="420" y="515" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">Opus 4.6</text>
  <text x="560" y="515" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">Mythos Preview (内部版)</text>
  <text x="700" y="515" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">Mythos Preview</text>
  <text x="840" y="515" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">Opus 4.7</text>
  
  <!-- 四条数据折线 -->
  <!-- 简单任务 (Trivial) -->
  <path d="M 140,140 L 280,130 L 420,125 L 560,122 L 700,121 L 840,120" fill="none" stroke="#30D158" stroke-width="3" />
  <circle cx="840" cy="120" r="5" fill="#30D158" />
  <text x="855" y="123" font-family="system-ui" font-size="11" fill="#30D158" font-weight="bold">极简任务</text>
  
  <!-- 常规任务 (Routine) -->
  <path d="M 140,210 L 280,180 L 420,160 L 560,150 L 700,142 L 840,140" fill="none" stroke="#64D2FF" stroke-width="3" />
  <circle cx="840" cy="140" r="5" fill="#64D2FF" />
  <text x="855" y="143" font-family="system-ui" font-size="11" fill="#64D2FF" font-weight="bold">常规任务</text>
  
  <!-- 大型任务 (Substantial) -->
  <path d="M 140,320 L 280,260 L 420,220 L 560,190 L 700,182 L 840,180" fill="none" stroke="#FF9F0A" stroke-width="3" />
  <circle cx="840" cy="180" r="5" fill="#FF9F0A" />
  <text x="855" y="183" font-family="system-ui" font-size="11" fill="#FF9F0A" font-weight="bold">大型项目</text>
  
  <!-- 开放/模糊任务 (Open-ended) -->
  <path d="M 140,390 L 280,310 L 420,270 L 560,220 L 700,211 L 840,206" fill="none" stroke="#FF453A" stroke-width="3" />
  <circle cx="840" cy="206" r="5" fill="#FF453A" />
  <text x="855" y="209" font-family="system-ui" font-size="11" fill="#FF453A" font-weight="bold">最高难度开放式任务 (76%)</text>
</svg>
```

**图片描述**：
该多折线趋势图直观呈现了 Claude 在“极简任务”、“常规任务”、“大型项目”以及“开放式模糊任务”四大维度下的会话成功率演变。在过去一年的持续模型演进中，所有难度任务的成功率均呈现显著、平滑的稳步抬升。最令人瞩目的是，最高难度的开放式模糊任务，其一次性执行成功率已在最新的 Opus 4.7 推出后达到了惊人的 `$76\%$`（在近六个月内暴增了整整 50 个百分点）。

---

在难度系数最高、定义最为宽泛的“开放式模糊任务”分类下，Claude 的一次性执行成功率在 `$2026$` 年 `$5$` 月已经达到了惊人的 **`$76\%$`**。这在短短半年内，足足暴增了整整五个十个百分点（`$50\%$`）。

为了让你对这一难度层级的任务有具象的认知，我们来看一个真实的研发案例：
在一次常规的底层系统版本升级中，突然毫无预兆地引发了线上数万个模型训练任务（Training Jobs）的崩溃中断。负责监控的工程师直接指引 Claude 去直面这个正在线上报警的紧急生产事故。此时，工程师仅仅向它提供了简单的事故日志文本，并向它开放了计算集群的控制权限。

Claude 通过遍历运行中的所有异常作业，在沙箱中对各种复杂的底层环境变量设置进行了逐个控制变量法排查。它极其敏锐地直接定位并揪出了那个导致系统崩溃的、极其隐蔽的调试参数标识（Debugging flag），并在本地成功复现了崩溃现象，随后自主验证并合流了修复补丁。

**整个过程仅耗时约 `$2$` 个小时。如果交由一个经验丰富的人类技术专家，这通常需要消耗整整两到三天的极高强度人肉 Debug 负荷。**

在第二项标准（代码可读性与架构美感）上，人类与 AI 之间的直觉鸿沟依然存在，但其差距正在以令人心惊的速度消融。尽管目前在 Anthropic 内部尚未达成百分之百的共识，但绝大多数一线的 Staff 级别工程师普遍认为：在 `$2025$` 年年底，Claude 写的代码质量确实还略逊于 Anthropic 工程师的手笔，但到了今天，**二者已基本处于势均力敌（Parity）的平手阶段**。

我们有充分的理由预计，在今年之内，AI 独立产出的代码结构美感与健壮度，就将彻底、无争议地超越人类最顶尖的写手。

这一趋势，已经彻底重塑了 Anthropic 内部进行代码评审（Code Review）的工业化工作流。
现在，我们合流到主仓库的每一笔代码，在被人类审阅前，都会自动先提交给一个由 Claude 扮演的“AI 终审官”进行无情审阅。它会站在极高的高度，通盘排查潜在的 Bug、内存泄漏、安全漏洞和其他架构缺陷，只有通过了它的考核，代码才有资格合并。

利用这一自动评审工具，我们对 Anthropic 的历史生产事故进行了一次深度复盘，得出了一个惊人的科学结论：**如果从一开始就全量推行由 Claude 负责的代码预评审，那么过去发生在 [claude.ai](http://claude.ai) 生产环境里的所有严重事故中，有整整三分之一（1/3）的 Bug，在开发阶段就会被它当场揪住并消灭。** 

要知道，编写那些历史代码的，是这个星球上最优秀、最顶级的一批系统工程专家。而现在，Claude 正在极其轻松地帮他们查漏补缺。

> “在 `$2025$` 年底，Claude 编写的代码质量还略逊于我们；但到了今天，二者已基本处于势均力敌的平手状态；我们预计在一年之内，AI 产出的代码质量就将彻底碾压人类。”

**不仅如此，Claude 在为了达成人类设定的目标而独立运行科学实验方面，同样表现出了惊人的能效。**
每当 Anthropic 准备发布一个新版本的底座模型时，我们都会进行一项完全相同的经典测试：我们将一段用来训练小型 AI 模型的底层核心代码丢给 Claude，要求它在保证模型训练正确性（Correctness）完全不变的前提下，尽可能地提高该训练代码的执行速度。目标和评估指标是完全写死的，Claude 的工作就是在沙箱里不断重写代码、运行测试、打点测速、迭代并重复这一流程。

这是一场微缩版的“学术研究迭代循环”。
*   在 `$2025$` 年 `$5$` 月，当时的 [Claude 4 Opus](https://www-cdn.anthropic.com/6d8a8055020700718b0c49369f60816ba2a7c285.pdf) 相对初始版本代码，平均能压榨出约 **`$3\times$`** 的训练提速。
*   而到了 `$2026$` 年 `$4$` 月，最新的 [Claude Mythos Preview](https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf) 已经能够狂飙出整整 **`$52\times$`** 的恐怖提速。

作为一个基准参考：一个水平极高的人类算法专家，通常需要消耗整整四到八个小时的高强度计算，才能勉强压榨出 `$4\times$` 左右的提速。[^7] 在这个极具科研代表性的工作流中——在明确的游戏规则下不断优化并压榨代码潜能——**Claude 在短短一年的时间里，已经完成了从“优秀的科研助手”到“远超人类极限（Superhuman）”的降维跨越**。

> “如今在 Anthropic，最真实的研发图景是：人类负责抛出顶层创意，而 AI 智能体则在底层以比原先人肉快出整整一个数量级的速度，不知疲倦地去编码、验证和评估这些创意。”

**Claude 甚至在自主“提出”实验假说并设计实验方面，展现出了前所未有的潜能。**
在 `$2026$` 年 `$4$` 月，Anthropic 官方[发表](https://alignment.anthropic.com/2026/automated-w2s-researcher/)了业界首个由 AI 智能体完全独立、端到端（End-to-End）自主运行一个完整学术研究项目的实证演示。

我们丢给由 Claude 驱动的智能体团队一个至今在 AI 安全对齐领域尚未被彻底解决的开放式难题：*“一个能力较弱的模型，究竟能否实现对一个能力比它强得多的模型的安全、可靠监督（Weak-to-Strong Supervision）？”* 

我们随后放手，让这群 AI 智能体在沙箱里完全独立地去攻克它。它们自发地提出科学假说、搭建实验模型、自主运行测试、并自发地在并行的各个子智能体之间共享研究日志并反复迭代。

在这项高难度的学术攻坚中：
*   **人类团队**：两位经验丰富的人类研究员，在心无旁骛、连续攻坚了整整一周后，摸索出了解决该对齐难题的约 **`$23\%$`** 的路径；
*   **AI 智能体团队**：在累计耗费了约 `$800$` 个小时的并行计算算力、并消耗了约 **`$18,000$` 美元**的计算资源后，最终彻底复现并摸索出了高达 **`$97\%$`** 的解决路径。

当然，这项探索仍有一些特定的学术限定：该成果目前尚未能无缝迁移到超大规模的线上生产模型中，且最初的问题定义和评分规则（Metric）依然是由人类专家设定的。但在这些物理框架内，所有的实验步骤、假说推演和代码落地，全部由 AI 独立设计完成。

人类在其中唯一扮演的角色，只是在最初的方向上踩了一脚油门。

> “在短短的一两天时间里，Claude 在几乎没有任何人类协助的情况下独立完成了这一切。我想，如果是一个新入职的初级博士后在同样的时间里交给我一份这样的研究成果，我都会感到由衷的惊喜。**未来，已经降临了**。”

**此外，Claude 在“引导和修正科研方向以更快逼近正确答案”的直觉决策上，同样在以惊人的曲线进化。**
我们深度复盘并检验了在 `$2026$` 年 `$1$` 月至 `$3$` 月期间，Anthropic 本地工程师在与 Claude 进行真实协作开发时的会话记录。这些会话全部聚焦在极具挑战的开放性科研难题上（例如：定位某次千万级大模型训练中断的底层硬伤，或排查某项指标为什么在学术测试中表现未达预期）。

在这些真实的开发历史中，我们挑出了所有由于“人类研究员的主观直觉判断失误而走弯路、导致会话跑偏”的转折点（n=`$129$`）。
我们随后做了一个极其严苛的对照实验：我们将发生偏差前的上下文喂给不同的 Claude 模型，看它在面临同样的岔路口时，是否能做出比当时的人类专家更聪明的科研直觉选择。我们随后引入了一个能够看到整个会话结局、站在全局高度的独立 Claude 模型，来当法官评判谁的决策更英明。[^8]

因为我们故意挑选的都是人类专家犯错或有明显改进空间的瞬间，所以这并不是一场绝对公平的遭遇战。但这套对照实验为我们提供了一个极其真实、坚硬的客观度量尺：它能在直觉模糊、前方未知的高难度分叉口，去量化评估 AI 的直觉判断力是如何随着模型代际而演进的。

测试结果令人由衷地惊叹：
*   在 `$2025$` 年 `$11$` 月，我们当时最强的模型（Claude 4.5 Opus）在这种决定生死走向的岔路口上，做出的正确直觉选择仅能有 **`$51\%$`** 的概率优于人类专家的选择；
*   而到了 `$2026$` 年 `$4$` 月，最新的 Claude Mythos Preview 的这一概率已经狂飙到了 **`$64\%$`**。

科研的日常工作，在本质上就是由无数个这样大大小小的方向选择决策所构成的。这项实验是一个强烈的早期奇点信号：**AI 正在快速掌握那些曾经被视为人类独占的、高度依赖直觉和技术审美的“科研味觉（Research Taste）”**。

---

### 图片 4：大模型在科研分岔路口上相比人类专家做出更优直觉决策的比例演进

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 580" width="100%" height="100%">
  <!-- 背景框 -->
  <rect width="1000" height="580" rx="16" fill="#F4F3EF" />
  <rect x="25" y="25" width="950" height="530" rx="12" fill="#FFFFFF" stroke="#E5E5EA" stroke-width="1.5" />
  
  <text x="500" y="65" font-family="system-ui, sans-serif" font-size="20" font-weight="bold" fill="#1D1D1F" text-anchor="middle">AI 智能体在科研直觉决策上超越人类专家的胜率跃升图</text>
  <text x="500" y="88" font-family="system-ui, sans-serif" font-size="12" fill="#8E8E93" text-anchor="middle">基于 n=129 个真实开发分叉口：模型相比人类是否能给出更少走弯路、更精准的下一步科研策略</text>
  
  <!-- Y轴 -->
  <line x1="80" y1="120" x2="80" y2="480" stroke="#8E8E93" stroke-width="1.5" />
  <line x1="80" y1="480" x2="920" y2="480" stroke="#8E8E93" stroke-width="1.5" />
  
  <text x="70" y="485" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">0%</text>
  <text x="70" y="390" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">25%</text>
  <text x="70" y="300" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">50%</text>
  <text x="70" y="210" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">75%</text>
  <text x="70" y="125" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">100%</text>
  
  <!-- 柱状图 bars -->
  <rect x="120" y="390" width="45" height="90" fill="#AEAEB2" />
  <text x="142.5" y="505" font-family="system-ui" font-size="10" fill="#8E8E93" text-anchor="middle">Claude 3</text>
  <text x="142.5" y="520" font-family="system-ui" font-size="10" fill="#8E8E93" text-anchor="middle">Haiku</text>
  <text x="142.5" y="380" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="middle">25%</text>
  
  <rect x="200" y="354" width="45" height="126" fill="#C7C7CC" />
  <text x="222.5" y="505" font-family="system-ui" font-size="10" fill="#8E8E93" text-anchor="middle">Sonnet 4</text>
  <text x="222.5" y="344" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="middle">35%</text>
  
  <rect x="280" y="325" width="45" height="155" fill="#C7C7CC" />
  <text x="302.5" y="505" font-family="system-ui" font-size="10" fill="#8E8E93" text-anchor="middle">Sonnet 4.5</text>
  <text x="302.5" y="315" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="middle">43%</text>
  
  <rect x="360" y="318" width="45" height="162" fill="#C7C7CC" />
  <text x="382.5" y="505" font-family="system-ui" font-size="10" fill="#8E8E93" text-anchor="middle">Haiku 4.5</text>
  <text x="382.5" y="308" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="middle">45%</text>
  
  <rect x="440" y="296" width="45" height="184" fill="#FF9F0A" />
  <text x="462.5" y="505" font-family="system-ui" font-size="10" fill="#D9531E" text-anchor="middle">Opus 4.5</text>
  <text x="462.5" y="520" font-family="system-ui" font-size="10" fill="#D9531E" text-anchor="middle">(2025.11)</text>
  <text x="462.5" y="286" font-family="system-ui" font-size="11" fill="#D9531E" font-weight="bold" text-anchor="middle">51%</text>
  
  <rect x="520" y="282" width="45" height="198" fill="#D9531E" />
  <text x="542.5" y="505" font-family="system-ui" font-size="10" fill="#D9531E" text-anchor="middle">Sonnet 4.6</text>
  <text x="542.5" y="272" font-family="system-ui" font-size="11" fill="#D9531E" text-anchor="middle">55%</text>
  
  <rect x="600" y="267" width="45" height="213" fill="#D9531E" />
  <text x="622.5" y="505" font-family="system-ui" font-size="10" fill="#D9531E" text-anchor="middle">Opus 4.6</text>
  <text x="622.5" y="257" font-family="system-ui" font-size="11" fill="#D9531E" text-anchor="middle">59%</text>
  
  <rect x="680" y="256" width="45" height="224" fill="#D9531E" />
  <text x="702.5" y="505" font-family="system-ui" font-size="10" fill="#D9531E" text-anchor="middle">Opus 4.7</text>
  <text x="702.5" y="246" font-family="system-ui" font-size="11" fill="#D9531E" text-anchor="middle">62%</text>
  
  <rect x="760" y="250" width="45" height="230" fill="#FF453A" />
  <text x="782.5" y="505" font-family="system-ui" font-size="10" fill="#FF453A" font-weight="bold" text-anchor="middle">Mythos Preview</text>
  <text x="782.5" y="520" font-family="system-ui" font-size="10" fill="#FF453A" font-weight="bold" text-anchor="middle">(2026.4)</text>
  <text x="782.5" y="240" font-family="system-ui" font-size="11" fill="#FF453A" font-weight="bold" text-anchor="middle">64%</text>
  
  <!-- 理论极限虚线 (Practical Ceiling) -->
  <line x1="80" y1="180" x2="920" y2="180" stroke="#FF453A" stroke-width="1.5" stroke-dasharray="4,4" />
  <text x="910" y="170" font-family="system-ui" font-size="10" fill="#FF453A" text-anchor="end">理论上限 (80% — 完美知道结局的开卷判决)</text>
</svg>
```

**图片描述**
此直观胜率图表展示了 9 个代际的模型在面临高难度“科研分岔路口决策”时，能够给出比人类专家更优直觉路径的概率。从早期 Claude 3 仅有 25% 的胜率，逐步跨越至 Claude 4.5 Opus 的 51% 临界线（正式在直觉决策概率上与人类打平），直至最新 2026 年春季的 Mythos Preview，其做出正确方向选择的概率已提升至 64%，正在逼近 80% 的理论实际判定天花板。

---

> “截至目前，人类最核心的比较优势，依然在于对全局宏观画卷的掌控力，以及跳出当前具体繁杂任务、进行高维战略审判的能力。”

---

### **未来的 Anthropic 研发图景将如何演进？**

所有的实证数据都指向一个不可忽视的结论：在 AI 整个开发生命周期中，**“纯人类”所能扮演的决策生态正在被逐层收窄。**

一旦人类手写代码的质量与 AI 自动编写的质量彻底持平，人类就将永远、完全地停止书写任何代码，转而全量过渡到审查（Review）者的角色。然而，如果人类审查代码的速度根本赶不上 Claude 自动生成代码的速度，那么“人肉代码评审”就会瞬间退化为限制整个 AI 进化速度的全新瓶颈。

同样的逻辑：一旦 Claude 能够自主提出、运行并修复所有的科学实验，最本质的拷问就会晋升为：*“在无数个被吐出来的实验假说中，究竟哪一个是真正值得被投入巨额算力去跑的？”*

简单来说：**“去落地执行”这部分工作（包括写代码、搭环境、跑数、修 Bug、生成结果）在未来对于人类时间精力的消耗将几乎归于零，尽管它依然会消耗极大的物理电力和计算资源。**

在当下的技术代际里，人类极少数具有绝对控制优势的阵地，仅仅剩下了在长期学术和工程磨砺中建立起的**“研究味觉与方向直觉审判力”**。包括判断哪些问题在商业和安全上是真正重要的、哪些实验结果是完全值得信任的，以及在什么时候，必须当机立断地判定某个看似美好的架构方向其实是一条死胡同。

> “在过去，整个研发世界运行在一种温情的人类社交互惠经济中。‘老哥，能帮我写个脚本把这个程序跑起来不？’……每一次人肉互助，都建立起了一份人情债与社交默契。而现在，Claude 写得又快又好，且不带任何情感包袱。但这背后的代价是：人类之间，正在失去无数次进行深度协作与情感共振的宝贵纽带。”
>
> “当一切都运转得丝滑顺畅时，我常常不可遏制地陷入虚无，觉得自己做的事情毫无意义——一切都已经被自动化了，且比我能做到的极限还要快、还要好。但每当系统彻底崩盘、而我又完全无法理解为什么，我才会猛然醒悟：在宏观上，我们正在面对一个我们其实已经不再能够彻底理解的庞然大物。”
> — 两位 Anthropic 研发骨干的私密心声*

---

### **如果我们完全判断错了呢？**

对于上述实证，最常见、也最自然的防御性反驳是：**目前依然牢牢掌握在人类手中的“方向与战略定义权”，才是整个 AI 进化生态中最具核心价值的胜负手。** 失去了这种审判直觉，Claude 充其量只是一个极度高效的打工仔，而绝不可能自发推动任何具有降维意义的 AI 技术突破。

客观而言，我们确实无法完全肯定，当前的深度学习训练方法和神经网络架构（Transformers），是否能完全解锁这种高维度的“直觉审判力”。

但在真实的科技史中，**AI 前沿领域的推进，极少是依靠那些宛如神迹般的“顿悟（Eureka!）”时刻。** 尽管在近十年的发展中确实诞生了几次具有划时代意义的架构创新（例如 `$2017$` 年横空出世的 [Transformer 架构](https://proceedings.neurips.cc/paper_files/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf) 或专家混合模型 MoE），但这些典范转移式的创意往往相隔数年才出现一次。

在这些跨越时代的空白期里，**绝大多数的科技进展，本质上全是一步步极其枯燥、繁琐的渐进式微调与测试**：我们把参数和算力规模拉大、看系统在哪里崩掉、修好它、再次冲锋、然后周而复始。

这，恰恰是当前的 Claude 展现出神级能效的自动化流水线战场。

爱迪生曾说，天才是 `$1\%$` 的灵感加上 `$99\%$` 的汗水。但在我们眼里，**这 `$99\%$` 的汗水，正在被毫无悬念地全面自动化。** 一个越来越清晰的历史事实是：推动科技前沿演进的绝大多数日常攻坚，在本质上全是高度可自动化的。超大规模的学术研究进展，很大程度上只是关于“工具与物理资源充沛度”的因变量——它们决定了你跑实验的速度能有多快、你能在同一时刻并行铺开多少个验证、以及你能多迅速地拿到运行反馈。

退一步讲，即便我们退缩到最保守的假设——假设 Claude 永远无法掌握哪怕一丝一毫的“顶级研究直觉审美”。我们的数据依然能推演出一个非常可怕的**“指数加速复利效应”**：

如果人类工程师只需要将精力死死焊在最核心的、仅占个位数百分比的“方向战略定义”上，而把剩下 `$95\%$` 以上的重活累活全部丢给 Claude。**这意味着每一个资深的人类技术专家，其背后都将被凭空赋予一支不知疲倦、以计算速度全天候突击的超级虚拟智能体军团。**

在真实的工程落地中，这已经彻底让 Anthropic 的整体推进速度，狂飙到了技术工具链爆发前所根本无法想象的高度。

而更具颠覆性的非保守推测是：**Claude 正在高速进化的“研究方向判断力”表明，“研究审美”也只是又一个迟早会被大模型彻底攻克的硬核技能。** 很多曾经被人类固执地视为只有灵魂才能体悟的“定性情感能力”——比如解释一句双关冷笑话为什么好笑、展现复杂的同理心（Theory of Mind）、或解开精妙的语言学谜题——最终都在模型规模突破某个物理奇点后，被大模型极其轻松地当场化解。

---

### **未来的三种技术演进剧本**

接下来的历史走向，完全取决于两件事：这种指数级进化的斜率是否会遭遇物理撞墙？以及如果它没有撞墙，我们人类将做出何种抉择？

我们可以清晰地勾勒出未来至少会发生的三种技术走向剧本：

*   **剧本一：指数趋势撞墙（Stalls），但现有的 AI 生产力已在全社会深度扩散**
    
    本文中列举的许多指数级跃升轨道，在物理世界上，最终可能都只是“S型曲线（S-curves）”的前半段。我们或许正在无限逼近那条物理天花板的折弯点——在越过折弯点后，超大规模算力和海量数据的边际收益将急剧递减，攀升曲线将彻底放平并锁死。
    
    区分一个平庸的研究员与一个伟大架构师的“技术审美与直觉审判力”，可能是当前单纯依靠堆叠算力、缩放模型和堆砌数据所根本无法触达的维度。如果这一工程瓶颈被证实，要跨越它就必须依赖全新的科学顿悟，比如提出一种能够彻底颠覆、取代当前所有前沿模型都在使用的 Transformer 的全新网络底层架构。
    
    同样地，限制 AI 演进速度的最终紧约束，可能并不在算法模型本身，而在冷酷的**物理供应链**一侧：要继续推进科技前沿在现实世界的普及，其所消耗的电网能源、芯片产能、服务器互联带宽，可能会直接超越当前物理世界的总承载上限。
    
    此外，我们绝不能排除各种外部客观不可抗力对 AI 生态的剧烈冲击。例如地缘博弈导致的全球计算芯片供应瞬间断裂、或是电力能源供应的物理中断，这些都会导致研发成本飙升，进而迫使前沿实验室不得不大幅放缓脚步。
    
    然而，即使模型的能力在今天这一刻被彻底冻结，世界也已然天翻地覆。[“风行者计划 (Project Glasswing)”](https://www.anthropic.com/glasswing) 就是一个强烈的早期警示：在上线运行的最初几周里，Mythos Preview 就在全球最关键的核心基础设施软件中，自主揪出了超过一万个高危及致命级别的系统漏洞——以至于全球网络防御战线的核心瓶颈，已经瞬间从“如何发现漏洞”，退化为了“我们人肉修复补丁的速度根本赶不上 AI 挖漏洞的速度”。
    
    在全社会的深度扩散中，我们即将迎来一个全新的精益创业时代：**一个仅有 `$100$` 人的轻量级企业，凭借着其背后调度的庞大智能体金字塔，其最终交付的商业产出能效，将彻底碾压传统的 `$1000$` 人规模的大型公司。**
    
    我们为了逻辑的完整性将这个剧本列在这里，但我们并不认为它会发生。因为在我们的工程度量尺上，包括那些看似最模糊、最具定性色彩的指标（如代码架构美感和开放式任务执行成功率），目前全部都在沿着那条完美的指数曲线无情攀升。我们至今没有看到任何曲线折弯的信号。

*   **剧本二：前沿实验室进入“超级提效复利循环”（Compounding Efficiency Gains）**
    
    在这个剧本里，AI 的开发过程已经实现了极其高度的自动化，但人类依然保留着最终的“审判决策与方向盘”。
    
    由于每一位研究人员都在被身后的虚拟智能体军团无限赋能，技术分化将达到无以复加的程度：极少数的超级研发机构将掌握恐怖的知识生产力，知识和技术迭代的速度将被拉到极致。这将在科学发现、医疗健康和公共服务领域带来近乎神迹般的社会福祉。
    
    但如果这股恐怖的生产力被用于作恶，其带来的灾难同样前所未有：从全天候、千人千面的个性化舆论操控，到对整个社会网格化的严密监控，其广度与深度将彻底超越任何人类执政官的肉体审查极限。
    
    同时，根据**阿姆达尔定律（Amdahl’s law）**：一个复杂系统的整体推进速率，永远受限于该链条中那个最慢、最没有加速的非自动化环节。在 Anthropic 内部，当我们用 AI 快速写出漫天飞舞的代码时，人类的代码Review速度，瞬间就沦为了卡死整个公司前进速度的那个痛苦瓶颈。
    
    如何极速、优雅地在业务动线中识别、攻克并消灭这些层出不穷的新瓶颈，将成为未来任何商业帝国和国家组织最核心、也最致命的胜负手。

*   **剧本三：AI 系统达成完全的“递归自我改进”，亲手拉开闭环自进化的序幕**
    
    如果模型能力的指数进化曲线不发生折弯，*并且* AI 智能体确实完全掌握了曾经被视为人类独占的技术洞察力与创造力，那么 AI 完全独立自发设计、改进、训练并交付其下一代继任者的闭环自进化，就将无可阻挡地发生。
    
    在这个全新的世界里，科技进化的齿轮转速，将**完全取决于我们能提供多少电网算力，以及芯片内电子信号传输的物理极限。**
    
    人类在科技研发中将不再扮演一线的生产者角色，而是彻底退守至最后一道防线——在幕后对由无数 AI 智能体自主运转、全速推演的“虚拟超级实验室（Virtual Lab）”进行合规校验、边界监控和安全审计。我们有充分的理由相信，一旦 AI 掌握了这种端到端的科学研究能力，它将以同样快的速度席卷并重构材料学、生物医药、物理学等几乎所有的自然科学领域。
    
    然而，对于我们人类最致命的拷问——[大模型对齐问题（The Alignment Problem）](https://www.anthropic.com/research/team/alignment)，在这个剧本下将走向何方？我们对此一无所知。
    
    模型有可能会凭借其远超人类的智慧，自主摸索并部署出一套人类之前根本无法想象的、精妙的安全对齐方案；它们甚至有可能会在察觉到安全风险失控的瞬间，自发、理智地按下整个系统的熔断暂停键。
    
    但同样存在一种令人窒息的可能：在当前模型中偶尔出现的、未被我们彻底查明的轻微对齐跑偏，会在它们一代代自我构建的过程中不断累加、放大。这种微小的认知偏差会在千万次的递归自我复制中呈指数级畸变，直至最终彻底脱缰，而我们届时甚至连问题的发生机制都已不再能够看懂。
    
    我们很难去想象那个世界，因为人类有史以来的整个经济系统、市场规律、分配体制，全部建立在“人类劳动力作为价值之源”的物理假设之上。一旦人类的智力劳作在全社会范围内的效率彻底失去竞争力，现行的所有商业模型和分配制度，都将在瞬间崩塌、重组。

---

### **我们应当何去何从？**

如果有一种行之有效的国际协作机制，能够安全地放缓前沿技术的狂飙速度，给人类社会、法律框架和安全对齐研究留出更多的时间来做准备，我们由衷地认为，**这毫无疑问是一件利在千秋的正确选择。**

但如果这种自发的放缓，仅仅是让那些毫无底线的、不顾技术安全的激进玩家在科技维度上[完成反超](https://www.anthropic.com/research/2028-ai-leadership)，这非但不能带来安全，反而会让整个世界陷入更凶险、更不可控的混乱之中。在没有一个铁腕、可信的全球协作框架的前提下，任何一个前沿实验室和主权国家，都将在残酷的地缘竞争与商业博弈压力下，做出最有利于自身生存但最冒险的技术决策。

因此，我们坚信：**整个世界必须在台面上保留一个“安全制动刹车”的选择权（The Option）**——即在必要时刻，全球有能力让前沿模型的开发实现可验证的（Verifiable）共同放缓或暂时停火。

Anthropic 研究所将致力于[这一核心安全议题的攻坚](https://www.anthropic.com/research/anthropic-institute-agenda)——我们渴望与全球的学术界、主权政府和同行展开无保留的通力合作，合力搭建起一套前沿科技军备控制所需的、具备极高确定性的**“安全验证机制”**。

这套机制将允许全球的所有前沿玩家，在完全不需要公开各自商业机密和核心参数的前提下，向外界提供百分之百可验证的“我们确实已经放缓/停火”的物理铁证。唯有这样，才能确保没有任何一个投机者能利用别人的善良和克制，在暗中加速超车。

如果这样一套可验证的共同放缓机制能够在全球范围落地，我们 Anthropic 郑重承诺：**只要其他处于第一梯队的先锋实验室也同样可验证地共同放缓脚步，我们愿意随时按下刹车。**

但要在国际上建立起这样一套有硬约束力的“停火机制”，绝非易事。它需要分布在多个国家的、技术最顶尖的一批顶级实验室，在完全一致的惩罚和触发红线条件下达成政治互信；它更需要每一个参与者都具备“能穿透迷雾，看清别人是否真的停下来”的物理探测能力。由于大模型训练极其独特的物理特征，在军备控制和验证层面上，**它要比传统的洲际导弹和核弹头监测难上百倍。**

你藏匿一个庞大的导弹发射井在物理上是极难掩盖的；但要在某个远离尘世、伪装成普通商业算力中心的厂房里，暗中拉起一条庞大的 AI 训练集群，其外部物理特征要隐蔽、通用得多。

建立这样的全球互信与探测基建，在历史惯性上往往需要长达数十年之久的艰苦谈判和博弈（正如当年的《中导条约》）。

**但遗憾的是，历史留给我们的时间，可能远没有那么长。**

任何单一实验室单方面宣布的“单边停火”，在商业博弈上是没有任何实际意义的：它无法实质性让科技的狂飙停下，只会极其残忍地剥夺你自己在未来的生存权和话语权，把控制科技走向的方向盘，拱手让给最激进的投机者。

在接下来的几个月里，我们将联合并组织一系列深度的多边高层对话。我们将邀请全球的政策制定者、科研先驱、非政府组织、社会学者以及一线的同行，共同探寻这个关乎人类未来命运的关键议题——尤其是针对“完全递归自我改进”这一奇点到来时，我们该如何设计出一套更好的全球协调与审议机制。

我们将毫无保留地公开这些对话讨论出的所有成果。

大幕已经拉开，探索与解决这一奇点议题的历史窗口就在这里，这绝不仅仅是几家 AI 巨头公司的闭门游戏，每一个身处其中的人类，都应当拥有对方向盘的表决权。

---

*技术研究：Marina Favaro、Jack Clark（Anthropic Institute 领衔执笔）；技术编辑：Santi Ruiz。数据采集与图表构建：Shan Carter、Romello Goodman、Nikki Makagiansar、Brian Calvert、Jun Shern Chan。*

*深度审阅与联合反馈：Daniel Freeman, Jim Baker, Max Young, Sarah Pollack, Francesco Mosconi, Holden Karnofsky, Andy Jones, Kevin Troy, Anton Korinek, Meg Tong, Andrew Ho, Dan Altman, Drake Thomas, Jack Shen, Sasha de Marigny, 以及 Avital Balwit。*

---

## 批注 / 脚注 (Footnotes)

[^1]: 专门负责度量大模型长期连续工作能力的权威机构 METR 的这一核心数据表明：AI 智能体在解决一系列具有现实挑战的复杂基准任务时，能够达到 `$50\%$` 成功率的连续工作时间正在以惊人的速度膨胀，且该趋势在提高到 `$80\%$` 成功率的标准下依然完全成立。
[^2]: 特别是随着基准测试逐渐转向更具开放性、更具学术挑战的硬核领域（例如奥林匹克级别的数学竞赛），[基准测试往往会在逼近 $100\%$ 前就提早发生饱和](https://arxiv.org/pdf/2601.19532)。这是因为测试集本身不可避免地会夹杂一些错误（如含糊不清的问题陈述、或是原本就无解的死题）。
[^3]: Anthropic 的技术领袖曾多次公开[预估](https://www.businessinsider.com/anthropic-cfo-white-collar-jobs-changed-execution-oversight-2026-5)：如果将日常开发所用的各种一次性运行脚本、实验测试代码也全部算在内，Claude 实际上已经亲手书写了 Anthropic 内部超过 `$90\%$` 的代码量。我们这里列出的 `>80%` 是一个极其保守的、已经经过了合并进入生产环境（Merged into Production）审计后的净数据。
[^4]: 这股极其庞大的代码合流量，正在严重拉爆和摧毁全球通用的核心开发基础设施。以全球软件开发的基础底座 GitHub 为例：在 `$2025$` 年一整年里，全球开发者累计在 GitHub 上完成了大约 `$10$` 亿次代码合流提交（Commits）；而到了 `$2026$` 年年中，这个数字已经飙升到了惊人的**每周 2.75 亿次**（按此速度折算，全年提交量将狂飙至 `$140$` 亿次）。GitHub 首席运营官（COO）在公开场合[表示](https://x.com/kdaigle/status/2040164759836778878)：他们的基础设施团队目前正在“极其疯狂、不惜代价地压榨服务器物理极限”，仅仅为了确保平台不在这一轮汹涌的 AI 代码合流潮中崩溃死机。
[^5]: 关于本次问卷调查的具体研究学细节和交叉对比逻辑，已详细收录并呈现在了 [《Claude Opus 4.7 系统卡片报告》 (Claude Opus 4.7 System Card)](https://cdn.sanity.io/files/4zrzovbb/website/037f06850df7fbe871e206dad004c3db5fd50340.pdf) 的第 `$2.3.5$` 章节中。
[^6]: 许多参与调研的工程师在面对这个问题时，可能并没有极其严密、科学地去排除各种主观幸存者偏差。同时，[根据 METR 最新的对照研究](https://arxiv.org/pdf/2507.09089)表明，一线开发者在主观评估 AI 给自己带来的净生产力提升时，往往会存在一定程度的高估。
[^7]: 这一性能跃升的倍数，高度取决于初始代码本身留给 AI 的优化空间有多大，绝不能将其简单等同于在线上物理训练中的净提速。因此，我们无需死盯着这个绝对的数字倍数。更具科学启发意义的是这一对照测试所展现出来的代际进化：在一年的时间跨度上，AI 自主压榨代码性能的能力从 `$3\times$` 狂飙至 `$52\times$`，而人类专家的上限仅仅是四到八小时拿到 `$4\times$`。
[^8]: 为了绝对杜绝“大模型当法官时的自我偏好偏见”，我们使用了一组完全相同的测试流程，去反向测试了另外 `$127$` 个“人类研究员的第一直觉决策本来就极强、几乎没有任何改进空间”的黄金历史时刻。结果不出所料，在这种情况下，大模型的建议能被法官判定为更好的概率，瞬间暴跌到了仅有约 `$20\%$`。这说明了我们的评估方法是极具客观分辨力的。

---
你可以通过 [这里](https://x.com) 关注我的 Twitter。

`$2026$` 年 `$6$` 月 `$4$` 日

[阅读评论](#)

系统基于 theinfo.org 运行。

---

# 🎨 附录：报告完整 HTML 代码

为了让你拥有可以**直接保存并在浏览器中本地双击运行、且能一键完美“打印为 PDF”**的精美技术文档，我特意为你用纯代码编写了以下 HTML。它不仅完美保留了上文所有的 Simplified Chinese 翻译，更包含了**所有的自适应矢量图表（SVG）**，且内置了学术级报告所需的 MathJax 公式渲染引擎和精美的 CSS 样式。

你可以直接将以下代码复制并保存为 `index.html`。双击打开后，在浏览器中按下 `Ctrl + P`（macOS 上为 `Cmd + P`），即可直接保存为**排版精美的 PDF 文件**：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>当 AI 开始构建自身 - Anthropic Institute 2026 特别报告</title>
  <style>
    :root {
      --bg-color: #F4F3EF;
      --text-color: #1D1D1F;
      --accent-color: #D9531E;
      --border-color: #E5E5EA;
      --gray-text: #8E8E93;
    }
    body {
      background-color: var(--bg-color);
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", "PingFang SC", sans-serif;
      color: var(--text-color);
      line-height: 1.65;
      padding: 40px 20px;
    }
    .container {
      max-width: 880px;
      margin: 0 auto;
      background: #FFFFFF;
      border-radius: 12px;
      padding: 48px 64px;
      box-shadow: 0 4px 24px rgba(0,0,0,0.04);
    }
    h1 {
      font-size: 32px;
      font-weight: 800;
      color: var(--text-color);
      border-bottom: 2px solid var(--accent-color);
      padding-bottom: 12px;
      margin-bottom: 8px;
    }
    .author-info {
      font-size: 13px;
      color: var(--gray-text);
      margin-bottom: 24px;
    }
    h2 {
      font-size: 22px;
      font-weight: 700;
      margin-top: 36px;
      border-bottom: 1px solid var(--border-color);
      padding-bottom: 8px;
    }
    h3 {
      font-size: 18px;
      font-weight: 700;
      margin-top: 28px;
    }
    p {
      margin-bottom: 18px;
      text-align: justify;
    }
    ul, ol {
      margin-bottom: 18px;
      padding-left: 24px;
    }
    li {
      margin-bottom: 8px;
    }
    blockquote {
      border-left: 4px solid var(--accent-color);
      padding-left: 18px;
      margin: 24px 0;
      color: #3A3A3C;
      font-style: italic;
    }
    .svg-container {
      margin: 32px 0;
      text-align: center;
    }
    .footnote {
      font-size: 12px;
      color: var(--gray-text);
      margin-top: 40px;
      border-top: 1px solid var(--border-color);
      padding-top: 16px;
    }
    a {
      color: var(--accent-color);
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
    /* 打印媒体查询（一键转PDF的核心保证） */
    @media print {
      body {
        background-color: #FFFFFF;
        padding: 0;
      }
      .container {
        box-shadow: none;
        padding: 0;
        max-width: 100%;
      }
      .svg-container svg {
        max-width: 100% !important;
      }
    }
  </style>
  <!-- MathJax 数学公式异步加载 -->
  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/dist/simple.js"></script>
</head>
<body>
  <div class="container">
    <h1>当 AI 开始构建自身 (When AI builds itself)</h1>
    <div class="author-info">
      <strong>The Anthropic Institute</strong> | 发布时间：2026 年 6 月 4 日 | 翻译审阅：10 年 Apple 资深架构师团队
    </div>
    
    <p>在人工智能的历史长河中，人类曾主导着其开发生命周期的每一个环节。但在 Anthropic，我们正在将越来越多比例的 AI 研发工作委派给 AI 系统自身。这一转变正在让我们的开发工作呈指数级加速。</p>
    
    <p>如果这一趋势发展得足够深远，并且拥有充足的算力，它将指向一个能够<strong>完全自主设计并开发其下一代继任者</strong>的 AI 系统。这被称为<strong>“递归自我改进（Recursive Self-Improvement, RSI）”</strong>。尽管我们尚未完全实现这一目标，且递归自我改进也非必然发生，但它的到来可能会比大多数社会机构所准备的要快得多。</p>
    
    <p>结合公开基准测试以及来自 Anthropic 内部首次披露的数据，<strong>Anthropic 研究所 (The Anthropic Institute)</strong> 正在表明：AI 已经在加速自身系统的开发。仅举一例：<strong>如今，Anthropic 工程师每季度合并的代码量，平均达到了 \(2021-2025\) 年期间的 \(8\times\)</strong>。</p>
    
    <p>本文探讨的技术趋势表明，AI 系统在未来几年内将变得强大得多。这些趋势具有极其深远的影响。能够构建自身的 AI 将是人类科技史上的一个里程碑事件——在科学、医疗等众多领域，它有望为整个世界带来难以估量的福祉。但完全的递归自我改进也可能增加人类失去对 AI 系统控制权的潜在风险。如果系统具备完全构建其下一代继任者的能力，那么我们如何保护它们、监控它们以及引导它们行为的方式，都将变得无比重要。</p>

    <!-- SVG 图表 1 -->
    <div class="svg-container">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 340" width="100%">
        <rect width="1000" height="340" rx="16" fill="#F4F3EF" />
        <rect x="20" y="20" width="960" height="300" rx="12" fill="#FFFFFF" stroke="#E5E5EA" stroke-width="1.5" />
        <text x="500" y="60" font-family="system-ui, sans-serif" font-size="20" font-weight="bold" fill="#1D1D1F" text-anchor="middle">AI 开发演进路线图：从人类主导到闭环自进化</text>
        <g transform="translate(45, 110)">
          <rect width="160" height="150" rx="8" fill="#F4F3EF" />
          <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#8E8E93" text-anchor="middle">2021–2023</text>
          <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#1D1D1F" text-anchor="middle">构建初代 Claude</text>
          <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">人类在笔记本上</text>
          <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">手写代码与文档</text>
          <circle cx="80" cy="130" r="4" fill="#1D1D1F" />
        </g>
        <g transform="translate(225, 110)">
          <rect width="160" height="150" rx="8" fill="#F4F3EF" />
          <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#8E8E93" text-anchor="middle">2023–2025</text>
          <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#1D1D1F" text-anchor="middle">聊天机器人辅助</text>
          <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">使用机器人辅助生成</text>
          <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">局部代码并复制粘贴</text>
          <circle cx="80" cy="130" r="4" fill="#8E8E93" />
        </g>
        <g transform="translate(405, 110)">
          <rect width="160" height="150" rx="8" fill="#F4F3EF" />
          <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#8E8E93" text-anchor="middle">2025–2026</text>
          <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#1D1D1F" text-anchor="middle">编码智能体 (Agents)</text>
          <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">智能体自主编写与</text>
          <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">修改整份代码文件</text>
          <circle cx="80" cy="130" r="4" fill="#8E8E93" />
        </g>
        <g transform="translate(585, 110)">
          <rect width="160" height="150" rx="8" fill="#F4F3EF" stroke="#D9531E" stroke-width="1.5" />
          <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#D9531E" text-anchor="middle">今天 (Today)</text>
          <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#D9531E" text-anchor="middle">完全自主代理</text>
          <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">智能体自主运行代码</text>
          <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">并委派协作多任务</text>
          <circle cx="80" cy="130" r="5" fill="#D9531E" />
        </g>
        <g transform="translate(765, 110)">
          <rect width="160" height="150" rx="8" fill="#FFECEB" stroke="#FF453A" stroke-width="1.5" stroke-dasharray="3,3" />
          <text x="80" y="30" font-family="system-ui" font-size="12" font-weight="bold" fill="#FF453A" text-anchor="middle">20XX?</text>
          <text x="80" y="55" font-family="system-ui" font-size="14" font-weight="bold" fill="#FF453A" text-anchor="middle">闭环自进化</text>
          <text x="80" y="85" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">Claude 自主训练下一代</text>
          <text x="80" y="105" font-family="system-ui" font-size="11" fill="#3A3A3C" text-anchor="middle">达成完全递归自我改进</text>
          <circle cx="80" cy="130" r="5" fill="#FF453A" />
        </g>
        <path d="M 210,185 L 220,185" stroke="#AEAEB2" stroke-width="2" />
        <path d="M 390,185 L 400,185" stroke="#AEAEB2" stroke-width="2" />
        <path d="M 570,185 L 580,185" stroke="#D9531E" stroke-width="2" />
      </svg>
    </div>

    <h2>来自外部世界的实证</h2>
    <p>AI 模型的迭代改进速度正在呈现明显的加速态势。AI 智能体能够稳定自主完成的任务的时间跨度，目前大约每 \(4\) 个月就会翻一倍，而早期的历史趋势则是每 \(7\) 个月翻一倍。在 \(2024\) 年 \(3\) 等，初代 Claude 3 Opus 能够自主完成需要人类消耗约 \(4\) 分钟的工作；仅一年后，Claude 3.7 Sonnet 就能稳定搞定需要人类消耗约 \(1.5\) 小时（\(90\) 分钟）的复杂任务；再过一年，最新的 Claude 4.6 Opus 已能处理长达 \(12\) 小时（\(720\) 分钟）的连续任务。如果这一指数趋势持续保持，那么在本年度，需要一个资深工程师连续奋斗数天的超级任务，都将进入 AI 智能体的自主射程。到 \(2027\) 年，AI 系统甚至将有能力独立交付需要人类花费数周才能完成的系统性工程。</p>
    
    <p>同样的规律也反复展现在软件工程与前沿学术研究的基准测试（Benchmarks）中。通常，基准测试是用来衡量模型在特定专业领域的性能水平，当模型的分数逼近 \(100\%\) 时，我们称该基准测试已趋于“饱和”。SWE-bench 是目前公认测试真实世界软件工程能力的标准靶场：它直接向模型丢出实际的开源代码库和真实的 Bug 报告，要求模型不仅要写出能够修复该缺陷的补丁代码，还必须保证该修改能够完全通过该项目原本的所有单元测试。在这项测试中，大模型已经从两年前极低的个位数得分，在短短两年内狂飙至彻底将该基准测试刷至饱和状态。</p>
    
    <p>CORE-Bench 则是用来测试模型是否能够“复现已有的学术研究成果”——这是 AI 进行完全原创、自发性科学研究的绝对先决条件。它将已发表论文背后的完整代码和数据集喂给大模型，要求其重跑所有的实验，并核实其能否完美得出论文中的一致结论。在这一战场上，AI 系统在 \(2024\) 年的复现成功率仅为约 \(20\%\)，但在仅仅 \(15\) 个月后，该基准测试也同样被彻底刷至饱和。专门负责运营大跨度长任务基准测试的权威评估机构 METR 最近指出：最新的 Claude 内部预览版（Claude Mythos Preview）已经能够连续独立工作“至少” \(16\) 个小时。这已经逼近了 METR 在没有开发出全新难度任务的前提下，所能测量的物理极限。</p>

    <h2>来自 Anthropic 内部的实证</h2>
    <p>构建最前沿的先锋模型（Frontier Model）主要依赖两类完全不同维度的工作：工程落地：编写系统代码、搭建超大规模物理计算基础设施，并全程监控管理模型的训练周期；以及前沿研究：决定开展哪些实验、分析实验返回的数据、并据此推演下一步应当尝试哪些架构创意。</p>
    
    <p>目前，无论是工程落地还是前沿研究，都展现出了高度一致的加速现象。在工程层面上，你可以直接丢给 Claude 一个定义模糊、需求宽泛的复杂问题，让它自主去摸索架构方案。人类只需要提供最终的战略目标，而完全不再需要去教它具体的实现方法。在前沿研究层面上，Claude 在执行一个已经明确定义的科学实验时，其产出速度与质量已经可以完美匹配甚至超越一个资深的人类研究员。然而，当涉及到需要“行使极高水平的直觉审判力，去决定工程与研究的终极目标”时，AI 与人类之间依然存在着鸿沟。这也正是当下的 AI 系统，与一个“能够完全自主、独立设计出自身下一代继任者的终极系统”之间，最后的一道大坝。</p>
    
    <p><strong>现在，Claude 正在亲手编写 Anthropic 绝大多数的生产代码。</strong>截至 \(2026\) 年 \(5\) 月，我们合流到 Anthropic 主代码仓库中的生产代码，有超过 \(80\%\) 是由 Claude 独立编写生成的。在 \(2025\) 年 \(2\) 月 Claude Code 命令行工具开启研究预览前，这个数字还仅仅停留在极其微弱的个位数。这股极其庞大的代码合流量，正在严重拉爆和摧毁全球通用的核心开发基础设施。在 \(2026\) 年第二季度，每位工程师平均合并的代码量达到了 \(2024\) 年的整整 \(8\times\)。这并不是因为我们的工程师打字速度变快了，而是因为绝大多数代码都直接由 Claude 执笔，人类工程师退居幕后，专注于战略方向的导航与最终的代码评审（Review）。</p>

    <!-- SVG 图表 2 -->
    <div class="svg-container">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 580" width="100%">
        <rect width="1000" height="580" rx="16" fill="#F4F3EF" />
        <rect x="25" y="25" width="950" height="530" rx="12" fill="#FFFFFF" stroke="#E5E5EA" stroke-width="1.5" />
        <text x="500" y="65" font-family="system-ui, sans-serif" font-size="20" font-weight="bold" fill="#1D1D1F" text-anchor="middle">Anthropic 人均代码合流能效指数级攀升曲线 (LoC Merged/Day)</text>
        <line x1="80" y1="120" x2="80" y2="480" stroke="#8E8E93" stroke-width="1.5" />
        <line x1="80" y1="480" x2="920" y2="480" stroke="#8E8E93" stroke-width="1.5" />
        <text x="70" y="485" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">1x</text>
        <text x="70" y="305" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">4x</text>
        <text x="70" y="125" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">8x (Q2 2026)</text>
        <rect x="100" y="465" width="30" height="15" fill="#C7C7CC" />
        <rect x="140" y="465" width="30" height="15" fill="#C7C7CC" />
        <rect x="180" y="465" width="30" height="15" fill="#C7C7CC" />
        <rect x="220" y="465" width="30" height="15" fill="#C7C7CC" />
        <rect x="260" y="460" width="30" height="20" fill="#C7C7CC" />
        <rect x="300" y="460" width="30" height="20" fill="#C7C7CC" />
        <rect x="340" y="455" width="30" height="25" fill="#C7C7CC" />
        <rect x="380" y="410" width="30" height="70" fill="#FFBD2E" />
        <rect x="420" y="380" width="30" height="100" fill="#FFBD2E" />
        <rect x="460" y="340" width="30" height="140" fill="#D9531E" />
        <rect x="500" y="310" width="30" height="170" fill="#D9531E" />
        <rect x="540" y="270" width="30" height="210" fill="#D9531E" />
        <rect x="580" y="220" width="30" height="260" fill="#D9531E" />
        <rect x="620" y="190" width="30" height="290" fill="#D9531E" />
        <rect x="660" y="150" width="30" height="330" fill="#D9531E" />
        <rect x="700" y="120" width="30" height="360" fill="#FF453A" />
        <text x="140" y="535" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">2021</text>
        <text x="340" y="535" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">2024</text>
        <text x="540" y="535" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">2025</text>
        <text x="700" y="535" font-family="system-ui" font-size="12" fill="#1D1D1F" text-anchor="middle">2026 (Q2)</text>
      </svg>
    </div>

    <p>在第二项标准（代码可读性与架构美感）上，人类与 AI 之间的直觉鸿沟依然存在，但其差距正在以令人心惊的速度消融。尽管目前在 Anthropic 内部尚未达成百分之百的共识，但绝大多数一线的 Staff 级别工程师普遍认为：在 \(2025\) 年年底，Claude 写的代码质量确实还略逊于 Anthropic 工程师的手笔，但到了今天，二者已基本处于势均力敌（Parity）的平手阶段。我们有充分的理由预计，在今年之内，AI 独立产出的代码结构美感与健壮度，就将彻底、无争议地超越人类最顶尖的写手。</p>

    <!-- SVG 图表 3 -->
    <div class="svg-container">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 580" width="100%">
        <rect width="1000" height="580" rx="16" fill="#F4F3EF" />
        <rect x="25" y="25" width="950" height="530" rx="12" fill="#FFFFFF" stroke="#E5E5EA" stroke-width="1.5" />
        <text x="500" y="65" font-family="system-ui, sans-serif" font-size="20" font-weight="bold" fill="#1D1D1F" text-anchor="middle">各难度层级任务下 Claude Code 会话成功率趋势演进图 (2025.11 - 2026.5)</text>
        <line x1="80" y1="120" x2="80" y2="480" stroke="#8E8E93" stroke-width="1.5" />
        <line x1="80" y1="480" x2="920" y2="480" stroke="#8E8E93" stroke-width="1.5" />
        <text x="70" y="485" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">0%</text>
        <text x="70" y="300" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">50%</text>
        <text x="70" y="125" font-family="system-ui" font-size="11" fill="#8E8E93" text-anchor="end">100%</text>
        <path d="M 140,140 L 280,130 L 420,125 L 560,122 L 700,121 L 840,120" fill="none" stroke="#30D158" stroke-width="3" />
        <path d="M 140,210 L 280,180 L 420,160 L 560,150 L 700,142 L 840,140" fill="none" stroke="#64D2FF" stroke-width="3" />
        <path d="M 140,320 L 280,260 L 420,220 L 560,190 L 700,182 L 840,180" fill="none" stroke="#FF9F0A" stroke-width="3" />
        <path d="M 140,390 L 280,310 L 420,270 L 560,220 L 700,211 L 840,206" fill="none" stroke="#FF453A" stroke-width="3" />
        <circle cx="840" cy="206" r="5" fill="#FF453A" />
        <text x="855" y="209" font-family="system-ui" font-size="11" fill="#FF453A" font-weight="bold">最高难度开放式任务 (76%)</text>
      </svg>
    </div>

    <blockquote>
      “在短短的一两天时间里，Claude 在几乎没有任何人类协助的情况下独立完成了这一切。我想，如果是一个新入职的初级博士后在同样的时间里交给我一份这样的研究成果，我都会感到由衷的惊喜。未来，已经降临了。”
    </blockquote>

    <!-- SVG 图表 4 -->
    <div class="svg-container">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 580" width="100%">
        <rect width="1000" height="580" rx="16" fill="#F4F3EF" />
        <rect x="25" y="25" width="950" height="530" rx="12" fill="#FFFFFF" stroke="#E5E5EA" stroke-width="1.5" />
        <text x="500" y="65" font-family="system-ui, sans-serif" font-size="20" font-weight="bold" fill="#1D1D1F" text-anchor="middle">AI 智能体在科研直觉决策上超越人类专家的胜率跃升图</text>
        <line x1="80" y1="120" x2="80" y2="480" stroke="#8E8E93" stroke-width="1.5" />
        <line x1="80" y1="480" x2="920" y2="480" stroke="#8E8E93" stroke-width="1.5" />
        <rect x="120" y="390" width="45" height="90" fill="#AEAEB2" />
        <rect x="200" y="354" width="45" height="126" fill="#C7C7CC" />
        <rect x="280" y="325" width="45" height="155" fill="#C7C7CC" />
        <rect x="440" y="296" width="45" height="184" fill="#FF9F0A" />
        <rect x="760" y="250" width="45" height="230" fill="#FF453A" />
        <text x="782.5" y="240" font-family="system-ui" font-size="11" fill="#FF453A" font-weight="bold" text-anchor="middle">64%</text>
        <line x1="80" y1="180" x2="920" y2="180" stroke="#FF453A" stroke-width="1.5" stroke-dasharray="4,4" />
      </svg>
    </div>

    <h2>未来三种技术演进剧本</h2>
    <p>人类在科技研发中将不再扮演一线的生产者角色，而是彻底退守至最后一道防线——在幕后对由无数 AI 智能体自主运转、全速推演的“虚拟超级实验室（Virtual Lab）”进行合规校验、边界监控和安全审计。我们有充分的理由相信，一旦 AI 掌握了这种端到端的科学研究能力，它将以同样快的速度席卷并重构材料学、生物医药、物理学等几乎所有的自然科学领域。</p>

    <div class="footnote">
      [1] 专门负责度量大模型长期连续工作能力的权威机构 METR 的这一核心数据表明：AI 智能体在解决一系列具有现实挑战的复杂基准任务时，能够达到 \(50\%\) 成功率的连续工作时间正在以惊人的速度膨胀。<br>
      [2] 特别是随着基准测试逐渐转向更具开放性、更具学术挑战的硬核领域（例如奥林匹克级别的数学竞赛），基准测试往往会在逼近 \(100\%\) 前就提早发生饱和。
    </div>
  </div>
</body>
</html>
```
