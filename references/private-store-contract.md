# 私有知识库契约

仅在需要读取或写入用户的长期资料时阅读本文件。

## 入口发现

私有知识库应有一个标题为 `PM Interview Hub` 的首页或根目录文件，并包含标记 `PM_INTERVIEW_HUB_V1`。首页登记各区域的真实链接。

定位规则：

1. 优先查找用户此前已选定的 Hub。已选定飞书等文档空间时，不在本地项目另建 Hub；已选定本地项目时，不再搜索并创建平行文档库。
2. 尚未选定时：用户明确指定当前 Codex 项目则查找项目根目录唯一的 `PM Interview Hub.md`；否则使用已授权的文档工具搜索标题与标记。
3. 搜索结果为零时，请用户提供 Hub 入口；用户明确授权当前项目作为长期工作区时，才可建立最小 Hub。
4. 搜索结果超过一个时，请用户选择，禁止同时维护。
5. 不把解析出的文档 ID、空间 ID、URL 或凭证写入公开仓库。

## 推荐区域

- `00 Profile`：个人事实和项目事实。
- `01 Current Plan`：当前求职目标、节奏、限制。
- `02 Experience Cards`：按经历组织的跨公司问答。
- `03 Processes`：按公司、岗位和批次组织的面试流程。
- `04 Interview Reviews`：一场一页的原始记录与复盘。
- `05 Reusable Learnings`：仍与用户相关的跨流程教训。
- `06 Resumes`：已冻结或已投递的简历版本。
- `90 Rule Promotion Queue`：待脱敏、待验证、待发布的通用规则。
- `99 Inbox`：尚未整理的 JD、转写、截图说明或回忆。

## 最小读取

按任务读取最少资料：

| 任务 | 必读 | 按需读取 |
|---|---|---|
| 简历 | Profile、目标 JD | Current Plan、Experience Cards、旧简历 |
| 准备 | 当前 Process、Profile、目标 JD | Experience Cards、Current Plan |
| 模拟 | 当前 Process、Profile | JD、Experience Cards |
| 复盘 | 当前 Process、本场原始记录 | Profile、对应 Experience Cards |
| 归档 | Process、相关 Reviews | Reusable Learnings、Resumes |

不要为了“更完整”而默认读取整个知识库。

## 数据规范

每个派生产物至少记录：

- 标题和更新时间。
- 来源链接或来源说明。
- `confirmed`、`inferred` 或 `needs-verification`。
- 所属公司、岗位、批次或经历标识（适用时）。
- 与 Process、Review、Experience Card 或 Resume 的反向链接。

高风险事实（数字、日期、职责边界、流程结果）还应记录：

- `confirmed_at`：最近一次由用户或可信来源确认的时间。
- `source`：可追溯来源。
- `supersedes`：存在旧口径时明确写出被替代的版本。

## 输出前事实门

只要产出会复述个人事实，按以下顺序读取最新版：

1. Profile 中的事实总表。
2. 当前 Process。
3. 本次会使用的 Experience Card。

三处冲突时不沿用旧对话中的数字或措辞。以最新明确确认的事实为准；仍无法判断则标记 `needs-verification`，并在交付中避免使用争议口径。

面试日期已经过去而 Process 仍为 `preparing` 或 `interviewing` 时，设置 `state-check-needed: true`，同步提醒 Current Plan，并请用户确认实际状态。不得自行改成通过、未通过或等待结果。

写入前读取目标页面的最新版本，尽量增量更新。遇到并发修改、结构不兼容或权限不足时停止写入，返回草稿和冲突说明。

## 准备与复盘写入验收

- 每轮准备固定使用 `assets/templates/round-prep.md`；每场复盘固定使用 `assets/templates/interview-review.md`。板块顺序保持稳定，可在板块内增删内容；缺失材料标记“未获取/不适用”。
- Review 一场一页，Process 保留阶段索引、下一轮假设和当前题单链接，不在两处复制整篇答案；Current Plan 只维护流程状态、下一步和链接。
- 写入前定位目标页并读取最新版本；写入后重新读取，逐项核对标题、场次、来源、固定板块、链接、事实/推断标记、状态和下一步。只报告确实写入成功的页面。
- 写入失败、页面歧义或格式不兼容时，保留原页，提供按固定板块组织的草稿与待补位置；不得声称“已同步飞书”。

## 无连接器时

如果用户没有指定本地项目作为私有知识库，仍可完成分析和起草，但必须：

1. 明确说明没有写入私有知识库。
2. 按目标页面结构输出可复制草稿。
3. 列出建议写入或更新的页面。
4. 不在 skill 目录、公开仓库或临时 Git 提交中保存个人资料。
