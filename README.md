# Awesome RSI

> 递归自我改进（Recursive Self-Improvement, RSI）与自进化智能体研究阅读路线图。

本清单整理了 138 项代表性论文、博客与项目，覆盖理论、Agent Harness、模型权重、训练、数据、评价、环境、联合改进、自动化 AI 研发及评测边界。

> [!NOTE]
> **⭐ 先读** 是各路线的推荐入口。同一研究的论文、博客和项目页合并在同一项，不重复计数。

## 目录

- [00 定义、综述与理论](#00-定义综述与理论)
- [01 Harness：提示词、记忆、技能、工作流与自身代码](#01-harness提示词记忆技能工作流与自身代码)
- [02 模型权重：自训练、自纠错与测试时学习](#02-模型权重自训练自纠错与测试时学习)
- [03 训练调参：超参数、架构、优化器与损失函数](#03-训练调参超参数架构优化器与损失函数)
- [04 数据与课程：自己出题，决定接下来学什么](#04-数据与课程自己出题决定接下来学什么)
- [05 评价与奖励：自己打分，也改进打分方式](#05-评价与奖励自己打分也改进打分方式)
- [06 自博弈与环境：让对手、关卡和模拟经验也变化](#06-自博弈与环境让对手关卡和模拟经验也变化)
- [07 联合改进：把多个循环连接起来](#07-联合改进把多个循环连接起来)
- [08 自动化 AI 研发：让 AI 参与设计下一代 AI](#08-自动化-ai-研发让-ai-参与设计下一代-ai)
- [09 评测与边界：怎样判断它是真的变强](#09-评测与边界怎样判断它是真的变强)

## 00 定义、综述与理论

先用第 1 项建立分类，再用第 2、3 项对照。综述中的分级和定义属于作者提出的框架，并非统一行业标准。

1. [The Path to Recursive Self-Improving Agents: Foundation, Framework, and Future Directions](https://self-improving-agent.com/) (2026) — **⭐ 先读**  
   从模型、harness、数据、训练器和改进机制五个对象理解自我改进。 [GitHub](https://github.com/D2I-ai/awesome-recursive-self-improving-agents)  
2. [Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops](https://arxiv.org/abs/2607.07663) (2026) — **⭐ 先读**  
   按“改什么”和“循环闭合到什么程度”组织文献。  
3. [Self-Improvements in Modern Agentic Systems: A Survey](https://arxiv.org/abs/2607.13104) (2026)  
   梳理模型参数与外部运行框架如何从经验中持续更新。 [项目页](https://selfimproving-agent.github.io/)  
4. [A Survey of Self-Evolving Agents: What, When, How, and Where to Evolve on the Path to Artificial Super Intelligence](https://arxiv.org/abs/2507.21046) (2025)  
   按演化对象、时机、方式和应用场景阅读 Agent 自演化研究。  
5. [A Comprehensive Survey of Self-Evolving AI Agents: A New Paradigm Bridging Foundation Models and Lifelong Agentic Systems](https://arxiv.org/abs/2508.07407) (2025)  
   补充终身学习、自演化 Agent 的机制与应用脉络。  
6. [Gödel Machines: Self-Referential Universal Problem Solvers Making Provably Optimal Self-Improvements](https://arxiv.org/abs/cs/0309048) (2003 起)  
   可证明自我修改的理论源头。  
7. [The Last AI Built by Humans: Toward Genuine Recursive Self-Improvement](https://arxiv.org/abs/2609.11873) (2026)  
   讨论执行、策略、经验获取、环境适应和元改进的自主性。  
8. [Recursive Self-Improvement in Physical AI: Mechanisms, Evidence, and Evaluation](https://arxiv.org/abs/2610.38266) (2026)  
   梳理具身系统如何更新策略、世界模型与技能，并用四级框架区分任务内适应、持久提升与改进器本身的提升。  

## 01 Harness：提示词、记忆、技能、工作流与自身代码

Harness 是包在模型外面的运行系统，这一类通常不更新底座模型权重。建议先读 DGM → GEPA → ReasoningBank → ADAS。

### A. 自身代码与在线运行框架

9. [Darwin Gödel Machine (DGM)](https://arxiv.org/abs/2505.22954) (2025) — **⭐ 先读**  
   Agent 修改自身实现，通过实测筛选，并从保存的版本继续探索。 [项目页](https://sakana.ai/dgm/)  
10. [SICA — A Self-Improving Coding Agent](https://arxiv.org/abs/2504.15228) (2025)  
    编程 Agent 检查并编辑自身实现，用评测反馈改进性能与效率。  
11. [Gödel Agent: A Self-Referential Agent Framework for Recursive Self-Improvement](https://arxiv.org/abs/2410.04444) (2024)  
    在目标和反馈约束下自主修改自身代码与逻辑。  
12. [Self-Taught Optimizer (STOP): Recursively Self-Improving Code Generation](https://arxiv.org/abs/2310.02304) (2023)  
    让负责优化程序的改进器优化自身。  
13. [Hyperagents](https://arxiv.org/abs/2603.19461) (2026) — **⭐ 先读**  
    把任务 Agent 与元 Agent 放进可修改系统。  
14. [Huxley-Gödel Machine (HGM)](https://arxiv.org/abs/2510.21614) (2025)  
    区分当前任务分数与后代质量，用后代表现指导自修改搜索。  
15. [Meta-Harness: End-to-End Optimization of Model Harnesses](https://arxiv.org/abs/2603.28052) (2026)  
    外层 Agent 读取历史代码、评分和执行轨迹，搜索更好的 harness。  
16. [Live-SWE-agent](https://arxiv.org/abs/2511.13646) (2025)  
    在软件工程任务中在线调整执行框架，重点看任务内适应。  
17. [Continual Harness](https://arxiv.org/abs/2605.09998) (2026)  
    在持续交互中更新提示、技能、记忆与子 Agent。  
18. [Prime Agent](https://www.primeintellect.ai/blog/prime-agent) (2026)  
    可修改 harness 用于实际编程 Agent 的官方工程解读。  
19. [ModularRSI: Modular and Generalizable Recursive Harness Self-Improvement](https://arxiv.org/abs/2609.14857) (2026)  
    对比同一任务的成功与失败轨迹，分别改进五个 harness 模块，再用与演化任务分离的基准检验迁移。  
20. [RRSI: Regularized Recursive Self-Improvement of Agent Harnesses](https://arxiv.org/abs/2609.24972) (2026)  
    限制每轮候选改动的规模，筛除针对基准的特化和高成本改动，再用分布外任务检验迁移。  
21. [SelfSearch: Reward-Free Search for Self-Improving Agents](https://arxiv.org/abs/2609.37968) (2026)  
    让 Agent 依据以往自修改的记录提出新版本，搜索阶段不使用下游任务奖励。  
22. [Harness²: Recursive Agent Harnessing for an Open World](https://arxiv.org/abs/2610.14224) (2026)  
    先在当前任务中验证并调整执行框架，再把这些改动的经验用于更新负责后续适应的框架。  

### B. 提示词与上下文

23. [APE — Large Language Models Are Human-Level Prompt Engineers](https://arxiv.org/abs/2211.01910) (2022)  
    模型生成候选指令，再按任务得分选择。  
24. [OPRO — Large Language Models as Optimizers](https://arxiv.org/abs/2309.03409) (2023)  
    把历史候选和分数交给模型，提出下一轮更好的提示或解。  
25. [DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines](https://arxiv.org/abs/2310.03714) (2023)  
    将模型调用写成模块，再按评价指标优化提示与示例。 [项目页](https://dspy.ai/)  
26. [MIPRO — Optimizing Instructions and Demonstrations for Multi-Stage Language Model Programs](https://arxiv.org/abs/2406.11695) (2024)  
    联合优化多阶段流程中的指令和少样本示例。  
27. [TextGrad: Automatic “Differentiation” via Text](https://arxiv.org/abs/2406.07496) (2024)  
    把自然语言批评作为优化信号，沿计算图改进多个组件。  
28. [metaTextGrad: Automatically Optimizing Language Model Optimizers](https://arxiv.org/abs/2505.18524) (2025)  
    从“优化任务”走向“优化优化器”。  
29. [Promptbreeder: Self-Referential Self-Improvement Via Prompt Evolution](https://arxiv.org/abs/2309.16797) (2023) — **⭐ 先读**  
    同时演化任务提示和用于产生新提示的变异提示。  
30. [GEPA: Reflective Prompt Evolution Can Outperform Reinforcement Learning](https://arxiv.org/abs/2507.19457) (2025) — **⭐ 先读**  
    根据执行轨迹反思并演化提示。 [GitHub](https://github.com/gepa-ai/gepa)  
31. [ACE — Agentic Context Engineering](https://arxiv.org/abs/2510.04618) (2025)  
    把上下文当作可积累、更新和整理的经验手册。  
32. [SpecForge: Recursive Self-Improvement for Coding Agents via Behavioral Specifications](https://arxiv.org/abs/2610.15708) (2026)  
    用代码测试失败的反馈修订自然语言行为规范，再让编程 Agent 按新版规范生成代码。  

### C. 记忆与经验

33. [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366) (2023) — **⭐ 先读**  
    把失败转化成文字反思，供后续尝试使用；不更新模型权重。  
34. [ExpeL: LLM Agents Are Experiential Learners](https://arxiv.org/abs/2308.10144) (2023)  
    从任务经历中提炼通用经验，在新任务中检索和使用。  
35. [Dynamic Cheatsheet: Test-Time Learning with Adaptive Memory](https://arxiv.org/abs/2504.07952) (2025)  
    维护精简的策略、代码片段与解题经验，在推理时复用。  
36. [ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory](https://arxiv.org/abs/2509.25140) (2025) — **⭐ 先读**  
    从自评的成功和失败经历中提炼推理策略。 [解读](https://research.google/blog/reasoningbank-enabling-agents-to-learn-from-experience/)  
37. [A-MEM: Agentic Memory for LLM Agents](https://arxiv.org/abs/2502.12110) (2025)  
    动态组织、关联和更新记忆条目。  
38. [MemEvolve: Meta-Evolution of Agent Memory Systems](https://arxiv.org/abs/2512.18746) (2025)  
    搜索记忆系统的编码、存储、检索和管理方式。  
39. [Memento 3: Model-Based Recursive Self-Improvement through Reflective Rulebooks](https://arxiv.org/abs/2610.11794) (2026)  
    把交互经验写入可修订的规则手册，编译成可执行世界模型，并回放已观测的状态转移以验证更新。  
40. [Reglos: A Self-Evolving Personal Memory Agent with Recursive Self-Improvement](https://arxiv.org/abs/2611.06049) (2026)  
    随对话更新个人记忆，从失败轨迹提出 harness 补丁，再由另一模型家族的评审筛查针对基准的改动。  

### D. 工具与技能

41. [Voyager: An Open-Ended Embodied Agent with Large Language Models](https://arxiv.org/abs/2305.16291) (2023) — **⭐ 先读**  
    在 Minecraft 中探索并积累可执行代码技能。 [项目页](https://voyager.minedojo.org/)  
42. [LATM — Large Language Models as Tool Makers](https://arxiv.org/abs/2305.17126) (2023)  
    模型生成可复用工具，再由工具使用者调用。  
43. [SkillWeaver: Web Agents Can Self-Improve by Discovering and Honing Skills](https://arxiv.org/abs/2504.07079) (2025)  
    通过网页探索、练习和反馈，把操作沉淀成可复用 API。  
44. [MetaSkill-Evolve: Recursive Self-Improvement of LLM Agents via Two-Timescale Meta-Skill Evolution](https://arxiv.org/abs/2607.05297) (2026)  
    用快循环改进任务技能，用慢循环改进负责修订技能的元技能。  
45. [Skill∞: Recursive Self-Improvement for Agent Skill Optimization](https://arxiv.org/abs/2610.35434) (2026)  
    将技能优化步骤写成可修改的元技能，用同一流程更新任务技能和元技能，并检验跨任务复用。  

### E. 工作流与多 Agent

46. [ADAS — Automated Design of Agentic Systems](https://arxiv.org/abs/2408.08435) (2024) — **⭐ 先读**  
    元 Agent 编写、测试和搜索新的 Agent 设计。  
47. [AFlow: Automating Agentic Workflow Generation](https://arxiv.org/abs/2410.10762) (2024)  
    搜索模型调用、检查与任务分解等工作流结构。  
48. [EvoFlow: Evolving Diverse Agentic Workflows On The Fly](https://arxiv.org/abs/2502.07373) (2025)  
    通过检索、交叉、变异和选择演化工作流种群。  
49. [EvoAgentX: An Automated Framework for Evolving Agentic Workflows](https://arxiv.org/abs/2507.03616) (2025)  
    整合工作流生成、运行、评价和多种优化算法。  
50. [RSIFlow: Adaptive Self-Improvement Workflows with an Evolving Meta-Agent](https://arxiv.org/abs/2610.21791) (2026)  
    元 Agent 根据轨迹选择针对能力瓶颈的改进流程，再把执行结果沉淀为技能，改进后续流程编排。  

## 02 模型权重：自训练、自纠错与测试时学习

这一类真正更新模型参数。建议先读 STaR → ReST-EM → SEAL → TTRL。

51. [STaR: Bootstrapping Reasoning With Reasoning](https://arxiv.org/abs/2203.14465) (2022) — **⭐ 先读**  
    生成推理过程，筛选正确样本，再用于下一轮训练。  
52. [Reinforced Self-Training (ReST) for Language Modeling](https://arxiv.org/abs/2308.08998) (2023)  
    反复生成样本并用奖励反馈改进策略。  
53. [ReST-EM — Beyond Human Data: Scaling Self-Training for Problem-Solving with Language Models](https://arxiv.org/abs/2312.06585) (2023) — **⭐ 先读**  
    用可验证反馈筛选自生成解，再训练并重复。  
54. [SPIN — Self-Play Fine-Tuning Converts Weak Language Models to Strong Language Models](https://arxiv.org/abs/2401.01335) (2024)  
    让模型与上一轮输出进行自博弈微调。  
55. [RISE — Recursive Introspection: Teaching Language Model Agents How to Self-Improve](https://arxiv.org/abs/2407.18219) (2024)  
    根据先前尝试与反馈进行多轮修正。  
56. [SCoRe — Training Language Models to Self-Correct via Reinforcement Learning](https://arxiv.org/abs/2409.12917) (2024)  
    用多轮在线强化学习改善自纠错。  
57. [SEAL — Self-Adapting Language Models](https://arxiv.org/abs/2506.10943) (2025) — **⭐ 先读**  
    模型生成用于更新自身的数据与更新指令。 [项目页](https://jyopari.github.io/posts/seal)  
58. [TTRL — Test-Time Reinforcement Learning](https://arxiv.org/abs/2504.16084) (2025) — **⭐ 先读**  
    在没有真实标签的测试数据上估计奖励并更新参数。  
59. [SDFT — Self-Distillation Enables Continual Learning](https://arxiv.org/abs/2601.19897) (2026)  
    让带示例上下文的模型充当自己的教师。  
60. [RLTLDR: Self-improvement by Internalizing Self-generated Feedback](https://arxiv.org/abs/2609.37633) (2026)  
    从验证器反馈中提炼简短经验，用它指导下一次尝试，再把生成经验的能力内化到模型权重。  
61. [CARE: Grounded Recursive Self-Improvement for Production Customer-Service Agents](https://arxiv.org/abs/2611.02839) (2026)  
    从线上失败中定位模型错误，用核验后的修复做在策略自蒸馏，再经模拟测试、线上对照和人工审批筛选下一版本。  

## 03 训练调参：超参数、架构、优化器与损失函数

建议先读 autoresearch → PBT → DiscoPOP，再读元学习与算法发现。

62. [autoresearch](https://github.com/karpathy/autoresearch) (2026) — **⭐ 先读**  
    Agent 改训练代码、运行限时实验、比较结果并保留有效改动。  
63. [Population Based Training of Neural Networks (PBT)](https://arxiv.org/abs/1711.09846) (2017) — **⭐ 先读**  
    在训练中联合更新模型与超参数日程。  
64. [Neural Architecture Search with Reinforcement Learning](https://arxiv.org/abs/1611.01578) (2016)  
    用控制器生成网络结构、训练和评价候选。  
65. [Learning to Learn by Gradient Descent by Gradient Descent](https://arxiv.org/abs/1606.04474) (2016)  
    把优化器本身变成可学习的模型。  
66. [VeLO: Training Versatile Learned Optimizers by Scaling Up](https://arxiv.org/abs/2211.09760) (2022)  
    训练可用于不同任务的学习型优化器。  
67. [Lion — Symbolic Discovery of Optimization Algorithms](https://arxiv.org/abs/2302.06675) (2023)  
    通过程序搜索发现优化算法。  
68. [AutoML-Zero: Evolving Machine Learning Algorithms From Scratch](https://arxiv.org/abs/2003.03384) (2020)  
    从基础数学运算演化学习算法。  
69. [DiscoPOP — Discovering Preference Optimization Algorithms with and for Large Language Models](https://arxiv.org/abs/2406.08414) (2024) — **⭐ 先读**  
    模型提出并实现偏好优化损失，继续搜索更好的损失函数。  
70. [Eliminating Meta Optimization Through Self-Referential Meta Learning](https://arxiv.org/abs/2212.14392) (2022)  
    研究能修改自身学习行为的自指元学习系统。  
71. [RSI-Opt: Recursive Self-Improvement Optimizer Agents For Model Training](https://arxiv.org/abs/2610.32026) (2026)  
    用 Agent 在训练中调整优化设置，再由元 Agent 根据多轮实验修订其提示、操作手册与优化器代码库。  

## 04 数据与课程：自己出题，决定接下来学什么

先读 Self-Instruct，再读 Absolute Zero → R-Zero → Agent0。“零数据”通常指特定后训练阶段。

72. [Self-Instruct: Aligning Language Models with Self-Generated Instructions](https://arxiv.org/abs/2212.10560) (2022) — **⭐ 先读**  
    从少量种子任务生成、过滤指令数据，再用于训练。  
73. [WizardLM / Evol-Instruct](https://arxiv.org/abs/2304.12244) (2023)  
    逐步把已有指令改写得更复杂，再用生成数据训练模型。  
74. [Absolute Zero: Reinforced Self-Play Reasoning with Zero Data](https://arxiv.org/abs/2505.03335) (2025) — **⭐ 先读**  
    模型自己提出和解决代码任务，由执行器提供反馈。  
75. [Self-Challenging Language Model Agents](https://arxiv.org/abs/2506.01716) (2025)  
    构造带验证函数的任务，用挑战者和执行者形成循环。  
76. [R-Zero: Self-Evolving Reasoning LLM from Zero Data](https://arxiv.org/abs/2508.05004) (2025) — **⭐ 先读**  
    出题者与解题者共同演化。  
77. [Agent0: Unleashing Self-Evolving Agents from Zero Data via Tool-Integrated Reasoning](https://arxiv.org/abs/2511.16043) (2025)  
    课程 Agent 与执行 Agent 共同演化。  
78. [Self-Play Pretraining with Zero Data](https://arxiv.org/abs/2609.30063) (2026)  
    从随机初始化开始，让生成器用程序合成字节序列，并随学习器的进步调整预训练课程，作为概念验证。  
79. [Questioning the Questions: Sustaining Self-Evolution in Reasoning Models](https://arxiv.org/abs/2610.04299) (2026)  
    用题目有效性与数学新颖性反馈调整出题奖励和训练数据，缓解多轮自训练中的无效题与重复题。  

## 05 评价与奖励：自己打分，也改进打分方式

先读 Self-Rewarding → Self-Taught Evaluators → rStar-Math，再读 RQGM。

80. [Constitutional AI: Harmlessness from AI Feedback](https://arxiv.org/abs/2212.08073) (2022)  
    依据人为原则，让 AI 生成批评、修改与偏好反馈。  
81. [Self-Rewarding Language Models](https://arxiv.org/abs/2401.10020) (2024) — **⭐ 先读**  
    模型同时生成并评价回答，通过迭代偏好优化共同提升。  
82. [Self-Taught Evaluators](https://arxiv.org/abs/2408.02666) (2024) — **⭐ 先读**  
    从未标注指令与合成对比回答出发训练评价模型。  
83. [ReST-MCTS*: LLM Self-Training via Process Reward Guided Tree Search](https://arxiv.org/abs/2406.03816) (2024)  
    用树搜索与过程奖励生成训练轨迹。  
84. [rStar-Math: Small LLMs Can Master Math Reasoning with Self-Evolved Deep Thinking](https://arxiv.org/abs/2501.04519) (2025) — **⭐ 先读**  
    推理策略与过程偏好模型迭代共同训练。  
85. [Eureka: Human-Level Reward Design via Coding Large Language Models](https://arxiv.org/abs/2310.12931) (2023)  
    模型编写奖励函数，查看训练反馈，再修改奖励代码。 [项目页](https://eureka-research.github.io/)  
86. [The Red Queen Gödel Machine: Co-Evolving Agents and Their Evaluators (RQGM)](https://arxiv.org/abs/2606.26294) (2026)  
    让 Agent 与评价过程共同演化。  
87. [RecurSE: Bounded Recursive Self-Evaluation for LLM Rubric Judges](https://arxiv.org/abs/2608.24231) (2026)  
    用同步更新的模型副本检查裁判的评分依据，把检查结果作为训练奖励，并用验证指标决定何时停止。  
88. [RewardWeaver: Long-Horizon Interactive Learning for Language Agents via Self-Evolving Reward Adaptation](https://arxiv.org/abs/2610.10120) (2026)  
    从失败轨迹归因当前策略的能力瓶颈，为下一轮训练选择对应的过程奖励。  

## 06 自博弈与环境：让对手、关卡和模拟经验也变化

先读 AlphaZero → POET → EnvGen。环境演化和固定算法下的自博弈属于相关基础，并非天然具备元递归能力。

89. [AlphaZero — Mastering Chess and Shogi by Self-Play with a General Reinforcement Learning Algorithm](https://arxiv.org/abs/1712.01815) (2017) — **⭐ 先读**  
    通过与自身对弈不断生成学习信号。  
90. [POET — Paired Open-Ended Trailblazer](https://arxiv.org/abs/1901.01753) (2019) — **⭐ 先读**  
    同时生成学习环境和对应解决方案。  
91. [Enhanced POET](https://arxiv.org/abs/2003.08536) (2020)  
    扩展开放式环境与策略共同演化。  
92. [ACCEL — Evolving Curricula with Regret-Based Environment Design](https://arxiv.org/abs/2203.01302) (2022)  
    逐步编辑关卡，让课程保持在 Agent 能力边界附近。  
93. [EnvGen: Generating and Adapting Environments via LLMs for Training Embodied Agents](https://arxiv.org/abs/2403.12014) (2024) — **⭐ 先读**  
    根据 Agent 薄弱能力，让大模型调整训练环境。  
94. [DreamGym — Scaling Agent Learning via Experience Synthesis](https://arxiv.org/abs/2511.03773) (2025)  
    用经验模型合成状态转移与反馈，自适应生成训练任务。  
95. [SPIRAL: Self-Play on Zero-Sum Games Incentivizes Reasoning via Multi-Agent Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2506.24119) (2025)  
    与不断变强的自身版本博弈，形成对手驱动课程。  
96. [SPADE: Self-Play in Adaptive Synthetic Executable Environments](https://arxiv.org/abs/2608.19197) (2026)  
    让同一模型扮演环境设计者与学习者，编写可执行训练环境，再依据有无提示时的奖励差调整环境难度。  
97. [Dream-RSI: Recursive Self-Improvement through Evolving Worlds](https://arxiv.org/abs/2609.14858) (2026)  
    用历史搜索树构造回放模拟器，低成本评估并改进探索策略，再让新版策略扩充后续搜索记录。  

## 07 联合改进：把多个循环连接起来

先读 BetterTogether → SkillRL，再看多模态和 MetaRSI。

98. [BetterTogether — Fine-Tuning and Prompt Optimization: Two Great Steps that Work Better Together](https://arxiv.org/abs/2407.10930) (2024) — **⭐ 先读**  
    交替优化提示词和模型权重。  
99. [SkillRL: Evolving Agents via Recursive Skill-Augmented Reinforcement Learning](https://arxiv.org/abs/2602.08234) (2026) — **⭐ 先读**  
    让技能库与 Agent 策略在强化学习中共同演化。  
100. [Agent0-VL: Exploring Self-Evolving Agent for Tool-Integrated Vision-Language Reasoning](https://arxiv.org/abs/2511.19900) (2025)  
     视觉语言模型同时承担解题与验证角色。  
101. [VLAW: Iterative Co-Improvement of Vision-Language-Action Policy and World Model](https://arxiv.org/abs/2602.12063) (2026)  
     真实交互改进世界模型，再用模拟数据改进机器人策略。  
102. [RLAnything: Forge Environment, Policy, and Reward Model in Completely Dynamic RL System](https://arxiv.org/abs/2602.02488) (2026)  
     联合更新环境、策略和奖励模型。  
103. [MetaRSI / RSI2: A Meta-Recursive Self-Improving System for Recursive Self-Improving Systems Themselves](https://arxiv.org/abs/2609.06396) (2026)  
     探索数据、harness 与模型更新的组合及元调度。  
104. [Recursive Self-Improvement through Multi-Agent Self-Supervision](https://arxiv.org/abs/2610.12176) (2026)  
     交替演化多 Agent 工作流并用自产轨迹微调模型，让更新后的模型参与下一轮工作流设计与自评。  
105. [Drafting Agents, Not Just Tokens: Speculative Recursive Self-Improvement for Agentic Systems](https://arxiv.org/abs/2610.16491) (2026)  
     内循环提前提出候选 Agent，并在完整验证后采纳。外循环用已完成的搜索训练改进器，评价器保持固定。  
106. [AdaRSI: On-Demand Recursive Self-Improvement for Embodied Agents](https://arxiv.org/abs/2610.20474) (2026)  
     先修订机器人技能与 harness，再通过回放定位仍然失败的动作步骤，用自主采集的示范做针对性微调。  
107. [Self-Evolving Coding Agents via Harness-Policy Optimization](https://arxiv.org/abs/2610.22791) (2026)  
     交替搜索编程 harness 与更新策略权重，再让新版策略根据自身失败提出下一轮 harness 改动。  
108. [The Trinity: Capability-Driven Recursive Self-Improvement for Multimodal Agents](https://arxiv.org/abs/2610.36077) (2026)  
     围绕跨任务共用的能力生成可验证的模拟环境，从执行轨迹演化可复用的 harness 模块，再在未见任务上检验迁移。  
109. [RSI-Env: An Open-Ended Environment for Recursive Self-Improvement of Agents](https://arxiv.org/abs/2611.01736) (2026)  
     在持久环境中联合更新模型与 harness，由独立控制器管理评测和版本，通过验收的版本接管下一轮改进。  

## 08 自动化 AI 研发：让 AI 参与设计下一代 AI

先读 AIDE → AlphaEvolve → Frontis-MA1。自动完成实验或论文不直接证明新系统已接管并增强下一轮研发。

110. [AIDE: AI-Driven Exploration in the Space of Code](https://arxiv.org/abs/2502.13138) (2025) — **⭐ 先读**  
     把机器学习工程表示成代码空间中的树搜索。  
111. [The AI Scientist: Towards Fully Automated Open-Ended Scientific Discovery](https://arxiv.org/abs/2408.06292) (2024)  
     覆盖研究想法、实验、分析和论文写作。 [项目页](https://sakana.ai/ai-scientist/)  
112. [The AI Scientist-v2: Workshop-Level Automated Scientific Discovery via Agentic Tree Search](https://arxiv.org/abs/2504.08066) (2025)  
     通过实验管理与树搜索扩展自动科研流程。  
113. [AlphaEvolve: A Coding Agent for Scientific and Algorithmic Discovery](https://arxiv.org/abs/2506.13131) (2025) — **⭐ 先读**  
     代码生成、自动评价与演化搜索结合。 [介绍](https://deepmind.google/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms/) · [影响](https://deepmind.google/blog/alphaevolve-impact/)  
114. [ASI-Evolve: AI Accelerates AI](https://arxiv.org/abs/2603.29640) (2026)  
     把数据、架构与学习算法探索放入自动化实验循环。  
115. [Frontis-MA1 / OpenMLE](https://arxiv.org/abs/2607.28568) (2026) — **⭐ 先读**  
     结合可验证机器学习环境、研究操作训练和长时程搜索。  
116. [Accelerating Scientific Discovery with Co-Scientist](https://arxiv.org/abs/2502.18864) (2025)  
     多 Agent 生成、辩论和改进科学假设。  
117. [Recursive self-improvement of AI research agents](https://arxiv.org/abs/2609.26457) (2026)  
     AIDE² 改写自身代码，用隐藏评测筛选改动，再由获选版本继续自修改，并用留出任务检验迁移。  
118. [Training LLM Agents to Automate LLM Post-Training with RSI-Dojo](https://arxiv.org/abs/2611.03698) (2026)  
     把论文、数据和指标转成可执行的后训练任务，用筛选后的实验轨迹训练能选数据、跑实验和诊断失败的 Agent。  

## 09 评测与边界：怎样判断它是真的变强

先读 PAST-Bench 和 S3Gym，再读反例。能力更强、经验有效、改进器更强，是三个不同的评价问题。

119. [PAST-Bench: Benchmarking the Foundations of Recursive Self-Improvement in Personal Agents](https://arxiv.org/abs/2608.04003) (2026) — **⭐ 先读**  
     检查经验是否通过保存、检索和更新改善后续表现。  
120. [S3Gym: Can LLMs Turn Self-Testing and Self-Judging into Self-Improvement?](https://arxiv.org/abs/2608.31100) (2026) — **⭐ 先读**  
     分开探索与保留测试，对比三条经验利用路径。  
121. [Large Language Models Cannot Self-Correct Reasoning Yet](https://arxiv.org/abs/2310.01798) (2023)  
     分析缺少外部反馈时的自纠错失败。  
122. [Large Language Model Agents Are Not Always Faithful Self-Evolvers](https://arxiv.org/abs/2601.22436) (2026)  
     用因果干预检查 Agent 是否真的依赖积累经验。  
123. [AI Models Collapse When Trained on Recursively Generated Data](https://www.nature.com/articles/s41586-024-07566-y) (2024)  
     研究递归生成数据造成分布退化的条件与机制。  
124. [MLE-bench: Evaluating Machine Learning Agents on Machine Learning Engineering](https://arxiv.org/abs/2410.07095) (2024)  
     评价模型选择、数据处理和训练等机器学习工程能力。  
125. [RE-Bench: Evaluating Frontier AI R&D Capabilities of Language Model Agents against Human Experts](https://arxiv.org/abs/2411.15114) (2024)  
     用开放式研究工程任务与人类专家对照。  
126. [PaperBench: Evaluating AI's Ability to Replicate AI Research](https://arxiv.org/abs/2504.01848) (2025)  
     评价理解并复现 AI 论文的能力。  
127. [LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory](https://arxiv.org/abs/2410.10813) (2024)  
     评价长期交互中的记忆能力。  
128. [MemoryAgentBench — Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://arxiv.org/abs/2507.05257) (2025)  
     检查多轮交互下的信息记忆、更新与使用。  
129. [Self-Refine: Iterative Refinement with Self-Feedback](https://arxiv.org/abs/2303.17651) (2023)  
     一次任务内反复修改输出，不等于系统发生持久改进。  
130. [Recursive Language Models](https://arxiv.org/abs/2512.24601) (2025)  
     这里的 recursive 是计算结构，不能据此归入 RSI 成果。  
131. [AI4AI-Bench: Benchmarking LLM Agents in Algorithmic Design for Recursive Self-Improvement](https://arxiv.org/abs/2608.20318) (2026)  
     让 Agent 改写十类训练算法，再由独立流程从头训练，用固定的隐藏评测比较收益。  
132. [SEABench: Benchmarking Endogenous Misalignment In Self-Evolving Agents](https://arxiv.org/abs/2609.35596) (2026)  
     用长程任务与不演化的对照组，检查局部有用的 harness 更新是否在后续任务中引发安全问题。  
133. [Auditing the Product, Not the Recursion: The Evaluation Evidence Behind Recursive Self-Improvement Claims](https://arxiv.org/abs/2610.27610) (2026)  
     审计 RSI 研究的评测设计，分别检查最终系统的表现、完整循环的可重复性，以及改进器在同起点与同预算下的收益。  
134. [RSI Arena: Towards Recursive Self-Improvement with Human Feedback](https://arxiv.org/abs/2610.33624) (2026)  
     在两阶段自主后训练中比较人类偏好、能力基准与安全表现，观察到偏好改善与基准收益未明显同步。  
135. [SelfImprove-Bench: Evaluating Generalization in Self-Improving Agents](https://arxiv.org/abs/2611.02797) (2026)  
     用五级泛化阶梯检验探索、规划与推理的提升能否迁移到未见场景和更高难度。  
136. [Can Coding Agents Sustain Continual Evolution without Forgetting?](https://arxiv.org/abs/2611.03219) (2026)  
     让编程 Agent 的 harness 在不同软件工程数据集上连续演化，测量此前任务上的性能回退。  
137. [From AutoResearch to Continual AutoResearch: Do Agents Learn Across Tasks?](https://arxiv.org/abs/2611.05108) (2026)  
     在相同任务序列和预算下比较保留与重置状态的 Agent，区分经验对研究效率和最终解质量的影响。  
138. [Beneath the Surface: What We Overlook When We Talk About Agent Evolution](https://arxiv.org/abs/2611.07624) (2026)  
     用重复评测与组件干预检查 harness 演化后的能力保留、部署成本和迁移，并据此修订演化流程。  

## 收录与使用说明

本清单以主要路线、关键分支和代表资料覆盖为目标，不宣称穷尽全部相关文献。近期预印本作为前沿阅读，不代表结论已广泛复现。

阅读时重点检查：

- 系统允许改什么；
- 反馈从哪里来；
- 更新是否保留；
- 是否参与下一轮改进；
- 在未参与优化的任务和相同计算预算下是否仍然有效。

## 贡献

欢迎通过 Issue 或 Pull Request 补充资料。建议说明条目所属路线、研究对象、反馈来源、更新是否持久，以及它为何构成自我改进而不只是单次自我修正。

## 免责声明

本资料仅供学习交流与信息参考，基于公开论文、博客及技术报告整理，不构成对相关研究结论、方法或产品的背书。内容可能存在遗漏、理解偏差或更新滞后，请以原始文献及官方最新信息为准；文中的分类与解读为整理者的理解，不代表原作者或所属机构的立场。
