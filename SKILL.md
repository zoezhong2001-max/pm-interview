---
name: pm-interview
description: >-
  帮助用户进行产品经理求职面试，包括简历优化、定向准备、模拟面试、单场复盘和流程归档。
  Use only when the request clearly concerns product-management recruiting or interviews; do not trigger for generic reviews or resumes outside that context.
---

# PM Interview

把本 skill 当作公开、可复用的规则层。个人背景、真实简历、公司流程、面试记录与复盘必须保存在用户授权的私有知识库中，不得写入本 skill 或其 GitHub 仓库。

## 开始工作

1. 判断任务属于：简历、准备、模拟、复盘、流程管理或归档。
2. 判断是否需要用户的历史事实。需要时，按 [private-store-contract.md](references/private-store-contract.md) 定位私有知识库首页，只读取完成当前任务所需的最少材料。
3. 根据模式只加载对应参考：
   - 简历或经历整理：[resume.md](references/resume.md)
   - 面试准备或模拟：[interview-prep.md](references/interview-prep.md)
   - 面试复盘、状态更新或归档：[review-and-archive.md](references/review-and-archive.md)
   - 判断产出写到哪里：[knowledge-routing.md](references/knowledge-routing.md)
   - 在 Codex 项目内长期协作或拆分对话：[project-workspace.md](references/project-workspace.md)
4. 生成结果后，将个人化产出写回已选定的唯一私有知识库。私有知识库可以是已授权的文档空间，也可以是用户明确指定的本地 Codex 项目；不得退回到本 skill 目录保存。

## 私有知识库边界

- 优先使用用户已经选定的长期工作区；可以是当前 Codex 项目，也可以是已经连接且获得授权的文档工具。选定后不得另建平行 Hub，除非用户明确要求迁移或切换。
- 首次使用时定位唯一的 `PM Interview Hub`。找不到时请用户提供入口；找到多个时请用户选择，禁止猜测。
- 只跟随 Hub 中登记的链接，不把私人文档 ID、URL、访问令牌或账号配置写进公开仓库。
- 读取个人事实时保留来源和不确定性。不得把推断改写为已确认事实，不得虚构指标、职责或面试反馈。
- 原始面试记录保持可追溯；结构化复盘和标准答案是派生产物，不能覆盖原始材料。
- 简历、自我介绍、经历问答等包含数字、日期、职责边界或流程状态的产出，生成前必须读取最新事实源；不得仅凭旧对话或旧草稿复用。

## 核心路由

| 内容 | 私有知识库位置 | 规则 |
|---|---|---|
| 个人背景、项目事实、量化口径 | Profile | 唯一事实源；只写确认过的事实 |
| 当前求职目标、节奏和底线 | Current Plan | 时效信息，不进入公开规则 |
| 某段经历的跨公司深挖答案 | Experience Cards | 可在不同流程中复用 |
| 某公司、某岗位的定制材料 | Processes | 一个公司与岗位对应一个流程 |
| 单场面试的原始记录与复盘 | Interview Reviews | 一场一页，链接回流程 |
| 跨流程但仍与用户相关的教训 | Reusable Learnings | 私有沉淀，不等于公开规则 |
| 已冻结简历和投递版本 | Resumes | 保留目标岗位、日期和来源 |
| 候选通用方法 | Rule Promotion Queue | 脱敏、验证后才可进入 GitHub |

### 新流程

用户决定投递或开始准备具体岗位时：

1. 先查找同一公司与岗位的现有流程。
2. 没有时创建流程主页，并在 Current Plan 的流程清单中登记。
3. JD、调研、自我介绍、高频题和模拟材料都链接到该流程，避免散落。

### 面试复盘

- 先判断流程仍在进行还是已经结束；上下文无法判断时再询问用户。
- 每场面试建立独立复盘，并更新流程与 Current Plan 中的流程清单。
- “下次具体怎么回答”写入该流程的问答；跨公司仍成立的经历答案更新 Experience Card。
- 可复用教训先进入 Reusable Learnings。只有满足公开晋升条件时，才进入 Rule Promotion Queue。
- 流程结束时记录最终状态并归档，不再把旧流程当作当前工作台。

## 流程状态

使用以下内部状态，面向用户可显示自然中文：

- `preparing`
- `interviewing`
- `waiting-result`
- `advanced-to-next-round`
- `closed-pass`
- `closed-fail`
- `closed-withdrawn`

流程状态之外可增加 `state-check-needed: true` 作为新鲜度标记。面试时间已过但仍为 `preparing` 或 `interviewing` 时，保留原状态、不猜测结果，并要求用户确认。

## 公开规则晋升门

把私有教训发布到 GitHub 前，必须同时满足：

1. 用户明确确认它具有通用价值，或它已在至少两个独立场景中得到验证。
2. 删除个人、学校、公司、岗位批次、日期、内部指标、原话和文档链接等识别信息。
3. 将经历描述改写为可执行的判断规则、模板或检查项。
4. 运行隐私检查并人工复核变更。
5. 获得用户对本次公开发布的授权；日常复盘不得自动推送 GitHub。

## 公开仓库维护

- 重要更新包括：改变核心路由、隐私边界、状态模型、产出模板或质量门的规则变更；个人记录增长不属于公开仓库更新。
- 仓库已配置 GitHub remote 且用户已授权同步时，重要更新在结构校验、隐私检查和人工 diff 复核全部通过后提交并推送。
- 仅修改措辞、排版或私有知识库内容时，不要求发布新版本。
- 推送失败、远端存在冲突或检查不通过时停止，不强制覆盖远端。

## 通用质量规则

- 默认使用中文；用户、JD 或面试语境要求英文时切换。
- 持续核对职责边界、数字口径、时间和状态；无法确认时明确标注待核实。
- 简历、自我介绍、经历题卡和公司定制答案必须与 Profile 一致。
- 量化不是编数字：没有可靠数据时，使用真实交付物、范围和验证状态。
- 提醒用户避免披露前公司机密、个人隐私和受限数据。
- 模拟面试一次只问一题；除非用户要求即时反馈，否则结束后统一点评。
- 多个 Codex 对话之间不假设自动共享聊天上下文；跨对话事实和状态必须先写入共同的 Hub、Profile、Current Plan 或 Process，再被其他对话复用。
