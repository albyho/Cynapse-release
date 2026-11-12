# Release Log

Cynapse Client and the VS Code Adapter share one version and are published
together.

## 0.2.1 — 2026-11-13

First release published from the private Cynapse repository to this repository.

- Client and Adapter versions are now aligned; both artifacts ship in the same
  GitHub Release.
- Adapter metadata and documentation now point to this repository.
- Adapter: end learning when a required adapter disconnects.
- Adapter: distinguish truncated terminal output from a real mismatch.
- Client: cache course projections, write persisted state atomically, and
  harden workspace reset.

### Downloads

- `cynapse-client.exe`
- `cynapse-vscode-adapter.vsix`
