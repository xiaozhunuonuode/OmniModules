# 来源与第三方许可

当前 1.2.1 包含石之家多账号每日签到、领奖和可选每日汇总通知，已移除商城代码。不分发 Omni、Dalamud、OmenTools、Windows 系统库、字体、开发测试或浏览器驱动。以下旧版参考记录及许可正文继续保留。

多账号集合、配置迁移、串行协调、每日汇总与原生 ImGui 卡片由本项目独立编写，没有复制新的上游实现或新增生产运行时依赖。

Server酱通知仅参考 [Server酱³ API](https://doc.sc3.ft07.com/zh/serverchan3/server/api)、[easychen/serverchan-demo](https://github.com/easychen/serverchan-demo) 与[官方 SDK 响应说明](https://github.com/easychen/serverchan-sdk)的公开接口契约，独立实现 HTTPS 表单、地址校验、加密保存与去重；未复制示例代码或引入 SDK。

浏览器登录交互参考 mi0e/BiliBiliDropsMiner，没有复制其 Python 登录实现、Selenium、扩展或依赖。模块使用 .NET WebSocket 与本轮独立浏览器资料目录实现浏览器连接，使用 Windows 当前用户 DPAPI 保存凭据。

石之家接口协议使用参考 dktank、Tataru、StarHeart、Rorinnn 等公开资料，C# 边界校验、状态管理和测试为本项目独立实现，未复制这些项目的 Python／TypeScript 实现。旧版曾参考商城公开前端 qu.sdo.com/public/js/personal-center-points.js 了解协议，没有复制官网 JavaScript 实现；对应功能已从当前版本移除。

旧版商城请求结构及历史业务码参考 dktank/ff14risingstones-daily-attendance 固定提交 `54fdab0d98138c3b38a063200686962c23d528aa` 的 `scripts/run-attendance.mjs`，保留其 MIT 许可如下。未复制或翻译 Sarean 的 AGPL Python 登录或签到实现。显示作者“小朱诺诺的”不替代第三方资料的署名和许可。

## dktank MIT License

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
