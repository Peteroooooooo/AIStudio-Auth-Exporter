# AI Studio Auth Exporter

这是为 [AIStudioToAPI 原项目（iBUHub/AIStudioToAPI）](https://github.com/iBUHub/AIStudioToAPI) 制作的非官方 Chrome 扩展。原项目把 Google AI Studio Build 封装为兼容 OpenAI、Gemini 和 Anthropic 的 API，并使用浏览器认证 JSON 管理账号。

本扩展从当前 Chrome Profile 中已登录的 AI Studio 标签和 Cookie 导出兼容 Playwright `storageState` 的 JSON，供你手动上传到 AIStudioToAPI 控制台。它只下载本地文件，不会自行上传。扩展与服务端、Docker 镜像分开；我的 [AIStudioToAPI 定制版 fork](https://github.com/Peteroooooooo/AIStudioToAPI) 是另一个仓库。

## 安装

1. Chrome 打开 `chrome://extensions`，开启“开发者模式”。
2. 点击“加载已解压的扩展程序”，选择本仓库的根目录（包含 `manifest.json`）。
3. 每个需要导出的 Chrome Profile 各安装一次。扩展只能读取它所在 Profile 的当前标签和 Cookie。

## 使用

1. 在目标 Profile 中打开并登录 AI Studio，切到 AI Studio 标签。
2. 点击扩展图标，再点击“从当前标签导出 JSON”。
3. JSON 会下载到 Chrome 的下载目录。再到原项目或定制版的控制台手动上传。

认证 JSON 包含登录状态，使用后请妥善保管或删除。如果同一个 Profile 登录了多个 Google 账号，导出的 Google Cookie 可能包含这些账号的会话；建议每个账号使用独立 Profile。不要把导出的 JSON 提交到 GitHub。

可运行 `node --test test/core.test.cjs` 检查格式转换逻辑。
