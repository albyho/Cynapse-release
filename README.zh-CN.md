# Cynapse Releases

[English](README.md) | 简体中文

Cynapse（Code + Synapse）是一个本地优先的交互式软件教程与工作流平台。课程在真实
软件中驱动交互式 UI 与可恢复的分步状态机，让你边做边学，而不是看录屏，也不是在
模拟器上。首个支持平台是 Windows。

本仓库只分发 Cynapse 的发布产物。源码仓库为私有仓库，这里不发布源代码。

## 下载

| 组件 | 下载 |
| --- | --- |
| Cynapse Client（Windows x64） | [`cynapse-client.exe`](https://github.com/albyho/Cynapse-release/releases/latest/download/cynapse-client.exe) |
| Cynapse VS Code Adapter | [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=tubumu.cynapse-vscode-adapter) · [`.vsix`](https://github.com/albyho/Cynapse-release/releases/latest/download/cynapse-vscode-adapter.vsix) |

所有版本也可在[发布页](https://github.com/albyho/Cynapse-release/releases)查看；
每个版本的变化见[版本记录](CHANGELOG.md)。

### Cynapse Client

1. 下载 `cynapse-client.exe`。
2. 直接运行。当前二进制未签名，Windows SmartScreen 可能提示风险；请仅在确认文件
   来自本仓库 Releases 时继续。
3. Client 目前以 Windows 为主要支持平台，其他平台仍在完善中。

### Cynapse VS Code Adapter

从 VS Code Marketplace 安装 **Cynapse VS Code Adapter**，或安装下载的 `.vsix`：

```powershell
code --install-extension cynapse-vscode-adapter.vsix
```

环境要求：

- VS Code `1.140.0` 或更高版本。
- 已安装并启动 Cynapse Client，且与 VS Code 运行在同一用户会话中。

Adapter 是 Client 的配套组件，不能单独播放课程。

## 示例课程

可直接打开的示例 Course Package 位于
[Cynapse Courses](https://github.com/albyho/Cynapse-courses)：

- [rust-by-example](https://github.com/albyho/Cynapse-courses/tree/main/rust-by-example)
  （[*Rust by Example*](https://rustwiki.org/zh-CN/rust-by-example/)）
- [agent-desktop-source-analysis](https://github.com/albyho/Cynapse-courses/tree/main/agent-desktop-source-analysis)
  （[agent-desktop](https://github.com/vercel-labs/agent-desktop/)）

agent-desktop 课程通过 git submodule 获取固定版本的官方源码。

## 路线图

- 支持 [`JupyterLab`](https://jupyter.org/)。
- 提供课程创作工具 `Cynapse Studio`。
- 增加更多示例课程。
- 支持 AI Agent。

## 许可证

Cynapse 发布产物使用 [MIT 许可证](LICENSE)。
