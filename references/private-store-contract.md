# 私有知识库契约

仅在需要读取或写入用户的长期资料时阅读本文件。

## 入口发现

私有知识库应有一个标题为 `PM Interview Hub` 的首页，并包含标记 `PM_INTERVIEW_HUB_V1`。首页登记各区域的真实链接。

定位规则：

1. 优先使用已连接并获得授权的 Feishu/Lark 或其他文档工具搜索标题与标记。
2. 搜索结果为零时，请用户提供 Hub 链接或先建立知识库。
3. 搜索结果超过一个时，请用户选择。
4. 不把解析出的文档 ID、空间 ID、URL 或凭证写入公开仓库。

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

写入前读取目标页面的最新版本，尽量增量更新。遇到并发修改、结构不兼容或权限不足时停止写入，返回草稿和冲突说明。

## 无连接器时

仍可完成分析和起草，但必须：

1. 明确说明没有写入私有知识库。
2. 按目标页面结构输出可复制草稿。
3. 列出建议写入或更新的页面。
4. 不在 skill 目录、公开仓库或临时 Git 提交中保存个人资料。
