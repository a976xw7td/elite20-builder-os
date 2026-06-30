# Elite20 Builder Program / NSEAP 项目阶段报告

## 一、项目背景

根据 Richard 对 Elite20 Builder Program / NSEAP 智能教育平台复制项目的要求，我们当前的任务不是简单整理一门课程，也不是先做一个完整 LMS，而是先搭建一个可以让二期 Builder 协作共建的 MVP 工作台。

项目目标可以概括为：

> 把 Elite20 / SIAS University Vibe Coding 课程重构为一套可复制、可部署、可持续演化的 AI Native Learning Operating System 参考实现。

当前 GitHub 仓库：

https://github.com/a976xw7td/elite20-builder-program-nseap

## 二、最初版本做了什么

最初版本主要解决的是二期如何先跑起来，也就是先建立 Builder Workflow。

核心流程是：

```text
Challenge 发布
-> AI 辅助开发
-> GitHub 提交
-> Peer Review
-> Agent Review
-> Documentation
-> Release
```

第一版仓库主要包含：

- Challenge 标准模板
- Rubric 评分模板
- Submission 提交模板
- GitHub Issue / PR 模板
- Project Manager Agent、Coding Coach Agent、Evaluation Agent 三个基础 Agent 说明
- Evaluation Report 模板
- MVP Roadmap

这一版的重点是：先把 Challenge、提交、评审、沉淀这一套协作流程标准化。

## 三、结合 Richard 四个文件后的新理解

Richard 后续提供的几个文件，让我们对这个仓库的定位做了升级。

这些文件分别指向四个更底层的方向：

| 文件 / 方向 | 对项目的启发 |
|---|---|
| Cognitive Cell | 一切皆 Agent / Cognitive Cell，课程、Challenge、Skill、Rubric、Knowledge Base 都可以成为系统中的认知单元 |
| Tech-discussions | 不要从 prompt 开始做 Agent，而要从 Situation 开始，按照 Situation -> Ontology -> Workflow -> Skill -> Agent -> Evaluation 的路径构建 |
| Adaptive Agent Model Framework | NSEAP 不是普通课程网站，而是学生、老师、AI Agent、知识库、学习记录、评估闭环共同组成的教育智能体系统 |
| Educational Knowledge Graph / LLM Agent Interface | 后续需要对齐 Ontology、Knowledge Graph、Agent Manifest、消息接口、Session、权限等标准化方向 |

因此，我们对项目的理解从：

```text
二期 Challenge / 作业 / 评审协作仓库
```

升级为：

```text
Elite20 Builder Program / NSEAP Reference Implementation Workspace
```

也就是说，这个仓库不只是用来收作业，而是要逐步成为二期把 Challenge 转化为 Skill、Task Agent、Ontology、Knowledge Base 和 Evaluation System 的工作台。

## 四、结合四个文件后的主要改动

### 1. 增加 Standards Mapping

新增：

```text
standards/standards-mapping.md
```

作用：

说明 Richard 提供的资料如何映射到当前仓库结构。

核心映射是：

```text
Tech-discussions
-> FDE 方法论

Cognitive Cell
-> 一切皆 Cognitive Cell / Agent

Adaptive Agent Model Framework
-> 教育智能体系统架构

Educational Knowledge Graph
-> Course / Skill / Challenge / Assessment Ontology

LLM Agent Interface
-> Agent Manifest / Interface / Session / Permission
```

### 2. 增加 Methodology 方法论层

新增：

```text
methodology/
  situation-to-agent.md
  fde-builder-workflow.md
  skill-construction-framework.md
  kstar-learning-loop.md
```

这部分的核心是把 Builder 的工作方式从“完成作业”升级为：

```text
Situation
-> Context
-> Ontology
-> Workflow
-> Skill
-> Task Agent
-> Evaluation
-> Knowledge Growth
```

也就是说，每个 Challenge 不只是提交一个结果，而应该沉淀出可复用的 Skill、Agent 能力、知识条目或 Ontology 更新。

### 3. 增加 Ontology 层

新增：

```text
ontology/
  course-ontology.md
  skill-ontology.md
  challenge-ontology.md
  project-ontology.md
  assessment-ontology.md
```

这部分用于描述课程、技能、挑战、项目、评估之间的语义关系。

例如：

```text
Challenge produces Skill
Challenge evaluatedBy Rubric
SubmissionArtifact providesEvidenceFor Skill
EvaluationReport mayCreate KnowledgeEntry
```

这样后续 Knowledge Base 不只是资料堆，而可以逐步向教育知识图谱演化。

### 4. 增加 Agent Manifest

新增：

```text
agents/manifests/
  project-manager-agent.manifest.yaml
  coding-coach-agent.manifest.yaml
  evaluation-agent.manifest.yaml
```

这一步是把三个 Agent 从普通说明文档和 prompt，推进到更标准化的 Agent Interface。

每个 manifest 开始定义：

- Agent 是谁
- 能做什么
- 输入是什么
- 输出是什么
- 需要哪些 GitHub 权限
- 和其他 Agent 怎么交接

### 5. 升级 Challenge 模板

原来的 Challenge 模板主要关注：

```text
任务目标
提交材料
评分标准
FAQ
```

现在已经升级为要求每个 Challenge 说明：

```text
Situation
Context
Ontology Mapping
Workflow
Skill / Agent Target
Evaluation
Knowledge Capture
```

这更符合 Richard 提到的“每个 Challenge 都应该成为 Task Skill 或 Task Agent”的方向。

### 6. 增加端到端示例

新增：

```text
examples/challenge-to-cognitive-cell-case/
```

这个示例用 Evaluation Agent 演示一个 Challenge 如何变成 Cognitive Cell。

包含：

```text
situation.md
context.md
ontology-mapping.md
workflow.md
skills.md
sample-submission/
evaluation-report.md
knowledge-capture.md
```

它展示了完整链路：

```text
学生提交 Challenge repo
-> Evaluation Agent 获取上下文
-> 对照 Rubric 检查
-> 生成评分报告
-> 给出修改建议
-> 沉淀 FAQ / Common Mistake / Best Practice / Ontology Update
```

这说明我们的目标不是只写模板，而是把一个 Challenge 真的跑成一个可复用的认知单元。

## 五、当前仓库的结构

当前仓库大致分为这些部分：

```text
docs/                 项目愿景、工作流、MVP路线图、下一步实现计划
standards/            Richard资料与仓库结构的映射
methodology/          Situation到Agent的方法论
ontology/             Course/Skill/Challenge/Project/Assessment本体草案
challenges/           Challenge模板、Rubric模板、提交模板、示例Challenge
agents/               三个基础Agent说明与协作流程
agents/manifests/     三个Agent的manifest
prompts/              三个Agent的prompt
reviews/              Evaluation Report模板
examples/             Challenge转Cognitive Cell的端到端示例
knowledge-base/       FAQ和后续知识沉淀入口
governance/           贡献和评审流程
.github/              GitHub Issue / PR模板
```

## 六、当前阶段的项目定位

当前仓库还不是完整平台，也不是最终 LMS。

它更准确的定位是：

```text
Elite20 Builder Program / NSEAP Reference Implementation Workspace
```

第一阶段重点不是做大而全的平台，而是先验证：

```text
一个 Challenge 能不能被标准化发布；
一个提交能不能被标准化评审；
一次评审能不能沉淀为知识；
一个 Challenge 能不能逐步转化为 Skill / Agent / Cognitive Cell。
```

## 七、下一步建议

下一步建议不要继续堆概念，而是继续做端到端样例。

计划是：

### 1. 完善 Evaluation Agent Case

当前已经有第一版。

后续可以增加：

- 一个优秀提交样例
- 一个不合格提交样例
- Agent Review 与人工 Review 的对照

### 2. 新增 Coding Coach Agent Case

目标是演示：

```text
学生遇到问题
-> Coding Coach 获取上下文
-> 诊断问题
-> 给出实现计划
-> 帮助学生自查
-> 形成 pre-submission check
```

### 3. 新增 Project Manager Agent Case

目标是演示：

```text
多个 Challenge 同时进行
-> 跟踪提交情况
-> 识别 Review Queue
-> 发现阻塞
-> 生成周报
```

### 4. 抽取机器可读 Schema

等三个 Case 跑通后，再抽取：

```text
challenge.schema.yaml
skill.schema.yaml
cognitive-cell.schema.yaml
evaluation-report.schema.yaml
agent-manifest.schema.yaml
```

### 5. 再考虑最小自动化

例如：

- 自动检查 submission.yaml
- 自动检查必交文件是否存在
- 自动生成 Evaluation Report 初稿
- 自动汇总 Challenge 进度

## 八、一句话总结

这次更新之后，项目已经从：

```text
GitHub 作业协作仓库
```

升级为：

```text
以 Challenge 为入口，
以 Cognitive Cell 为基本单元，
以 Situation -> Ontology -> Workflow -> Skill -> Agent -> Evaluation 为生产流程，
逐步沉淀 NSEAP AI Learning Operating System Reference Implementation 的 MVP 工作台。
```

