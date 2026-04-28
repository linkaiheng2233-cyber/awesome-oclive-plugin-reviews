## awesome-oclive-plugin-reviews

这个仓库是 **Oclive 插件公开评价索引**（只读索引，不托管插件代码），用于让用户在客户端内通过评分/短评进行初步鉴别。

### 核心原则

- **公开可审阅**：评价通过 GitHub PR 提交，历史可追踪、可回滚。
- **绑定稳定身份**：评价绑定到 `pluginId` + `pubkeyId`（签名公钥 ID）为主，必要时可细化到 `version`。
- **社区站可选**：不依赖网站；客户端可直接拉取本仓库 `reviews.json`。

### 索引文件

- `reviews.json`：索引主文件（schema v1）。

### 贡献

见 [`CONTRIBUTING.md`](./CONTRIBUTING.md)。

