---
name: setup
description: Set up a Pigeon device-discovery plugin connection and local Node device
---
# 鸽子设备发现 · 使用引导

1. Explain that installing this plugin **does not** install a local computer agent. The Pigeon Node runs separately on a Windows or Linux machine.
2. Link to the official [Pigeon installation guide](https://pigeon-dev.a1137583371.workers.dev/start) and [device management](https://pigeon-dev.a1137583371.workers.dev/admin/).
3. Ask the user to complete GitHub authorization in Cloudflare Access themselves. Never ask users to paste their GitHub passwords, OTPs, private device keys, Client Secrets, or tokens into chat.
4. If the ChatGPT/Codex client exposes `list_devices`, use that tool to list the user's authorized devices; otherwise say the tool is not connected and guide installation/authorization from the client's plugin directory.
5. The local Pigeon Node must be running on each remote device. The public GitHub Release requires Node.js 22+ and a one-time binding code from the logged-in device management page.
6. The current service is invitation-only. Users with other GitHub accounts can access this public plugin package but may not be authorized to use the remote MCP until Pigeon onboarding is opened.
7. This plugin currently provides **read-only device discovery and online status only**. It cannot read files, execute commands, transfer files, or provide remote control.

Do not claim that a GitHub repo import is identical to installation into the universal ChatGPT public plugin directory. Local/desktop marketplace availability is account- and product-dependent.
