# fc-downloader · 简体中文本地化

此分支基于 [ryoctrl/fc-downloader](https://github.com/ryoctrl/fc-downloader)，为桌面界面新增简体中文支持。项目使用 [MIT 许可证](LICENSE)。

## 切换语言

在左侧进入 **Settings / 設定 → General / 一般 → Language / 言語 → 简体中文**，即可即时切换。语言选择保存在本机，重启后继续生效。

首次使用时，根据系统首选语言选择界面语言。中文系统使用简体中文；已有用户保存的日语或英语选择会保留。此分支暂未提供繁体中文译文，中文地区的系统语言统一回退到简体中文。

本地化覆盖应用的导航、下载设置、创作者筛选、下载状态、媒体库、收藏、ZIP/PSD 查看器、Cookie 导入、定时下载及常规设置。站点内嵌网页、创作者姓名、帖子正文、文件名和原始服务端诊断消息保留原文。

## 使用

选择左侧站点并登录，勾选创作者、文件类型和时间范围，然后开始下载。程序会使用你已获得的访问权限下载内容。登录信息与下载记录保存在本机。

下载类型支持图片、视频、音频和附件。可选全部历史帖子、最近若干天、指定日期，或上次完整下载后的新帖子。已下载内容可跳过。

## 从源码运行

需要 Node.js 24 或更新版本，以及 npm。依赖版本以 `package-lock.json` 为准。

```bash
npm ci
npm run dev
```

检查及构建：

```bash
npm run lint
npm test
npm run build
```

`npm run build` 同时进行主进程和界面的 TypeScript 检查。Windows 便携版可使用以下命令打包，输出在 `release/`：

```bash
npm run build
npx electron-builder --win portable --x64 --publish never
```

## 翻译维护

- 中文字典：`src/renderer/src/design/locales/zh-CN.ts`。
- 语言选项及系统语言匹配：`src/renderer/src/design/language.ts`。
- `{name}`、`{n}`、`{postId}` 等占位符需要保持原样。
- `i18n.test.ts` 检查语言字典键名、占位符和系统语言匹配，避免界面缺字或显示未替换的变量。

更多功能、使用说明与开发规范见 [上游 README](README.md) 和 [贡献指南](CONTRIBUTING.md)。
