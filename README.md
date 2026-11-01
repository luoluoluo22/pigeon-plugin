# 鸽子 · ChatGPT 网页版接入

鸽子通过云端 HTTPS MCP 连接 ChatGPT。**不需要安装本地插件，也不需要执行命令。**

## 接入流程

仅适用于有 **Add custom MCP server** 入口的 ChatGPT 网页账号或工作区：

1. 打开 [ChatGPT 插件目录](https://chatgpt.com/plugins)，点击「+」→「Add custom MCP server」。
2. 名称填写 `鸽子 · 设备发现`，服务器地址填写：

   ```text
   https://pigeon-dev.a1137583371.workers.dev/v1/mcp
   ```

3. 选择 OAuth 身份验证，创建连接，完成 Cloudflare Access 的 GitHub 授权。
4. 在支持插件的 ChatGPT Work 网页会话中查询设备。

目前服务端仅对受邀 GitHub 账号开放。安装接口的权限由 ChatGPT 账号/工作区控制；没有入口时不能直接启用。

[查看精简网页版接入指南](https://pigeon-dev.a1137583371.workers.dev/chatgpt)。

## 设备端

ChatGPT 连接的是云端 MCP；要让电脑被发现，还需要在该电脑上运行 Pigeon Node。

- [GitHub 设备管理](https://pigeon-dev.a1137583371.workers.dev/admin/)
- [设备安装指南](https://pigeon-dev.a1137583371.workers.dev/start)
- [公开 Node 安装包](https://github.com/luoluoluo22/pigeon-node/releases/tag/v0.1.0)

当前 MCP 仅提供 `list_devices`、`get_device` 两个只读工具，不提供远程命令、文件读取、文件传输或远控。

## 官方资料

- [自定义 MCP 连接说明](https://help.openai.com/en/articles/12584461-connecting-custom-mcp-servers-in-chatgpt)
- [ChatGPT 插件目录](https://chatgpt.com/plugins)

[官网](https://pigeon-dev.a1137583371.workers.dev/) · [帮助](https://pigeon-dev.a1137583371.workers.dev/support) · [隐私](https://pigeon-dev.a1137583371.workers.dev/privacy)

本仓库仍保存早期插件清单作为开发存档；面向网页用户的正式接入方式是远程 MCP URL。
