## 如何提交插件评价（公开）

本仓库的评价用于在 Oclive 客户端内展示，帮助用户鉴别插件可信度与体验。提交方式为 **GitHub Pull Request**。

### 1. 准备信息

你需要知道至少：

- `pluginId`：插件的 `manifest.id`（例如 `com.example.my-plugin`）
- `pubkeyId`：该插件版本签名公钥 ID（来自插件市场索引/客户端展示）
- （可选）`version`：你评价的具体版本（如 `1.2.3`）

> 说明：用 `pluginId + pubkeyId` 绑定，可以避免“同名不同作者”混淆。

### 2. 编辑 `reviews.json`

在 `reviews.json` 的 `reviews[]` 中追加一条记录。示例：

```json
{
  "schemaVersion": 1,
  "generatedAt": "2026-04-28T00:00:00Z",
  "reviews": [
    {
      "id": "r-20260428-000001",
      "pluginId": "com.example.my-plugin",
      "pubkeyId": "ed25519:abcdef1234",
      "version": "1.2.3",
      "rating": 4,
      "title": "功能不错，安装顺利",
      "body": "我主要用来……（可选）",
      "createdAt": "2026-04-28T00:00:00Z",
      "author": {
        "github": "your-github-id"
      }
    }
  ]
}
```

### 3. 规则（v1）

- `rating`：1~5 的整数。
- `title`：建议 5~40 字。
- `body`：可选；禁止包含隐私信息与恶意内容。
- `author.github`：建议填写，便于追溯与反滥用。

### 4. 提交 PR

提交 PR 时请在描述中说明：

- 使用场景
- 评价版本（若填写了 `version`）
- 是否涉及权限/安全风险提示（例如需要 `shell.exec` 等）

