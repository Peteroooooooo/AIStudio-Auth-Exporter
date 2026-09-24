用于导出 Google AI Studio 登录凭据（Playwright `storageState` JSON），供 [AIStudioToAPI](https://github.com/iBUHub/AIStudioToAPI) 使用。**仅本地导出，绝不上传任何数据。**

#### 快速开始

1. **安装**：打开 `chrome://extensions` 开启“开发者模式” → “加载已解压的扩展程序”选择根目录。
2. **导出**：登录 AI Studio → 点击扩展图标 → 点击**“从当前标签导出 JSON”**。
3. **使用**：将下载的 JSON 上传至 API 控制台。

#### 注意事项

- **切勿外泄**：导出的 JSON 包含登录状态，严禁提交到代码仓库。
- **账号隔离**：一个 Chrome Profile 建议只登录一个 Google 账号，避免 Cookie 串号。
- **多配置**：每个 Chrome Profile 需要单独安装一次本扩展。
