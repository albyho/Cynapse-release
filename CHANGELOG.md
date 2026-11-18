# Release Log

Cynapse Client, the VS Code Adapter, and the JupyterLab Adapter share one
version. New releases package the Client and JupyterLab Adapter in one versioned
Windows zip and publish the VS Code Adapter through the VS Code Marketplace.

## 0.5.0 — 2026-11-18

- Client: add a Sound settings page with a 0–100 narration volume slider,
  speaker icon, and numeric readout. Volume persists in ClientSettings and
  applies live; volume 0 keeps narration playing silently.
- Client Core: add the persisted narration volume setting and the runtime
  caption-edge flip helper.
- Client: hovering the caption flips it to the opposite edge for the rest of
  the run. Settings stays the default and the flip never writes back; the hover
  fade is removed, and cursor polling stops while the caption is hidden.
- Client: render warnings in a readable card with aligned icon and text.
- Adapters: share the check and connection runtime and extract the TypeScript
  kit used by the VS Code Adapter.
- Build and docs: skip stable gates for docs-only changes, record the TurboWarp
  Desktop adapter research and the adapter common layer design, and focus the
  VS Code Adapter READMEs on users.

Cynapse commit: `014e8fef`

### Downloads

- `cynapse-0.5.0-windows-x64.zip`

## 0.4.0 — 2026-11-18

- Client: manage the JupyterLab host supply and provisioning lifecycle, preflight
  Course Environments before workspace preparation, and keep local-only Units
  running when the Adapter disconnects.
- Client: harden the Protocol Server across Adapter changes, reset disconnects,
  and Action deadlines, and complete playback lifecycle logging.
- Client: compact the Challenge panel, split the sidebar height with it, add
  selectable hint and result text, add copy selection / copy all context menu
  actions, and support Ctrl+C / Command+C for the current selection.
- Courses: validate packages strictly in one read, report every package
  diagnostic from `verify:content`, and require captions on every narration
  clip. **Breaking:** narration clips without captions are now rejected.
- Adapters: share the VS Code chunked-edit transaction, preserve document
  encoding when saving and decoding check captures, allow environment-check
  terminals at the Course Workspace root, and bound JupyterLab CellRun ACK
  payloads.
- Docs and tooling: record the 2026-11-17 repository audit and architecture
  review, add ADR-0068, and move speech-edit tooling under `tools/`.

Cynapse commit: `4e9eaa45`

### Downloads

- `cynapse-0.4.0-windows-x64.zip`

## 0.3.0 — 2026-11-16

- Client: add JupyterLab course support, including Course Environment
  provisioning from `pyproject.toml` / `pylock.toml`, managed JupyterLab server
  lifecycle, visible Notebook/Cell/Kernel actions, and cancellation and restart
  handling.
- JupyterLab Adapter: first release of the prebuilt extension, with cell text
  editing, Cell range execution, output reveal, scroll alignment, and a
  long-running execution notice.
- Protocol: standardize action names to PascalCase and prefix JupyterLab
  actions; the Client and both adapters ship together.
- Courses: add the Chinese signal-processing roadmap course with the silent
  welcome demo, introduction, and Week 1 lessons, narration, and exercises.
- Build and release: publish the Client and JupyterLab Adapter together in
  `cynapse-0.3.0-windows-x64.zip`; rebuild stale development wheels; include
  `pyproject.toml` and `pylock.toml` in published JupyterLab courses.
- Docs: add JupyterLab design, course-authoring, and release workflow
  documentation, and update the project skills.

Cynapse commit: `2fa77d15`

### Downloads

- `cynapse-0.3.0-windows-x64.zip`

## 0.2.4 — 2026-11-15

- Client: version settings, preserve the caption background color, keep one
  course selection state, record course-switch interruption before open and
  close, use the next Unit's target source for prompts, and join warning labels
  with the localized separator.
- Client and Adapter: drop rare-failure recovery that warnings or defaults now
  cover.
- Courses and narration: cache shared audio assets during package load, clear
  removed narration track phases during assembly, reject symlinks and junctions
  while publishing, bundle resource git worktrees, and pin resource checkouts in
  `resources.lock.json`.
- Adapter: make reset and text-edit recovery replay-safe.
- Build: centralize the release version in the Cargo workspace and verify all
  declarations plus the tag in CI.
- Docs: close the audit follow-ups, record the JupyterLab Adapter design, and
  document course publishing plus the release and course publishing skills.

Cynapse commit: `40113a3f`

### Downloads

- `cynapse-client.exe`
- `cynapse-vscode-adapter.vsix`

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
