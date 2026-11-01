# 鸽子 · 设备发现插件（内测安装源）

这是 **ChatGPT / Codex 插件的公开分发仓库**，不是本地 Pigeon Node 安装包。

- 插件内容：`list_devices`、`get_device` 两个只读 MCP 工具，查询经过 GitHub 登录授权的设备及在线状态。
- 云端 MCP：`https://pigeon-dev.a1137583371.workers.dev/v1/mcp`，使用 Cloudflare Access GitHub OAuth。
- 本地电脑节点：单独从 [Pigeon Node](https://github.com/luoluoluo22/pigeon-node/releases/tag/v0.1.0) 安装。
- 当前账户状态：**受邀内测**；其他 GitHub 用户虽然可以公开获取本插件文件，但目前不保证有权访问云端工具。
- 目前不具备远程命令、文件读取、文件传输或端到端加密。

## ChatGPT 桌面端 / Codex（公开 GitHub 安装源）

这是当前不经公共目录审核即可尝试的分发方式，**要求使用支持自定义本地插件市场的 ChatGPT 桌面端 / Codex 环境**。

打开已安装 Codex CLI 的终端：

```sh
codex plugin marketplace add luoluoluo22/pigeon-plugin
```

然后重新打开 ChatGPT 桌面应用，在 **Plugins → 鸽子 Pigeon**（或你的自定义市场来源）找到「鸽子 · 设备发现」，按界面提供的安装操作完成安装。如果桌面应用没有插件市场选择功能，需检查账户/版本支持，不能仅靠本仓库绕过限制。

安装完插件后，按提示 **Connect / GitHub 登录** 完成 Cloudflare Access OAuth，再在 ChatGPT 问「列出我的鸽子设备及在线状态」。若工具未出现，应检查插件已安装、OAuth 已连接及客户端对本地 MCP 插件的支持。

**注意：** 此仓库的 `mcp.json` / `.mcp.json` 声明远程 MCP，但通过本地市场导入时可能标为 **Desktop only**，不保证在 ChatGPT 网页版会话出现工具。登录 GitHub 也不会自动安装本机 Node。不要把“仓库公开”理解为“ChatGPT 插件已经公共上架”。

## ChatGPT Business / Enterprise / Edu 工作区

管理员可以在 **Admin Console → Plugins → Add → Import marketplace** 导入：

```text
https://github.com/luoluoluo22/pigeon-plugin
```

仓库根目录自带 `.agents/plugins/marketplace.json`，Path 一栏留空。导入后由管理员配置插件安装政策、必要的 MCP/应用连接及成员角色。团队成员在其工作区安装插件，再各自授权 GitHub 登录。

该过程只在支持 GitHub 插件市场导入的工作区可用。管理员导入并不自动授权外部服务，也不意味着网页端能运行带 MCP 声明的 Desktop only 插件。

## 未来：ChatGPT 公共插件目录

正式上架后，普通用户才可在 ChatGPT 插件目录搜索「鸽子」→「安装插件」→「连接」→「GitHub 登录」。**截至目前未公开上架**；目前个人私有插件详情链接也不会自动给其他用户安装权限。

## 设备端独立安装

新电脑需要 Node.js 22+，然后可使用固定 GitHub Release：

```sh
npx --yes --package https://github.com/luoluoluo22/pigeon-node/releases/download/v0.1.0/luoluoluo22-pigeon-node-0.1.0.tgz pigeon-node connect
```

该命令安装并运行**本机节点**，不会把插件安装进 ChatGPT。首次连接时在 [设备管理](https://pigeon-dev.a1137583371.workers.dev/admin/) 点击「添加设备」获取 10 分钟一次性绑定码。NPX 是前台进程；服务器长期使用应配置独立 systemd 服务。

## 验证与隐私

本仓库仅含插件清单、公共 MCP URL、Logo 和使用引导，**不包含 Cloudflare/GitHub Secret、用户 Token、私钥、个人设备数据或主项目服务端源码**。客户端无法绕过 Cloudflare Access 权限。任何需要密码、OAuth 授权或设备绑定的步骤必须由使用者自己执行。

官方说明：
- [OpenAI 插件安装与共享](https://help.openai.com/en/articles/20001256-plugins-in-chatgpt)
- [从 GitHub 导入插件市场](https://help.openai.com/en/articles/20001504-importing-and-syncing-plugin-marketplaces-from-github)
- [本地插件市场安装](https://developers.openai.com/plugins/build/plugins)

产品：[鸽子官网](https://pigeon-dev.a1137583371.workers.dev/) · [安装指南](https://pigeon-dev.a1137583371.workers.dev/start) · [支持](https://pigeon-dev.a1137583371.workers.dev/support)
