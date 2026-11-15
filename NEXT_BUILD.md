# Next build work queue

This plan applies to the next release build of the `oriyano/Pinta` fork. It records planned work; none of the items below is marked complete. Keep all implementation and release activity in this fork under [AGENTS.md](AGENTS.md).

## Release-critical work

Complete and verify these items before marking the next release build ready.

- [ ] **Repeatable builds and installers.** Pin the .NET SDK used by developers and CI. Build on Windows, Linux, and macOS. For each packaged application, launch it and test opening, editing, saving, and reopening an image.
- [ ] **Crash recovery.** Design and implement recovery snapshots for dirty documents without overwriting the original image. Test a crash or forced exit, an interrupted save, a failed save, and recovery after restart.
- [ ] **Accessibility.** Audit keyboard-only use and focus order across the canvas, layers, tools, and dialogs. Give custom and icon-only controls accessible names and states. Verify behavior with relevant assistive technology on supported platforms.
- [ ] **Dependency and file safety.** Review size and resource limits for image imports and test malformed files. Enable NuGet vulnerability auditing and reproducible restores with package lock files. Review dependency updates before accepting them.
- [ ] **Large-image responsiveness.** Establish repeatable benchmarks for opening, zooming, painting, effects, and undo with representative large images. Improve measured bottlenecks and compare results to the baseline.

## Decisions and scoped upgrades

Resolve these during next-build planning. Implement them in the next build when the investigation yields a defined, testable change; otherwise record the decision and follow-up scope.

- [ ] **Color profiles.** Assess how imports and exports handle embedded profiles and color conversion. Define preservation and conversion behavior before changing the pipeline.
- [ ] **Flexible editing.** Gather concrete user needs for non-destructive or more flexible editing. Choose a first feature only after specifying its file-format, history, and UI behavior.
- [ ] **Fork identity.** If this fork will be installed alongside upstream Pinta, decide whether it needs its own application ID, settings location, icons, and file associations to avoid collisions.

## Release gate

- [ ] The release-critical work is implemented and verified on supported platforms.
- [ ] The scoped-upgrade decisions are recorded, and any deferred work is identified in the release notes.
- [ ] The fork-only policy is preserved; no changes are submitted to `PintaProject/Pinta`.
