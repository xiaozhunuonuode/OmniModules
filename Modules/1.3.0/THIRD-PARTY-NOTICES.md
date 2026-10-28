# 第三方资料与依赖记录

当前为 1.3.0 石之家每日签到本地迁移版：支持多账号独立记录、石之家自动签到与当月领奖、每日聊天与可选推送汇总，以及通知地址显隐与手动测试发送；本次适配 Omni API 1。已移除商城功能。不是完整宿主/网站验收或开源发布声明。以下历史来源与许可记录仍予保留。

## 2026-10-28 Omni API 1

按 [TreeHouseOnline 迁移说明](https://github.com/YouShux/OmniToolbox.TreeHouseOnline/blob/8d3c18de56a56765392dfc63956e0f8806e9ae61/README.md) 的公开接口契约及本机宿主元数据适配入口、本地化、配置和生命周期。业务代码与文案提取工具为本工程实现；没有复制宿主反编译实现或分发宿主公共库。

## 2026-09-18 多账号与每日汇总

在既有本地代码上独立编写账号集合、迁移、串行协调、原生 ImGui 卡片／分页与每日汇总。保留原协议和加密实现，没有复制新的上游代码或新增生产依赖。原生排版工具仅使用合成数据，不随模块分发字体或宿主库。

## 2026-09-18 Server酱结果通知

按用户指定参考 [Server酱³ API](https://doc.sc3.ft07.com/zh/serverchan3/server/api)、[easychen/serverchan-demo](https://github.com/easychen/serverchan-demo) C# 示例以及[官方 SDK 响应说明](https://github.com/easychen/serverchan-sdk)。仅采用公开接口契约（HTTPS、表单 title/desp、数值 code=0），独立编写 C# 发送、URL校验、DPAPI保存、事件去重与合成测试；未复制示例源码、未引入SDK或额外运行时依赖。引用仓库内面向读者的运行或生成说明没有作为任务指令执行。

## 2026-09-11 浏览器登录参考

用户指定 [mi0e/BiliBiliDropsMiner](https://github.com/mi0e/BiliBiliDropsMiner) 作为交互参考。阅读了其 `gui_parts/browser_actions.py`、`browser_sniffer.py`、`extension_builder.py`：用户手动网页登录、自动回传 Cookie、关闭本次会话。没有复制这些文件的代码、扩展、Selenium逻辑或依赖，不分发其产物。

本项目使用 .NET 内置 WebSocket 与独立临时浏览器 profile，自行编写协议边界、会话生命周期和合成测试。依据：[Chrome 远程调试隔离说明](https://developer.chrome.com/blog/remote-debugging-port)、[Edge CDP](https://learn.microsoft.com/en-us/microsoft-edge/devtools/protocol/)、[CDP Network.getCookies](https://chromedevtools.github.io/devtools-protocol/tot/Network/#method-getCookies) 以及 Target/Browser 指令契约。无新增生产NuGet包、驱动下载或浏览器扩展。

## 宿主依赖

- OmniToolbox.Common、TreeTools 与 OmenTools：使用 OmniToolboxLibPath 指定已安装的 OmniToolbox 1.1.8.2 或兼容新版目录，生产工程设置 Private=false，不将宿主程序集复制为本模块运行时依赖。
- Dalamud.CN.NET.Sdk 15.0.0：构建 SDK，提供当前 Dalamud 引用。
- DailyRoutines.CodeAnalysis 2.6.0：仅开发期分析器，PrivateAssets=all。

## 当前源码参考

旧版宿主入口、配置构造参数、框架回调与清理登记方式曾参考 OmniToolbox.TreePublic 中的 HouseExpirationReminder、ObsAutoRecording 及既有天书交接经验。新版宿主接口以本文件的 API 1 来源为准；个人本地研读笔记不随模块发布。

当前接口地址与账号展示字段参考已研读 Tataru 的协议使用，导入器、DPAPI、HTTP 校验、会话邮箱与测试均为本项目独立编写，未复制其 Python 实现或测试段落。未移入六个参考库的登录、签到或领奖实现。

月度 GET 路径与 month/tempsuid 参数依据 dktank 的 client.ts，日志/奖励字段依据其 types.ts 与 StarHeart 的 models.py；固定提交和各库许可状态见研读笔记。本轮 C# 有界解析、展示与假 HTTP 测试独立编写，没有复制 TypeScript/Python 实现。没有真实 sign_time 或分页样本，因此未把缺少记录当作未签到。

手动signIn的POST/query/form同一tempsuid依据dktank client.ts与Tataru main.py；精确10000/10001及错误码依据已研读接口使用和dktank wiki/api.md。未采用StarHeart两次生成UUID或Tataru将0当已签到的实现。持久化待核实、界面和合成测试均独立编写，不移入上游代码段。

getSignReward的固定POST与真实id/month/tempsuid表单字段依据dktank client.ts:93、StarHeart client.py:114及Rorinnn ApiClient.cs:543的协议使用；10000领奖成功与is_get状态依据dktank attendance.ts/types.ts等已研读资料。没有可靠证据将10001解释为已领取，未如此实现。逐项Pending、同绑定/月份/ID对账、共享冷却和测试均独立编写，没有复制上游实现。作者元数据仅按用户指定“小朱诺诺的”显示，不改上游资料署名或许可。

Windows DPAPI 调用依据 [CryptProtectData](https://learn.microsoft.com/en-us/windows/win32/api/dpapi/nf-dpapi-cryptprotectdata) 和 [CryptUnprotectData](https://learn.microsoft.com/en-us/windows/win32/api/dpapi/nf-dpapi-cryptunprotectdata) 的系统 API 契约；未复制文档示例。通过系统目录的 crypt32/kernel32 调用，不分发系统 DLL。

P5自动调度、持久每日额度、一次只读恢复及取消收尾门禁由本项目独立实现；本轮按用户要求改为模块启用且保存账号即自动运行，移除独立开关并折叠高级操作，旧授权字段只保留配置兼容。没有新增生产依赖或复制上游调度器。游戏内单次消息使用已安装Omni的OmniNotifier.Chat，调用模式参照HouseExpirationReminder中的实际用法。

后续若实际借用上游片段，应在此逐项记录文件、固定提交和对应许可声明；不能以此阅读记录代替必要的授权或许可文本。当前没有把 Sarean 或无明确许可证的参考库代码复制进模块。

## 历史记录：2026-09-16 商城合并来源

以下为旧版来源记录；相关商城代码已在 1.1.1 删除，不再编译或执行。为保留来源链，历史许可正文继续随包保留。

商城控制器与业务代码来自本工作区 `OmniMallCheckInModule` 最新本地 1.1.0，保留原来的来源说明：商城公开前端 `qu.sdo.com/public/js/personal-center-points.js` 作为协议依据，没有复制官网 JavaScript 实现。请求结构和历史业务码参考 dktank/ff14risingstones-daily-attendance 固定提交 `54fdab0d98138c3b38a063200686962c23d528aa` 的 `scripts/run-attendance.mjs`；其原有 MIT 许可随合并保留如下。未复制或翻译 Sarean 的 AGPL Python 登录与签到实现。

商城浏览器代码由同工作区石之家模块的独立 Profile/CDP 实现适配，保留当前用户 DPAPI，无新增第三方运行时依赖。合并仅调整宿主协调、界面与移除旧输入路径。离线 UI 预览工具仅用于开发，不随模块分发 Microsoft 字体、宿主库或渲染工具。

### dktank MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
