# 来源与第三方许可

本版本合并同一开发工作区的石之家模块与商城模块，不分发 Omni、Dalamud、OmenTools、Windows 系统库或字体。

浏览器登录交互参考 mi0e/BiliBiliDropsMiner，没有复制其 Python 登录实现、Selenium、扩展或依赖。模块使用 .NET WebSocket 与本轮独立浏览器资料目录实现浏览器连接，使用 Windows 当前用户 DPAPI 保存凭据。

石之家接口协议使用参考 dktank、Tataru、StarHeart、Rorinnn 等公开资料，C# 边界校验、状态管理和测试为本项目独立实现，未复制这些项目的 Python／TypeScript 实现。商城公开前端 qu.sdo.com/public/js/personal-center-points.js 用于了解协议，没有复制官网 JavaScript 实现。

商城请求结构及历史业务码参考 dktank/ff14risingstones-daily-attendance 固定提交 `54fdab0d98138c3b38a063200686962c23d528aa` 的 `scripts/run-attendance.mjs`，保留其 MIT 许可如下。未复制或翻译 Sarean 的 AGPL Python 登录或签到实现。显示作者“小朱诺诺的”不替代第三方资料的署名和许可。

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
