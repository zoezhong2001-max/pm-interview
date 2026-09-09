# PM Interview Skill

一个用于产品经理求职的 Codex skill，覆盖简历整理、定向准备、模拟面试、单场复盘和流程归档。

## 设计原则

这个仓库只保存可公开复用的规则、模板和路由约定。个人背景、真实简历、公司流程、面试记录、逐字稿和复盘结果保存在用户授权的私有知识库中。

```text
GitHub skill（公开规则）
        ↓ 指导读取与写入
私有知识库（个人事实与产出）
```

私有知识库可以使用 Feishu/Lark 或其他已授权的文档工具。skill 不保存固定账号、文档链接、空间 ID 或访问凭证。

## 推荐使用方式

1. 在私有知识库中建立标题为 `PM Interview Hub` 的首页，并加入标记 `PM_INTERVIEW_HUB_V1`。
2. 在首页登记 Profile、Current Plan、Experience Cards、Processes、Interview Reviews、Reusable Learnings、Resumes、Rule Promotion Queue 和 Inbox 的真实链接。
3. 新的 JD、面试记录或转写先进入 Inbox。
4. 处理任务时先读取本 skill 的对应规则，再按最小读取原则读取私有资料。
5. 将个人化产出写回私有知识库；不要把它们提交到本仓库。
6. 只有完成验证、脱敏和人工授权的通用经验，才可以从 Rule Promotion Queue 晋升为公开规则。

具体的数据边界和目录契约见 [`references/private-store-contract.md`](references/private-store-contract.md)。

## 仓库内容

- `SKILL.md`：入口、路由、状态和隐私边界。
- `references/`：按场景加载的方法与规则。
- `assets/templates/`：不含真实数据的空白模板。
- `scripts/privacy-check.sh`：发布前的自动隐私检查。
- `agents/openai.yaml`：Codex UI 元数据。

## 发布前检查

在仓库根目录运行：

```bash
bash scripts/privacy-check.sh .
```

自动检查不能替代人工复核。发布前仍需检查 Git diff，确认没有姓名、联系方式、公司内部信息、私人文档链接、真实简历、面试原话或密钥。

## 安装

将整个 `pm-interview` 目录放入你的 Codex skills 目录，或使用 Codex 的 skill 安装能力从 GitHub 仓库安装。安装后可通过 `$pm-interview` 显式调用；在产品经理求职或面试语境中也允许自动触发。

## License

[MIT](LICENSE)
