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
| Cynapse Client (Windows x64) | [`cynapse-client.exe`](https://github.com/albyho/Cynapse-release/releases/latest/download/cynapse-client.exe) |
| Cynapse VS Code Adapter | [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=tubumu.cynapse-vscode-adapter) · [`.vsix`](https://github.com/albyho/Cynapse-release/releases/latest/download/cynapse-vscode-adapter.vsix) |

All versions are also available from the
[releases page](https://github.com/albyho/Cynapse-release/releases). See the
[release log](CHANGELOG.md) for changes in each version.

### Cynapse Client

1. Download `cynapse-client.exe`.
2. Run it. The binary is currently unsigned, so Windows SmartScreen may show a
   warning; only bypass it if the file came from this repository's Releases.
3. The Client is Windows-first. Other platforms are still being completed.

### Cynapse VS Code Adapter

Install **Cynapse VS Code Adapter** from the Marketplace, or install a
downloaded `.vsix`:

```powershell
code --install-extension cynapse-vscode-adapter.vsix
```

Requirements:

- VS Code `1.140.0` or newer.
- Cynapse Client installed and running in the same user session.

The Adapter is a companion to the Client and cannot play a course on its own.

## Sample courses

Ready-to-open example Course Packages are available in
[Cynapse Courses](https://github.com/albyho/Cynapse-courses):

- [rust-by-example](https://github.com/albyho/Cynapse-courses/tree/main/rust-by-example)
  ([*Rust by Example*](https://rustwiki.org/zh-CN/rust-by-example/))
- [agent-desktop-source-analysis](https://github.com/albyho/Cynapse-courses/tree/main/agent-desktop-source-analysis)
  ([agent-desktop](https://github.com/vercel-labs/agent-desktop/))

The agent-desktop course fetches its pinned official source as a git submodule.

## Roadmap

- Add [`JupyterLab`](https://jupyter.org/) support.
- Ship `Cynapse Studio`, the course authoring application.
- Add more sample courses.

## License

Cynapse releases are distributed under the [MIT License](LICENSE).
