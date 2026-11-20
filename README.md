# Cynapse Releases

English | [简体中文](README.zh-CN.md)

Cynapse (Code + Synapse) is a local-first interactive software tutorial and
workflow platform. Courses drive an interactive UI and a recoverable step state
machine while you work in the real application, instead of watching a
recording or using a simulator. Windows is the first supported platform.

This repository distributes Cynapse release artifacts. The source repository is
private; no source code is published here.

## Downloads

| Component | Download |
| --- | --- |
| Cynapse Client + JupyterLab Adapter (Windows x64) | [`cynapse-<version>-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/latest) |
| Cynapse VS Code Adapter | [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=tubumu.cynapse-vscode-adapter) |

All versions are also available from the
[releases page](https://github.com/albyho/Cynapse-release/releases). See the
[release log](CHANGELOG.md) for changes in each version.

### Cynapse Client and JupyterLab Adapter

1. Download the versioned `cynapse-<version>-windows-x64.zip` from the latest
   release.
2. Extract it and keep `cynapse-client.exe` and the JupyterLab Adapter wheel in
   the same directory. Do not run the executable from inside the zip.
3. Run `cynapse-client.exe`. The binary is currently unsigned, so Windows
   SmartScreen may show a warning; only bypass it if the file came from this
   repository's Releases.
4. The Client is Windows-first. Other platforms are still being completed.

The zip includes `cynapse_jupyterlab_extension-<version>-py3-none-any.whl`
beside the executable. The Client uses it automatically for JupyterLab courses;
no separate Adapter installation is required.

### Cynapse VS Code Adapter

Install **Cynapse VS Code Adapter** from the VS Code Marketplace.

Requirements:

- VS Code `1.140.0` or newer.
- Cynapse Client installed and running in the same user session.

The Adapter is a companion to the Client and cannot play a course on its own.

## Sample courses

Ready-to-open example Course Packages are available in
[Cynapse Courses](https://github.com/albyho/Cynapse-courses):

| Course | Version | Package | Source |
| --- | --- | --- | --- |
| 通过例子学 Rust（中文版） | `0.20.17` | [`rust-by-example-zh-cn/`](https://github.com/albyho/Cynapse-courses/tree/main/rust-by-example-zh-cn/) | [Rust by Example（中文版）](https://github.com/rust-lang-cn/rust-by-example-cn) |
| agent-desktop 源码分析 | `0.39.0` | [`agent-desktop-source-analysis-zh-cn/`](https://github.com/albyho/Cynapse-courses/tree/main/agent-desktop-source-analysis-zh-cn/) | [agent-desktop](https://github.com/vercel-labs/agent-desktop) |
| 信号处理路线图（中文版） | `0.2.4` | [`signal-processing-roadmap-zh-cn/`](https://github.com/albyho/Cynapse-courses/tree/main/signal-processing-roadmap-zh-cn/) | [Signal processing roadmap](https://github.com/minthanthtoo/signal-processing-roadmap) |
| 信号处理路线图（英文版） | `0.2.4` | [`signal-processing-roadmap/`](https://github.com/albyho/Cynapse-courses/tree/main/signal-processing-roadmap/) | [Signal processing roadmap](https://github.com/minthanthtoo/signal-processing-roadmap) |

The agent-desktop course fetches its pinned official source as a git submodule.

## Roadmap

- Ship `Cynapse Studio`, the course authoring application.
- Add more sample courses.
- Add AI agent support.
- Add Accessibility Tree support.
- Add more UI languages and course-content localization (i18n / L10n).

## License

Cynapse releases are distributed under the [MIT License](LICENSE).
