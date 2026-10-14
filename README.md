# AI engineering for real-world constraints

**面向真实领域约束的 AI 工程：让回答有依据，让知识更新可追溯，让工作流可控。**

我围绕科研仪器与产业服务场景做 AI 工程实践，关注领域知识如何进入系统、检索结果如何受到约束，以及 Agent 如何与真实业务流程连接。

目前的两条实践主线是：**实验需求 → 仪器知识与证据**，以及 **故障描述 → 维修协作与执行流程**。我把设计取舍、失败案例与验证范围一起公开，欢迎从工程实现和领域问题两方面提出质疑。

## 代表项目

| 项目 | 工程问题与探索 | 当前阶段 |
|---|---|---|
| [华博士 · 科研仪器领域智能体](https://github.com/2137183172-cyber/huaboshi-instrument-agent) | 如何把需求、实验步骤、设备角色和证据连接起来，并保证知识版本一致？ | 已公开开发预览；合成数据演示；未发布专用模型权重 |
| [Lab Repair Agent · 维修协作](https://github.com/2137183172-cyber/lab-repair-agent) | 如何把身份、报价、支付、维修和验收约束变成 Agent 可以安全调用的业务基础？ | 已公开业务工作流源码；LLM 编排仍在路线图 |

→ [项目导航与能力地图](projects/README.md) · [跨项目工程设计](ENGINEERING.md) · [公开建设记录](BUILD_LOG.md)

## 可以直接查看的工程模块

| 模块 | 设计重点 | 实现入口 |
|---|---|---|
| 版本化知识图谱 | 文件指纹、审核状态、版本一致性和回退边界 | [知识发布与图谱](https://github.com/2137183172-cyber/huaboshi-instrument-agent/blob/main/docs/MODULES.md#版本化知识与图谱) |
| 实验工作流约束 | 建模步骤和设备角色，避免把关联设备当作核心能力 | [场景与角色](https://github.com/2137183172-cyber/huaboshi-instrument-agent/blob/main/docs/MODULES.md#实验步骤与设备角色) |
| 公开输出边界 | 事实字段白名单、递归过滤、缺失信息保留 | [事实与输出](https://github.com/2137183172-cyber/huaboshi-instrument-agent/blob/main/docs/MODULES.md#确定性事实与公开输出) |
| 证据驱动的协作工作台 | 确定性匹配、核验依据、人工阶段推进 | [渠道协作](https://github.com/2137183172-cyber/huaboshi-instrument-agent/blob/main/docs/MODULES.md#证据驱动的渠道协作) |
| 维修状态与角色 | 身份档案、支付后开修、验收及协调方流程 | [工单状态](https://github.com/2137183172-cyber/lab-repair-agent/blob/main/docs/MODULES.md#业务状态与执行边界) |
| 匹配与竞标 | 技能与区域评分、报价选择、角色权限 | [工程师匹配](https://github.com/2137183172-cyber/lab-repair-agent/blob/main/docs/MODULES.md#工程师匹配与竞标) |

这些模块来自两个主项目；不是六个独立部署的产品。源码入口和验证范围见各自文档。

## 创新如何被检验

我关心三个可以通过实验回答的问题：

1. **流程与角色约束**能否减少检索推荐中的设备角色错误？
2. **知识版本一致性**能否减少资料更新后的新旧事实混用？
3. **权限、状态与幂等约束**能否降低 Agent 对业务工具的错误调用？

前两个问题已有部分工程基础；第三个问题以维修工作流为起点继续建设。当前尚未发布对照实验结论，不宣称算法首创或性能领先。

技术栈：Python · FastAPI · LangGraph · Neo4j · OpenAI-compatible APIs · Node.js · Vue · uni-app · MySQL / SQLite。

## 最近的公开建设

- **2026-10-13**：两个脱敏开发预览仓库公开，附启动说明、合成样例、贡献入口与验证边界。
- **2026-10-14**：整理工程模块、迭代案例与设计取舍，使历史修改可以追溯到具体问题。

接下来优先补齐公开合成基准、可复现演示、Agent 工具契约和失败案例集。完整的 [迭代逻辑](ITERATION_MAP.md) 与各仓库路线图会区分“源码已有”“本次已验证”和“计划中”。

## 一起研究具体问题

- [仪器选型 AI 什么时候应该继续追问？](https://github.com/2137183172-cyber/huaboshi-instrument-agent/discussions/1)
- [从“仪器坏了”到“有人能修”，最容易卡在哪一步？](https://github.com/2137183172-cyber/lab-repair-agent/discussions/1)

欢迎提交合成或匿名案例、失败样例、设计反例和 Pull Request。一个能复现的问题，比一句“效果很好”更有价值。

[公开 Projects 看板：主项目、模块与下一步实验](https://github.com/users/2137183172-cyber/projects/1)
