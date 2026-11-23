# Cynapse Releases

[English](README.md) | 简体中文

> **本仓库已归档。** 新版本发布在
> [albyho/Cynapse](https://github.com/albyho/Cynapse/releases)，下面的历史资产仍可
> 下载。

Cynapse（Code + Synapse）是一个本地优先的交互式软件教程与工作流平台。课程在真实
软件中驱动交互式 UI 与可恢复的分步状态机，让你边做边学，而不是看录屏，也不是在
模拟器上。首个支持平台是 Windows。

Cynapse 的源码与后续版本在 [albyho/Cynapse](https://github.com/albyho/Cynapse)。

## 下载

| 组件 | 下载 |
| --- | --- |
| Cynapse Client + JupyterLab Adapter（Windows x64） | [`cynapse-<version>-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/latest) |
| Cynapse VS Code Adapter | [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=tubumu.cynapse-vscode-adapter) |

所有版本也可在[发布页](https://github.com/albyho/Cynapse-release/releases)查看；
每个版本的变化见[版本记录](CHANGELOG.md)。

### Cynapse Client 与 JupyterLab Adapter

1. 从最新 Release 下载带版本号的 `cynapse-<version>-windows-x64.zip`。
2. 解压，并让 `cynapse-client.exe` 与 JupyterLab Adapter wheel 保持在同一个目录。
   不要直接在 zip 内运行 exe。
3. 运行 `cynapse-client.exe`。当前二进制未签名，Windows SmartScreen 可能提示风险；
   请仅在确认文件来自本仓库 Releases 时继续。
4. Client 目前以 Windows 为主要支持平台，其他平台仍在完善中。

zip 根目录包含 `cynapse_jupyterlab_extension-<version>-py3-none-any.whl`。Client 会在
JupyterLab 课程中自动使用它，不需要单独安装 Adapter。

### Cynapse VS Code Adapter

从 VS Code Marketplace 安装 **Cynapse VS Code Adapter**。

环境要求：

- VS Code `1.140.0` 或更高版本。
- 已安装并启动 Cynapse Client，且与 VS Code 运行在同一用户会话中。

Adapter 是 Client 的配套组件，不能单独播放课程。

## 示例课程

可直接打开的示例 Course Package 位于
[Cynapse Courses](https://github.com/albyho/Cynapse-courses)：

| 课程 | 版本 | 课程包 | 改编自 |
| --- | --- | --- | --- |
| 通过例子学 Rust（中文版） | `0.20.21` | [zip](https://github.com/albyho/Cynapse-courses/releases/tag/rust-by-example-zh-cn-0.20.21) | [Rust by Example（中文版）](https://github.com/rust-lang-cn/rust-by-example-cn) |
| agent-desktop 源码分析（中文版） | `0.39.0` | [zip](https://github.com/albyho/Cynapse-courses/releases/tag/agent-desktop-source-analysis-zh-cn-0.39.0) | [agent-desktop](https://github.com/vercel-labs/agent-desktop) |
| 信号处理路线图（中文版） | `0.2.4` | [zip](https://github.com/albyho/Cynapse-courses/releases/tag/signal-processing-roadmap-zh-cn-0.2.4) | [Signal processing roadmap](https://github.com/minthanthtoo/signal-processing-roadmap) |
| 信号处理路线图（英文版） | `0.2.4` | [zip](https://github.com/albyho/Cynapse-courses/releases/tag/signal-processing-roadmap-0.2.4) | [Signal processing roadmap](https://github.com/minthanthtoo/signal-processing-roadmap) |

下载课程 zip 并解压，得到 `<课程名>/` 目录，然后在 Cynapse Client 中打开该目录。
agent-desktop 的 zip 已包含固定版本的官方源码，无需配置 git submodule。

## 路线图

- 提供课程创作工具 `Cynapse Studio`。
- 增加更多示例课程。
- 支持 AI Agent。
- 支持 Accessibility Tree。
- 支持更多界面语言和课程内容本地化（i18n / L10n）。

## 许可证

Cynapse 发布产物使用 [MIT 许可证](LICENSE)。
