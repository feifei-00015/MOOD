<div align="center">
  <img src="docs/readme-assets/mood-app-icon.png" width="160" alt="MOOD 应用图标">
  <h1>MOOD</h1>
  <p><strong>记录自己，也让 AI 慢慢认识你。</strong></p>
  <p>一款把聊天、情绪、事件、计划和生活回忆串在一起的桌面应用。</p>
  <p>该介绍文档支持：<strong>简体中文</strong> · <a href="README_EN.md">English</a></p>
  <p><code>v1.0.0 Beta</code> · Windows x64 · macOS Apple Silicon</p>
  <p><a href="https://github.com/feifei-00015/MOOD/releases/download/v1.0.0-beta/MOOD-1.0.0-Beta-x64-Setup.exe">下载 Windows 版</a> · <a href="https://github.com/feifei-00015/MOOD/releases/download/v1.0.0-beta/MOOD-1.0.0-arm64.dmg">下载 macOS 版</a> · <a href="https://github.com/feifei-00015/MOOD/releases/tag/v1.0.0-beta">查看当前版本</a></p>
</div>

[![MOOD 桌面主页面动效](docs/readme-assets/hero-desktop.gif)](docs/readme-assets/hero-desktop.gif)

## 快速开始

MOOD `v1.0.0 Beta` 目前提供 Windows 和 macOS 两个桌面版本：

| 平台 | 支持架构 | 安装包大小 | 下载 |
| --- | --- | ---: | --- |
| Windows | x64 | 约 379 MB | [下载 `.exe` 安装程序](https://github.com/feifei-00015/MOOD/releases/download/v1.0.0-beta/MOOD-1.0.0-Beta-x64-Setup.exe) |
| macOS | Apple Silicon / arm64 | 约 404 MB | [下载 `.dmg` 安装包](https://github.com/feifei-00015/MOOD/releases/download/v1.0.0-beta/MOOD-1.0.0-arm64.dmg) |
| Linux | 暂未提供 | — | — |

[![MOOD 登录页面动效](docs/readme-assets/login.gif)](docs/readme-assets/login.gif)

### Windows

1. 下载 `MOOD-1.0.0-Beta-x64-Setup.exe`。
2. 运行安装程序，按提示完成安装。
3. 从开始菜单或桌面打开 MOOD。

如果 Windows 显示安全保护提示，请先确认文件来自本仓库的 Releases 页面，再决定是否继续。

### macOS

1. 下载 `MOOD-1.0.0-arm64.dmg`。
2. 打开 DMG，将 MOOD 安装到“应用程序”。
3. 从“应用程序”中打开 MOOD。

当前 macOS Beta 安装包尚未完成 Apple 开发者签名。如果系统阻止首次打开，请先确认安装包来自本仓库的 Releases 页面，然后在“系统设置 → 隐私与安全性”中选择“仍要打开”。

第一次启动时，macOS 还可能要求 MOOD 访问钥匙串中的“心情管家 Safe Storage”：

[![MOOD 的 macOS 钥匙串授权提示](docs/readme-assets/keychain-permission.png)](docs/readme-assets/keychain-permission.png)

这是因为 MOOD 会为本地记录、AI 配置和邮票照片生成加密密钥，并通过 macOS 钥匙串保护这些密钥。当应用需要加密或解密你的本地数据时，系统会询问是否允许它读取自己的安全存储项。你输入的是 Mac 的登录密码，整个验证过程由 macOS 处理，MOOD 不会获得这个密码，也不会因此读取钥匙串里的其他密码。

### 第一次使用

注册并登录后，打开“设置 → AI 模型”，填写你使用的兼容 AI 服务的 API Base URL、模型名称和 API Key，再点击“测试连接”。这些信息请从你选择的 AI 服务商处获取，不要把 API Key 分享给其他人。

Beta 版本仍在持续打磨。重要资料请定期导出备份，升级前也建议先保存一份个人 JSON。

## 为什么安装包比较大？

为了让 Beta 版本安装后就能使用心理支持检索，MOOD 目前随应用带有一份包含 3 万多条向量记录的 RAG 知识索引。安装包中的压缩索引约为 **155 MB**，第一次启动后会展开为约 **324 MB** 的本地工作索引。

`v1.0.0 Beta` 仍是一个正在认真打磨的测试版本。后续会结合大家的实际使用反馈继续精进功能、整理依赖并压缩资源，尽量让下载和安装体积更加友好。如果你对功能取舍、使用体验或体积优化有想法，欢迎通过文末的反馈渠道告诉我们。

## MOOD 想做什么？

我们每天都会经历很多事：一次争吵、一段低落、一个突然冒出的念头，或者终于完成了一件拖了很久的小事。它们常常散落在聊天记录、日历和待办事项里，过一阵子就很难再找回来。

MOOD 想把这些片段慢慢连起来：你可以记录正在发生的事，在需要时获得温和的日常情绪支持，也可以把重要经历整理成事件、故事和行动。经过你确认的记录会成为长期上下文，让之后的对话不必每次都从头开始。

更长远一点，我们希望这些资料不只属于某个模型或某款软件。现在你已经可以把个人画像、对话、事件、情绪和计划导出为 JSON；未来，它还可以被整理成一份由你决定范围、由你授权使用的个人上下文，交给其他 Agent。

[![MOOD 从记录到个人上下文的产品理念](docs/readme-assets/product-concept.png)](docs/readme-assets/product-concept.png)

> README 中的静态图片均使用原始分辨率上传，点击图片可以查看清晰原图。

## 这些功能怎样连在一起？

MOOD 不是把聊天、日历和待办简单地放在同一张桌面上。它们会沿着你的生活自然地接在一起。

### 1. 从一次聊天开始

你可以先说说今天发生了什么，或者只是告诉 MOOD：“我现在有点难受。”它会先听懂你此刻更需要被倾听、一起梳理，还是往前走一小步。

当对话里出现值得留下的经历时，MOOD 会询问你是否要整理，而不是擅自替你下结论。

[![MOOD 陪我聊聊页面](docs/readme-assets/chat.png)](docs/readme-assets/chat.png)

### 2. 把重要的事整理成故事

经过确认的内容可以成为事件。人物、时间、事实、当时的想法、感受和需要会被放在一起，方便以后回看。

当几件事彼此相关时，它们又会慢慢组成一段故事。你看到的不再是零散的聊天，而是自己真正走过的一段生活。

[![MOOD 故事索引页面](docs/readme-assets/story-index.png)](docs/readme-assets/story-index.png)

[![MOOD 事件详情页面](docs/readme-assets/event-detail.png)](docs/readme-assets/event-detail.png)

### 3. 看见情绪的变化

情绪日历让每天的心情、压力、睡眠和触发因素留在时间线上。它不是为了给你打分，而是帮你回头看见：最近哪些事情影响了自己，什么时候更容易疲惫，又有哪些变化正在悄悄发生。

[![MOOD 情绪日历](docs/readme-assets/mood-calendar.png)](docs/readme-assets/mood-calendar.png)

### 4. 把想法变成行动

聊清楚一件事之后，可以把下一步变成今天的计划或长期计划。计划不只是写下来，还能进入番茄钟，变成一段真正开始的专注时间。

完成情况和实际效果会继续被记录。以后再遇到类似的问题，MOOD 不只知道你曾经想做什么，也能参考哪些方法对你确实有用。

[![MOOD 今日计划与长期计划](docs/readme-assets/plans.png)](docs/readme-assets/plans.png)

[![MOOD 番茄钟专注页面](docs/readme-assets/focus-timer.png)](docs/readme-assets/focus-timer.png)

### 5. 也别忘了收藏那些好时刻

生活不只有需要解决的问题。完成一件事、去过一个地方，或者遇见一个想留下来的瞬间，都可以变成一枚邮票。它们是记录，也是给认真生活的自己留下一点奖励。

[![MOOD 邮票收藏页面](docs/readme-assets/stamps.png)](docs/readme-assets/stamps.png)

> 聊天 → 事件与故事 → 情绪 → 计划 → 专注 → 反馈 → 下一次更了解你

## AI 是怎样回答你的？

对你来说，这个过程不需要很复杂：MOOD 会先留意是否存在明显的安全风险；在你允许的范围内，结合近期对话、已经确认的经历、情绪和目标，再参考合适的心理支持对话案例，组织一次更贴近当前处境的回应。

如果出现可能危及人身安全的情况，MOOD 会优先提供安全指引，并鼓励你联系身边可信任的人、当地紧急服务或专业支持，而不是继续普通聊天。

[![MOOD 日常情绪支持回复流程](docs/readme-assets/rag-flow.png)](docs/readme-assets/rag-flow.png)

旧故事只能作为“可能有关”的线索。重要内容需要你确认后，才会被整理成事件或长期记忆；你也始终可以修改、关闭或删除它们。

## 你的记录，归你

当前版本可以导出一份精简 JSON，里面包括个人画像与偏好、有效的聊天记录与摘要、已确认的事件和故事、情绪记录，以及任务和长期计划。

导出文件不会包含邮票图片、系统日志、账号凭据或 AI 配置。请把它当作一份私人资料妥善保管。

**现在已经做到的：**你可以导出这些结构化记录，在更换设备或整理个人资料时继续掌握它们。

**未来想做到的：**从完整档案中生成一份更精炼、范围可选、经过你确认的 Agent Context Pack。你可以把它交给学习、工作、健康或通用 Agent，让新的 AI 更快理解你的背景和偏好。这个自动整理与导入能力仍是未来方向，不是当前版本已经完成的功能。

## 隐私、安全与使用边界

- 你可以分别控制长期记忆、历史上下文、事件整理和个人记忆检索。
- 对话中发现的重要信息不会自动成为事实，需要经过你的确认。
- 生成 AI 回复时，必要的对话和上下文会发送给你配置的 AI 服务商；请同时了解该服务商的隐私政策。
- 重要信息会加密保存。你也可以导出个人资料，或永久删除账号及其关联数据。
- MOOD 提供的是日常情绪支持，不进行心理诊断、药物建议，也不能替代心理咨询、医疗服务或紧急援助。

## 反馈与交流

GitHub 可以直接作为反馈渠道。你可以通过 Issues 提交问题和建议，我们准备了简单的填写模板：

- [反馈使用问题](https://github.com/feifei-00015/MOOD/issues/new?template=bug_report.yml)
- [提出功能建议](https://github.com/feifei-00015/MOOD/issues/new?template=feature_request.yml)
- 邮箱：[lxy20030628@sina.com](mailto:lxy20030628@sina.com)

GitHub Issue 中的内容默认公开，请不要上传 API Key、个人对话或其他隐私资料。如果需要私下交流，也可以发送邮件或扫描下方二维码添加微信：

<div align="center">
  <img src="docs/readme-assets/wechat-qr.jpg" width="360" alt="MOOD 作者个人微信二维码">
</div>

<div align="center">
  <p><strong>模型会更换，但你不必每次重新介绍自己。</strong></p>
</div>
