# goauth - 简洁易用的 Go 第三方登录 SDK

[![Go Reference](https://pkg.go.dev/badge/github.com/your-github-username/goauth.svg)](https://pkg.go.dev/github.com/your-github-username/goauth)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![持续集成中](https://img.shields.io/badge/状态-持续集成中-blue)

[English](README.md) | **简体中文**

**goauth** 是一个轻量级、易于集成和扩展的 Go 语言 SDK，旨在帮助您快速实现基于 OAuth 2.0 协议的第三方登录功能。目前已封装了 Google 一键登录、微信登录和 GitHub 登录，并且正在持续集成更多流行的第三方登录平台。

## 特性 (简体中文)

* **简洁易用:** 提供简单明了的 API，轻松集成到您的 Go Web 应用或服务中。
* **多平台支持:**
    * ✅ **Google账号一键登录:** 快速集成 Google Sign-In，提供无缝的用户体验。
    * ✅ **微信扫码登录:** 支持扫码登录和网页授权登录。
    * ✅ **GitHub账号一键登录:** 集成 GitHub OAuth 授权流程。
    * ⏳ **持续集成中:** 我们正在积极添加对更多平台的支持，敬请期待！
* **灵活的配置:** 允许您根据不同平台的需求进行灵活配置。
* **清晰的错误处理:** 提供详细的错误信息，方便您进行调试。
* **轻量级依赖:** 尽量减少外部依赖，保持 SDK 的轻巧。

## 快速开始 (简体中文)

### 安装

使用 `go get` 命令安装 goauth SDK：

```bash
go get [github.com/OmniStoneX/goauth](https://github.com/OmniStoneX/goauth)
```

请将 `github.com/your-github-username/goauth` 替换为您的实际 GitHub 仓库路径。

### 使用示例 (简体中文)

```go
// ... (中文示例代码) ...
```

### 其他平台集成 (简体中文)

请参考以下文档了解如何集成其他支持的平台：

* [Google 一键登录](docs/google.md)
* [微信登录](docs/wechat.md)
* [GitHub 登录](docs/github.md)
* [微博 登录](docs/github.md)

### 持续集成中的平台 (简体中文)

我们正在努力添加对以下平台的支持：

* [X(twitter)](链接到该平台的开发者文档或您的 Issue)
* [QQ](链接到该平台的开发者文档或您的 Issue)
* ...

### 配置 (简体中文)

每个第三方登录平台都需要不同的配置信息，例如 Client ID、Client Secret、Redirect URL 和 Scopes 等。请查阅各个平台的具体文档以获取详细的配置说明。

### 贡献 (简体中文)

欢迎任何形式的贡献！如果您发现了 Bug 或者希望添加新的功能或平台支持，请随时提交 Issues 或 Pull Requests。

### 许可证 (简体中文)

[MIT](LICENSE)

### 联系 (简体中文)

如果您有任何问题或建议，欢迎通过 [您的联系方式，例如 GitHub Issues 或邮件] 联系我们。