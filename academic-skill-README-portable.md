# Academic Skill

面向学术研究与论文写作的 Agent 工作流包。

它不是一个只会“生成论文文字”的工具，而是一个带有研究流程约束、并强调轻量优先的学术代理：先对齐任务，再按需要学习领域、筛选文献、验证方向、补强证据，最后才进入正式写作。

## 这个 Skill 能做什么

- 学习特定学科或子领域，例如经济学、计算机科学、医学、公共卫生、社会科学等
- 区分经典文献、前沿研究与低质量噪声来源
- 在需要时生成或验证研究 idea，并从创新性、数据可得性、实验可行性、复现难度等维度进行筛选
- 在用户选定方向后，整理真实参考文献、数据路径、证据包与写作提纲
- 按学科规范与目标语言起草论文、综述、proposal、开题报告或章节内容
- 对硕士论文等长文任务进行拆分、逐段写作与汇总
- 在任务确实需要且用户确认规模后，进行数据采集与清洗
- 支持中文、英文和中英混合任务

## 这个 Skill 的核心区别

很多写作工具擅长“把话写出来”，但不擅长“先把研究做扎实”。

这个 skill 的重点在于：

- 不跳过前期研究
- 不编造文献和引用
- 不把弱 idea 直接包装成“创新点”
- 不用同一个模板覆盖所有学科
- 不把中文写作做成英文句式的机械翻译
- 不为小任务强行开启完整重型流程
- 不用流畅措辞掩盖证据不足、字数不足或数据薄弱

## 默认工作流程

1. 先对齐任务目标、交付形式、语言和体量
2. 选择轻量支持、标准项目或长论文模式
3. 建立当前任务真正需要的文献和证据基础
4. 在需要时验证方向、方法、实验设计或数据路径
5. 对长任务进行模块拆分，逐段完成并最后整合

## 适合的任务

- 论文选题与研究 idea 设计
- 文献综述与 related work 写作
- 开题报告、研究计划与 proposal 撰写
- 本科、硕士、博士论文写作
- 中文 CSSCI / 中文核心风格论文写作
- 英文学术论文结构规划与初稿撰写
- 研究方法、实验路径、数据来源与可行性评估

## 中文写作支持

这个 skill 对中文语境做了专门优化：

- 共享中文学术表达规则：避免英文化直译和空泛评价
- 中文论文版风格：更适合本科、硕博论文、章节型长文、开题报告
- 中文期刊版风格：更适合 CSSCI、中文核心、投稿型文章，表达更紧凑，问题意识更强

## 迁移到其他 Agent

这个仓库现在不只适用于 Codex，也可以迁移到 Claude Code 或其他支持自定义提示词的 Agent。

- `academic-research/SKILL.md`
  Codex 原生入口，保留自动触发和资源导航
- `academic-research/references/universal-agent-spec.md`
  平台无关的研究协议，适合放进 system prompt、developer prompt 或项目指令
- `academic-research/references/agent-prompt-pack.md`
  可直接复制的提示词模板，包含模式选择、kickoff、direction validation、evidence pack、outline、drafting 等阶段
- `academic-research/references/agent-portability.md`
  不同 Agent 能力映射，说明什么情况下可以声称“已验证”，什么情况下只能保守表述

如果你在 Claude Code 中使用，最简单的方式是：

1. 把 `universal-agent-spec.md` 放进项目说明或系统提示词
2. 把 `agent-prompt-pack.md` 里的 kickoff prompt 作为任务起点
3. 根据是否有浏览、文件访问、代码执行能力，对照 `agent-portability.md` 调整验证表述

## 快速开始

英文示例：

```text
Use $academic-research to align the task, choose the lightest suitable workflow, learn the literature on digital finance, validate feasible directions, and draft a Chinese thesis-style literature review.
```

中文示例：

```text
使用 $academic-research 帮我先对齐任务目标，再学习“平台经济中的算法定价”这一方向，筛选高质量文献，验证可行研究方向，并按中文期刊风格准备写作提纲。
```

Claude Code / 通用 Agent 示例：

```text
Use the academic research workflow. First align the task, choose the lightest suitable mode, build a field memo on healthcare LLM evaluation, then filter the literature, validate feasible directions, and stop for my selection before drafting.
```

## 仓库结构

- `academic-research/SKILL.md`
  主 skill 说明文件，定义触发条件、工作流程与约束规则
- `academic-research/agents/openai.yaml`
  skill 的展示元数据
- `academic-research/references/`
  各类参考规则文件，包括领域学习、idea 验证、文献综述、引用规范、中文论文风格、中文期刊风格，以及跨 Agent 迁移说明

## 适合谁使用

这个 skill 更适合以下用户：

- 需要系统做论文前期准备的学生
- 需要快速建立领域地图与文献框架的研究者
- 希望用 Agent 协助完成学术写作，但又不希望它“乱编”的使用者

## 使用提醒

这个 skill 可以显著提升学术任务的严谨性，但它仍然不能替代研究者本人对问题、证据与结论的学术责任。

尤其是在医学、公共卫生、政策研究等高风险领域，仍然应由使用者进一步核验：

- 关键资料是否真实
- 证据等级是否可靠
- 引用是否准确
- 是否满足伦理与规范要求
