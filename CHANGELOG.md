# Release Log

Cynapse Client and the VS Code Adapter share one version and are published
together.

## 0.2.3 — 2026-11-14

- Client: add English and Simplified Chinese UI languages. Follow the Windows
  display language by default, switch immediately from the General page, and
  move Client-owned error and warning copy to a shared English-base catalog.
- Client: update the Course Tree through incremental Course Projection
  changes instead of rebuilding and cloning the whole course state.
- Client Core: index playback plans and Unit Steps, reuse one SQLite
  connection per Course Session, and avoid string-key allocation in Step
  lookups.
- Client: fail Unit and Course reset fast without staging, reset all course
  state when an unsupported legacy schema is found, and accept an explicit
  startup course.
- Courses: validate and stage packages before replacing them, detect resource
  submodules during publishing, add a clean course publisher, and correct a
  line pronunciation with a chapter intro.
- Docs: close the audit follow-ups, scope ADR-0060 to the GPUI host, and align
  terminology.
- Adapter: version aligned; no functional changes.

Cynapse commit: `5fd04bc1`

### Downloads

- `cynapse-client.exe`
- `cynapse-vscode-adapter.vsix`

## 0.2.2 — 2026-11-13

- Client: unify Next Step/Next Unit decisions, keep Continuous mode across
  human Unit boundaries, and fix final-Challenge advancement.
- Client: make Unit traversal and selection visible, show a busy state while
  resetting, and seek narration clips to their authored offsets.
- Client: refine Course Tree scrolling and width, make the breadcrumb
  horizontally scrollable, and keep the empty toolbar height stable.
- Client: move the challenge panel into its own view, use a collapsible hint
  row, and fade captions smoothly.
- Content: allow explicit human-step skips, reject unverified steps after a
  human boundary, and inspect only structured asset paths.
- Core/Model: reject linked workspace ancestors, remove the package-root
  workspace fallback, reset unsupported database schemas, cache Course Tree
  projections, and coalesce Step progress writes.
- Adapter: use the Client icon.

### Downloads

- `cynapse-client.exe`
- `cynapse-vscode-adapter.vsix`

## 0.2.1 — 2026-11-13

First release published from the private Cynapse repository to this repository.

- All workspace component versions are now aligned; both artifacts ship in the
  same GitHub Release.
- Adapter metadata and documentation now point to this repository.
- Adapter: end learning when a required adapter disconnects.
- Adapter: distinguish truncated terminal output from a real mismatch.
- Client: cache course projections, write persisted state atomically, and
  harden workspace reset.

### Downloads

- `cynapse-client.exe`
- `cynapse-vscode-adapter.vsix`
