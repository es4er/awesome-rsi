# Awesome RSI

> 递归自我改进（Recursive Self-Improvement, RSI）与自进化智能体研究阅读路线图。

本清单整理了 102 项代表性论文、博客与项目，覆盖理论、Agent Harness、模型权重、训练、数据、评价、环境、联合改进、自动化 AI 研发及评测边界。

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

## 01 Harness：提示词、记忆、技能、工作流与自身代码

Harness 是包在模型外面的运行系统，这一类通常不更新底座模型权重。建议先读 DGM → GEPA → ReasoningBank → ADAS。

### A. 自身代码与在线运行框架

8. [Darwin Gödel Machine (DGM)](https://arxiv.org/abs/2505.22954) (2025) — **⭐ 先读**  
   Agent 修改自身实现，通过实测筛选，并从保存的版本继续探索。 [项目页](https://sakana.ai/dgm/)  
9. [SICA — A Self-Improving Coding Agent](https://arxiv.org/abs/2504.15228) (2025)  
   编程 Agent 检查并编辑自身实现，用评测反馈改进性能与效率。  
10. [Gödel Agent: A Self-Referential Agent Framework for Recursive Self-Improvement](https://arxiv.org/abs/2410.04444) (2024)  
    在目标和反馈约束下自主修改自身代码与逻辑。  
11. [Self-Taught Optimizer (STOP): Recursively Self-Improving Code Generation](https://arxiv.org/abs/2310.02304) (2023)  
    让负责优化程序的改进器优化自身。  
12. [Hyperagents](https://arxiv.org/abs/2603.19461) (2026) — **⭐ 先读**  
    把任务 Agent 与元 Agent 放进可修改系统。  
13. [Huxley-Gödel Machine (HGM)](https://arxiv.org/abs/2510.21614) (2025)  
    区分当前任务分数与后代质量，用后代表现指导自修改搜索。  
14. [Meta-Harness: End-to-End Optimization of Model Harnesses](https://arxiv.org/abs/2603.28052) (2026)  
    外层 Agent 读取历史代码、评分和执行轨迹，搜索更好的 harness。  
15. [Live-SWE-agent](https://arxiv.org/abs/2511.13646) (2025)  
    在软件工程任务中在线调整执行框架，重点看任务内适应。  
16. [Continual Harness](https://arxiv.org/abs/2605.09998) (2026)  
    在持续交互中更新提示、技能、记忆与子 Agent。  
17. [Prime Agent](https://www.primeintellect.ai/blog/prime-agent) (2026)  
    可修改 harness 用于实际编程 Agent 的官方工程解读。  

### B. 提示词与上下文

18. [APE — Large Language Models Are Human-Level Prompt Engineers](https://arxiv.org/abs/2211.01910) (2022)  
    模型生成候选指令，再按任务得分选择。  
19. [OPRO — Large Language Models as Optimizers](https://arxiv.org/abs/2309.03409) (2023)  
    把历史候选和分数交给模型，提出下一轮更好的提示或解。  
20. [DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines](https://arxiv.org/abs/2310.03714) (2023)  
    将模型调用写成模块，再按评价指标优化提示与示例。 [项目页](https://dspy.ai/)  
21. [MIPRO — Optimizing Instructions and Demonstrations for Multi-Stage Language Model Programs](https://arxiv.org/abs/2406.11695) (2024)  
    联合优化多阶段流程中的指令和少样本示例。  
22. [TextGrad: Automatic “Differentiation” via Text](https://arxiv.org/abs/2406.07496) (2024)  
    把自然语言批评作为优化信号，沿计算图改进多个组件。  
23. [metaTextGrad: Automatically Optimizing Language Model Optimizers](https://arxiv.org/abs/2505.18524) (2025)  
    从“优化任务”走向“优化优化器”。  
24. [Promptbreeder: Self-Referential Self-Improvement Via Prompt Evolution](https://arxiv.org/abs/2309.16797) (2023) — **⭐ 先读**  
    同时演化任务提示和用于产生新提示的变异提示。  
25. [GEPA: Reflective Prompt Evolution Can Outperform Reinforcement Learning](https://arxiv.org/abs/2507.19457) (2025) — **⭐ 先读**  
    根据执行轨迹反思并演化提示。 [GitHub](https://github.com/gepa-ai/gepa)  
26. [ACE — Agentic Context Engineering](https://arxiv.org/abs/2510.04618) (2025)  
    把上下文当作可积累、更新和整理的经验手册。  

### C. 记忆与经验

27. [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366) (2023) — **⭐ 先读**  
    把失败转化成文字反思，供后续尝试使用；不更新模型权重。  
28. [ExpeL: LLM Agents Are Experiential Learners](https://arxiv.org/abs/2308.10144) (2023)  
    从任务经历中提炼通用经验，在新任务中检索和使用。  
29. [Dynamic Cheatsheet: Test-Time Learning with Adaptive Memory](https://arxiv.org/abs/2504.07952) (2025)  
    维护精简的策略、代码片段与解题经验，在推理时复用。  
30. [ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory](https://arxiv.org/abs/2509.25140) (2025) — **⭐ 先读**  
    从自评的成功和失败经历中提炼推理策略。 [解读](https://research.google/blog/reasoningbank-enabling-agents-to-learn-from-experience/)  
31. [A-MEM: Agentic Memory for LLM Agents](https://arxiv.org/abs/2502.12110) (2025)  
    动态组织、关联和更新记忆条目。  
32. [MemEvolve: Meta-Evolution of Agent Memory Systems](https://arxiv.org/abs/2512.18746) (2025)  
    搜索记忆系统的编码、存储、检索和管理方式。  

### D. 工具与技能

33. [Voyager: An Open-Ended Embodied Agent with Large Language Models](https://arxiv.org/abs/2305.16291) (2023) — **⭐ 先读**  
    在 Minecraft 中探索并积累可执行代码技能。 [项目页](https://voyager.minedojo.org/)  
34. [LATM — Large Language Models as Tool Makers](https://arxiv.org/abs/2305.17126) (2023)  
    模型生成可复用工具，再由工具使用者调用。  
35. [SkillWeaver: Web Agents Can Self-Improve by Discovering and Honing Skills](https://arxiv.org/abs/2504.07079) (2025)  
    通过网页探索、练习和反馈，把操作沉淀成可复用 API。  

### E. 工作流与多 Agent

36. [ADAS — Automated Design of Agentic Systems](https://arxiv.org/abs/2408.08435) (2024) — **⭐ 先读**  
    元 Agent 编写、测试和搜索新的 Agent 设计。  
37. [AFlow: Automating Agentic Workflow Generation](https://arxiv.org/abs/2410.10762) (2024)  
    搜索模型调用、检查与任务分解等工作流结构。  
38. [EvoFlow: Evolving Diverse Agentic Workflows On The Fly](https://arxiv.org/abs/2502.07373) (2025)  
    通过检索、交叉、变异和选择演化工作流种群。  
39. [EvoAgentX: An Automated Framework for Evolving Agentic Workflows](https://arxiv.org/abs/2507.03616) (2025)  
    整合工作流生成、运行、评价和多种优化算法。  

## 02 模型权重：自训练、自纠错与测试时学习

这一类真正更新模型参数。建议先读 STaR → ReST-EM → SEAL → TTRL。

40. [STaR: Bootstrapping Reasoning With Reasoning](https://arxiv.org/abs/2203.14465) (2022) — **⭐ 先读**  
    生成推理过程，筛选正确样本，再用于下一轮训练。  
41. [Reinforced Self-Training (ReST) for Language Modeling](https://arxiv.org/abs/2308.08998) (2023)  
    反复生成样本并用奖励反馈改进策略。  
42. [ReST-EM — Beyond Human Data: Scaling Self-Training for Problem-Solving with Language Models](https://arxiv.org/abs/2312.06585) (2023) — **⭐ 先读**  
    用可验证反馈筛选自生成解，再训练并重复。  
43. [SPIN — Self-Play Fine-Tuning Converts Weak Language Models to Strong Language Models](https://arxiv.org/abs/2401.01335) (2024)  
    让模型与上一轮输出进行自博弈微调。  
44. [RISE — Recursive Introspection: Teaching Language Model Agents How to Self-Improve](https://arxiv.org/abs/2407.18219) (2024)  
    根据先前尝试与反馈进行多轮修正。  
45. [SCoRe — Training Language Models to Self-Correct via Reinforcement Learning](https://arxiv.org/abs/2409.12917) (2024)  
    用多轮在线强化学习改善自纠错。  
46. [SEAL — Self-Adapting Language Models](https://arxiv.org/abs/2506.10943) (2025) — **⭐ 先读**  
    模型生成用于更新自身的数据与更新指令。 [项目页](https://jyopari.github.io/posts/seal)  
47. [TTRL — Test-Time Reinforcement Learning](https://arxiv.org/abs/2504.16084) (2025) — **⭐ 先读**  
    在没有真实标签的测试数据上估计奖励并更新参数。  
48. [SDFT — Self-Distillation Enables Continual Learning](https://arxiv.org/abs/2601.19897) (2026)  
    让带示例上下文的模型充当自己的教师。  

## 03 训练调参：超参数、架构、优化器与损失函数

建议先读 autoresearch → PBT → DiscoPOP，再读元学习与算法发现。

49. [autoresearch](https://github.com/karpathy/autoresearch) (2026) — **⭐ 先读**  
    Agent 改训练代码、运行限时实验、比较结果并保留有效改动。  
50. [Population Based Training of Neural Networks (PBT)](https://arxiv.org/abs/1711.09846) (2017) — **⭐ 先读**  
    在训练中联合更新模型与超参数日程。  
51. [Neural Architecture Search with Reinforcement Learning](https://arxiv.org/abs/1611.01578) (2016)  
    用控制器生成网络结构、训练和评价候选。  
52. [Learning to Learn by Gradient Descent by Gradient Descent](https://arxiv.org/abs/1606.04474) (2016)  
    把优化器本身变成可学习的模型。  
53. [VeLO: Training Versatile Learned Optimizers by Scaling Up](https://arxiv.org/abs/2211.09760) (2022)  
    训练可用于不同任务的学习型优化器。  
54. [Lion — Symbolic Discovery of Optimization Algorithms](https://arxiv.org/abs/2302.06675) (2023)  
    通过程序搜索发现优化算法。  
55. [AutoML-Zero: Evolving Machine Learning Algorithms From Scratch](https://arxiv.org/abs/2003.03384) (2020)  
    从基础数学运算演化学习算法。  
56. [DiscoPOP — Discovering Preference Optimization Algorithms with and for Large Language Models](https://arxiv.org/abs/2406.08414) (2024) — **⭐ 先读**  
    模型提出并实现偏好优化损失，继续搜索更好的损失函数。  
57. [Eliminating Meta Optimization Through Self-Referential Meta Learning](https://arxiv.org/abs/2212.14392) (2022)  
    研究能修改自身学习行为的自指元学习系统。  

## 04 数据与课程：自己出题，决定接下来学什么

先读 Self-Instruct，再读 Absolute Zero → R-Zero → Agent0。“零数据”通常指特定后训练阶段。

58. [Self-Instruct: Aligning Language Models with Self-Generated Instructions](https://arxiv.org/abs/2212.10560) (2022) — **⭐ 先读**  
    从少量种子任务生成、过滤指令数据，再用于训练。  
59. [WizardLM / Evol-Instruct](https://arxiv.org/abs/2304.12244) (2023)  
    逐步把已有指令改写得更复杂，再用生成数据训练模型。  
60. [Absolute Zero: Reinforced Self-Play Reasoning with Zero Data](https://arxiv.org/abs/2505.03335) (2025) — **⭐ 先读**  
    模型自己提出和解决代码任务，由执行器提供反馈。  
61. [Self-Challenging Language Model Agents](https://arxiv.org/abs/2506.01716) (2025)  
    构造带验证函数的任务，用挑战者和执行者形成循环。  
62. [R-Zero: Self-Evolving Reasoning LLM from Zero Data](https://arxiv.org/abs/2508.05004) (2025) — **⭐ 先读**  
    出题者与解题者共同演化。  
63. [Agent0: Unleashing Self-Evolving Agents from Zero Data via Tool-Integrated Reasoning](https://arxiv.org/abs/2511.16043) (2025)  
    课程 Agent 与执行 Agent 共同演化。  

## 05 评价与奖励：自己打分，也改进打分方式

先读 Self-Rewarding → Self-Taught Evaluators → rStar-Math，再读 RQGM。

64. [Constitutional AI: Harmlessness from AI Feedback](https://arxiv.org/abs/2212.08073) (2022)  
    依据人为原则，让 AI 生成批评、修改与偏好反馈。  
65. [Self-Rewarding Language Models](https://arxiv.org/abs/2401.10020) (2024) — **⭐ 先读**  
    模型同时生成并评价回答，通过迭代偏好优化共同提升。  
66. [Self-Taught Evaluators](https://arxiv.org/abs/2408.02666) (2024) — **⭐ 先读**  
    从未标注指令与合成对比回答出发训练评价模型。  
67. [ReST-MCTS*: LLM Self-Training via Process Reward Guided Tree Search](https://arxiv.org/abs/2406.03816) (2024)  
    用树搜索与过程奖励生成训练轨迹。  
68. [rStar-Math: Small LLMs Can Master Math Reasoning with Self-Evolved Deep Thinking](https://arxiv.org/abs/2501.04519) (2025) — **⭐ 先读**  
    推理策略与过程偏好模型迭代共同训练。  
69. [Eureka: Human-Level Reward Design via Coding Large Language Models](https://arxiv.org/abs/2310.12931) (2023)  
    模型编写奖励函数，查看训练反馈，再修改奖励代码。 [项目页](https://eureka-research.github.io/)  
70. [The Red Queen Gödel Machine: Co-Evolving Agents and Their Evaluators (RQGM)](https://arxiv.org/abs/2606.26294) (2026)  
    让 Agent 与评价过程共同演化。  

## 06 自博弈与环境：让对手、关卡和模拟经验也变化

先读 AlphaZero → POET → EnvGen。环境演化和固定算法下的自博弈属于相关基础，并非天然具备元递归能力。

71. [AlphaZero — Mastering Chess and Shogi by Self-Play with a General Reinforcement Learning Algorithm](https://arxiv.org/abs/1712.01815) (2017) — **⭐ 先读**  
    通过与自身对弈不断生成学习信号。  
72. [POET — Paired Open-Ended Trailblazer](https://arxiv.org/abs/1901.01753) (2019) — **⭐ 先读**  
    同时生成学习环境和对应解决方案。  
73. [Enhanced POET](https://arxiv.org/abs/2003.08536) (2020)  
    扩展开放式环境与策略共同演化。  
74. [ACCEL — Evolving Curricula with Regret-Based Environment Design](https://arxiv.org/abs/2203.01302) (2022)  
    逐步编辑关卡，让课程保持在 Agent 能力边界附近。  
75. [EnvGen: Generating and Adapting Environments via LLMs for Training Embodied Agents](https://arxiv.org/abs/2403.12014) (2024) — **⭐ 先读**  
    根据 Agent 薄弱能力，让大模型调整训练环境。  
76. [DreamGym — Scaling Agent Learning via Experience Synthesis](https://arxiv.org/abs/2511.03773) (2025)  
    用经验模型合成状态转移与反馈，自适应生成训练任务。  
77. [SPIRAL: Self-Play on Zero-Sum Games Incentivizes Reasoning via Multi-Agent Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2506.24119) (2025)  
    与不断变强的自身版本博弈，形成对手驱动课程。  

## 07 联合改进：把多个循环连接起来

先读 BetterTogether → SkillRL，再看多模态和 MetaRSI。

78. [BetterTogether — Fine-Tuning and Prompt Optimization: Two Great Steps that Work Better Together](https://arxiv.org/abs/2407.10930) (2024) — **⭐ 先读**  
    交替优化提示词和模型权重。  
79. [SkillRL: Evolving Agents via Recursive Skill-Augmented Reinforcement Learning](https://arxiv.org/abs/2602.08234) (2026) — **⭐ 先读**  
    让技能库与 Agent 策略在强化学习中共同演化。  
80. [Agent0-VL: Exploring Self-Evolving Agent for Tool-Integrated Vision-Language Reasoning](https://arxiv.org/abs/2511.19900) (2025)  
    视觉语言模型同时承担解题与验证角色。  
81. [VLAW: Iterative Co-Improvement of Vision-Language-Action Policy and World Model](https://arxiv.org/abs/2602.12063) (2026)  
    真实交互改进世界模型，再用模拟数据改进机器人策略。  
82. [RLAnything: Forge Environment, Policy, and Reward Model in Completely Dynamic RL System](https://arxiv.org/abs/2602.02488) (2026)  
    联合更新环境、策略和奖励模型。  
83. [MetaRSI / RSI2: A Meta-Recursive Self-Improving System for Recursive Self-Improving Systems Themselves](https://arxiv.org/abs/2609.06396) (2026)  
    探索数据、harness 与模型更新的组合及元调度。  

## 08 自动化 AI 研发：让 AI 参与设计下一代 AI

先读 AIDE → AlphaEvolve → Frontis-MA1。自动完成实验或论文不直接证明新系统已接管并增强下一轮研发。

84. [AIDE: AI-Driven Exploration in the Space of Code](https://arxiv.org/abs/2502.13138) (2025) — **⭐ 先读**  
    把机器学习工程表示成代码空间中的树搜索。  
85. [The AI Scientist: Towards Fully Automated Open-Ended Scientific Discovery](https://arxiv.org/abs/2408.06292) (2024)  
    覆盖研究想法、实验、分析和论文写作。 [项目页](https://sakana.ai/ai-scientist/)  
86. [The AI Scientist-v2: Workshop-Level Automated Scientific Discovery via Agentic Tree Search](https://arxiv.org/abs/2504.08066) (2025)  
    通过实验管理与树搜索扩展自动科研流程。  
87. [AlphaEvolve: A Coding Agent for Scientific and Algorithmic Discovery](https://arxiv.org/abs/2506.13131) (2025) — **⭐ 先读**  
    代码生成、自动评价与演化搜索结合。 [介绍](https://deepmind.google/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms/) · [影响](https://deepmind.google/blog/alphaevolve-impact/)  
88. [ASI-Evolve: AI Accelerates AI](https://arxiv.org/abs/2603.29640) (2026)  
    把数据、架构与学习算法探索放入自动化实验循环。  
89. [Frontis-MA1 / OpenMLE](https://arxiv.org/abs/2607.28568) (2026) — **⭐ 先读**  
    结合可验证机器学习环境、研究操作训练和长时程搜索。  
90. [Accelerating Scientific Discovery with Co-Scientist](https://arxiv.org/abs/2502.18864) (2025)  
    多 Agent 生成、辩论和改进科学假设。  

## 09 评测与边界：怎样判断它是真的变强

先读 PAST-Bench 和 S3Gym，再读反例。能力更强、经验有效、改进器更强，是三个不同的评价问题。

91. [PAST-Bench: Benchmarking the Foundations of Recursive Self-Improvement in Personal Agents](https://arxiv.org/abs/2608.04003) (2026) — **⭐ 先读**  
    检查经验是否通过保存、检索和更新改善后续表现。  
92. [S3Gym: Can LLMs Turn Self-Testing and Self-Judging into Self-Improvement?](https://arxiv.org/abs/2608.31100) (2026) — **⭐ 先读**  
    分开探索与保留测试，对比三条经验利用路径。  
93. [Large Language Models Cannot Self-Correct Reasoning Yet](https://arxiv.org/abs/2310.01798) (2023)  
    分析缺少外部反馈时的自纠错失败。  
94. [Large Language Model Agents Are Not Always Faithful Self-Evolvers](https://arxiv.org/abs/2601.22436) (2026)  
    用因果干预检查 Agent 是否真的依赖积累经验。  
95. [AI Models Collapse When Trained on Recursively Generated Data](https://www.nature.com/articles/s41586-024-07566-y) (2024)  
    研究递归生成数据造成分布退化的条件与机制。  
96. [MLE-bench: Evaluating Machine Learning Agents on Machine Learning Engineering](https://arxiv.org/abs/2410.07095) (2024)  
    评价模型选择、数据处理和训练等机器学习工程能力。  
97. [RE-Bench: Evaluating Frontier AI R&D Capabilities of Language Model Agents against Human Experts](https://arxiv.org/abs/2411.15114) (2024)  
    用开放式研究工程任务与人类专家对照。  
98. [PaperBench: Evaluating AI's Ability to Replicate AI Research](https://arxiv.org/abs/2504.01848) (2025)  
    评价理解并复现 AI 论文的能力。  
99. [LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory](https://arxiv.org/abs/2410.10813) (2024)  
    评价长期交互中的记忆能力。  
100. [MemoryAgentBench — Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://arxiv.org/abs/2507.05257) (2025)  
     检查多轮交互下的信息记忆、更新与使用。  
101. [Self-Refine: Iterative Refinement with Self-Feedback](https://arxiv.org/abs/2303.17651) (2023)  
     一次任务内反复修改输出，不等于系统发生持久改进。  
102. [Recursive Language Models](https://arxiv.org/abs/2512.24601) (2025)  
     这里的 recursive 是计算结构，不能据此归入 RSI 成果。  

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
