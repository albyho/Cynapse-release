# Release Log

Cynapse Client, the VS Code Adapter, and the JupyterLab Adapter share one
version. New releases package the Client and JupyterLab Adapter in one versioned
Windows zip and publish the VS Code Adapter through the VS Code Marketplace.

## 0.8.0 — 2026-11-22

- Client: the course tree is denser and clearer — compact rows with tuned
  height, play/pause icons for Unit selection, Unit checkboxes with full
  breadcrumb paths, no progress dots or row highlight, and Reset as the only
  action on completed Units. Controls stay in sync with active playback, a
  stopped session's playback is no longer read as a wait, and the tray icon
  uses gpui-tray.
- Client Core: locale catalogs are split by owner.
- Courses: authored steps survive `build_course.py`; narration padding is
  trimmed with a compiler-error step added, and the Rust package gets denser
  narration with synthesized TTS.
- Build and docs: MSIX packaging for Microsoft Store (identity from
  `packaging/msix/identity.json`, `runFullTrust`), refreshed app icons across
  client and VS Code Marketplace, the JupyterLab Adapter is in spec scope,
  the interaction rules follow the new course tree, and Markdown checks move
  to rumdl. Release and course-publish flows are documented.
- Adapters: scratch probes renamed to `research`.

Cynapse commit: `2eadaa89`

### Downloads

- [`cynapse-0.8.0-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/tag/v0.8.0)

## 0.7.0 — 2026-11-20

- Client: the main window stays above other windows while a manual Next/Retry,
  next-Unit prompt, passive playback interruption, error, or adapter wait needs
  the learner; a hidden or minimized window is restored without focus, once per
  new wait. Stop now clears Challenge/human waits and topmost immediately.
  Continue replays from the Step's first Action but skips Wait Actions already
  reached; human/Challenge boundaries before the saved Action are not re-prompted.
- Client Core: persist the current Step's Action index at Stop, replay from the
  Step start, skip Waits up to that index, and remove the final-Wait Stop special
  case so Stop always pauses.
- Docs: update the interaction spec and course authoring guide for the replay
  and Wait-skip rules.

Cynapse commit: `74115045`

### Downloads

- [`cynapse-0.7.0-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/tag/v0.7.0)

## 0.6.1 — 2026-11-20

- Client: narration phases stay owned by the Unit that started them; playback
  preparation errors and course-switch restart failures are reported instead of
  leaving the session waiting; unit progress is scanned once per render; the main
  window is topmost only while a human Step waits.
- Client Core: pending requests get individual ACK deadlines; discovery cleanup
  is token-aware; Play is excluded from one-off requests; a failed next-Unit
  plan stops learning cleanly.
- Adapter: cancelled requests are bounded; in-flight actions and request IDs are
  deduplicated; VS Code and JupyterLab use the unified text-edit anchors
  (Protocol v3).
- Courses: the Rust and signal-processing packages move to PascalCase actions
  and the unified text-edit anchors.
- Docs and tooling: audit status checks, review gate scope, and the script
  reference are tightened; content-verifier cleanup and `--since` handling are
  hardened; Python test tooling is consolidated.

Cynapse commit: `54a1ec27`

### Downloads

- [`cynapse-0.6.1-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/tag/v0.6.1)

## 0.6.0 — 2026-11-19

- Client: keep the status bar text on one line; it now pans horizontally with
  no scrollbar instead of wrapping and growing the bar.
- Client: warnings carry a stable identity, so switching languages re-renders
  them in the new locale instead of keeping the old wording.
- Courses: parse caption markup in one pass, which fixes a stray `<` before a
  markup tag swallowing the following emphasis.
- Courses: add the English edition of the signal processing roadmap.
- Build and docs: move the scenario harness into its own crate, drop the
  VS Code forwarding shims, and add the local release skill.

Cynapse commit: `e386f42b`

### Downloads

- [`cynapse-0.6.0-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/tag/v0.6.0)

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

- [`cynapse-0.5.0-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/tag/v0.5.0)

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

- [`cynapse-0.4.0-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/tag/v0.4.0)

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

- [`cynapse-0.3.0-windows-x64.zip`](https://github.com/albyho/Cynapse-release/releases/tag/v0.3.0)

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

- [`cynapse-client.exe`](https://github.com/albyho/Cynapse-release/releases/tag/v0.2.4)
- [`cynapse-vscode-adapter.vsix`](https://github.com/albyho/Cynapse-release/releases/tag/v0.2.4)

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

- [`cynapse-client.exe`](https://github.com/albyho/Cynapse-release/releases/tag/v0.2.3)
- [`cynapse-vscode-adapter.vsix`](https://github.com/albyho/Cynapse-release/releases/tag/v0.2.3)

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

- [`cynapse-client.exe`](https://github.com/albyho/Cynapse-release/releases/tag/v0.2.2)
- [`cynapse-vscode-adapter.vsix`](https://github.com/albyho/Cynapse-release/releases/tag/v0.2.2)

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
