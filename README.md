# OneDock AI Releases

这个仓库专用于 OneDock AI (macOS) 的版本更新与安装包分发。

## 工作流与用途

1. **GitHub Releases**：承载各个版本的应用安装包（如 `.zip` 或 `.dmg`）作为 Release Assets 下载附件。
2. **Sparkle Appcast**：托管位于根目录的 `appcast.xml`，它是客户端检查更新的 RSS 订阅源。
3. **隔离源码**：作为私有主仓库的发布出口，不包含任何业务源代码。

## 更新指南 (For Maintainer)

每次发布新版本时，请执行以下步骤：
1. 编译并公证应用，压缩为 `.zip`。
2. 使用 Sparkle 工具对 `.zip` 进行 EdDSA 签名。
3. 在本仓库创建一个新的 [GitHub Release](https://github.com/zeoi3/onedockAI-releases/releases)，上传 `.zip` 文件。
4. 更新根目录的 `appcast.xml`，添加包含新版本信息及 `sparkle:edSignature` 的 `<item>`。
5. 提交并推送 `appcast.xml` 到本仓库的 `main` 分支。
