# GPT Auth Bridge

**纯本地小工具** — 一键下载 `index.html`，在浏览器中打开即可使用，所有处理在浏览器内存中完成，不部署到任何服务器。

将 ChatGPT 网页登录态 `chatgpt.com/api/auth/session` 的响应 JSON 转换为 `Codex CLI(Codex APP)` 的 `~/.codex/auth.json` 格式。

## 适用范围

本工具适用于以下场景：

- **网页端 `chatgpt.com` 可正常登录使用**
- **Codex CLI 登录时要求手机号码验证**

通过提取网页端已有的登录会话，跳过 Codex 端的验证流程，直接生成可用的 `auth.json`。

如果网页端本身也要求手机号码验证，本工具无法绕过，建议使用接码平台处理网页端的手机验证后再使用。

后若再次出现codex要求登录，使用相同方式再次处理即可。

## 使用方式

1. [点击下载 index.html](https://raw.githubusercontent.com/wxpacc/chatgpt-codex-auth/master/index.html)（打开后 `Ctrl+S` 保存，或右键另存为）
2. 访问 `https://chatgpt.com/api/auth/session`，复制全部响应内容（访问前请确保plus账号已登录）
3. 粘贴到左侧「Session 响应」输入框（或点击粘贴按钮 / 打开文件）
4. 点击「转换」按钮（快捷键 `Ctrl+Enter`，勾选「压缩」可输出紧凑格式）
5. 点击「复制」按钮获取转换结果，或点击「下载」直接保存 `auth.json`
6. 将内容放入 `~/.codex/auth.json`
   - macOS / Linux: `~/.codex/auth.json`
   - Windows: `C:\Users\<用户名>\.codex\auth.json`

## 安全

- 所有处理在浏览器内存中完成
- 不发送任何网络请求
- 不使用 localStorage / sessionStorage / Cookie
- 关闭页面即清除所有数据
