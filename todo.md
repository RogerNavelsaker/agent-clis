# TODO

## Next Pass

- [ ] Convert repos with vendored upstream trees to explicit two-stage Nix packaging where stage 1 fetches the exact upstream source and stage 2 narrows to the package surface actually being built.
- [ ] Remove vendored upstream trees from repos once their packaging and sync lanes no longer depend on committed upstream source snapshots.
- [ ] Keep package manifests 1:1 with upstream identity while moving all packaging-specific behavior into Nix, wrappers, outputs, and package revision fields.

## Tier 1: Best Two-Stage Candidates

- [x] `nixpkg-context-mode-cli`: replace committed `upstream/` dependency with a two-stage fetch-and-package flow against the configured remote upstream.
- [x] `nixpkg-mcp-nixos-cli`: replace committed `upstream/` dependency with a two-stage fetch-and-package flow against the configured remote upstream.
- [x] `nixpkg-cass-memory-system`: replace vendored Node upstream with a two-stage source derivation so packaging only sees the app surface needed by `bun.nix`.
- [x] `nixpkg-overstory`: keep the compiled-binary packaging, but move fully to a two-stage upstream source derivation so no local or repo-root upstream baggage leaks into packaging.
- [x] `nixpkg-pi-coding-agent`: keep the compiled-binary packaging, but move fully to a two-stage upstream source derivation so only package runtime assets remain in scope.

## Tier 2: Rust Vendored Repos

- [x] `nixpkg-beads-rust`: replace vendored Rust source trees with remote upstream fetches and package-only source narrowing.
- [x] `nixpkg-cross-agent-session-resumer`: replace vendored Rust source tree with remote upstream fetch plus package-only source derivation.
- [x] `nixpkg-destructive-command-guard`: replace vendored Rust source tree with remote upstream fetch plus package-only source derivation.
- [x] `nixpkg-meta-skill`: replace vendored Rust source tree with remote upstream fetch plus package-only source derivation.
- [x] `nixpkg-pi-coding-agent-rust`: replace vendored Rust source tree with remote upstream fetch plus package-only source derivation.
- [x] `nixpkg-process-triage`: replace vendored Rust source tree with remote upstream fetch plus package-only source derivation.
- [x] `nixpkg-toon-rust`: replace vendored Rust source tree with remote upstream fetch plus package-only source derivation.

## Tier 3: Mixed-Language Vendored Repos

- [x] `nixpkg-beads-viewer`: replace vendored Go/Rust upstream trees with remote fetch plus package-only source staging.
- [x] `nixpkg-coding-agent-account-manager`: replace vendored Go/Node upstream trees with remote fetch plus package-only source staging.
- [x] `nixpkg-coding-agent-session-search`: replace vendored Rust/Python/Node upstream trees with remote fetch plus package-only source staging.
- [x] `nixpkg-mcp-agent-mail-rust`: replace vendored Rust/Node upstream trees with remote fetch plus package-only source staging.
- [x] `nixpkg-named-tmux-manager`: replace vendored Go/Node upstream trees with remote fetch plus package-only source staging.
- [x] `nixpkg-simultaneous-launch-button`: replace vendored Go upstream tree with remote fetch plus package-only source staging.
- [x] `nixpkg-ultimate-bug-scanner`: replace vendored Python upstream tree with remote fetch plus package-only source staging.

## Tier 4: Metadata And Sync Cleanup

- [ ] `nixpkg-automated-plan-reviser-pro`: confirm canonical upstream source and convert to explicit remote-source packaging if upstream code is still being mirrored locally.
- [ ] `nixpkg-code-intel-rust`: confirm canonical upstream source and move from metadata-only sync to packaging that fetches from the configured upstream directly.
- [ ] `nixpkg-code-intel-ts`: confirm canonical upstream source and move from metadata-only sync to packaging that fetches from the configured upstream directly.
- [ ] `nixpkg-repo-map`: confirm canonical upstream source and move from metadata-only sync to packaging that fetches from the configured upstream directly.
- [ ] `nixpkg-repo-updater`: confirm canonical upstream source and move from metadata-only sync to packaging that fetches from the configured upstream directly.

## Aligned Reference Patterns

- [x] `nixpkg-lean-ctx`: reference pattern for two-stage Rust packaging against an upstream repo that contains non-packaging CI and website baggage.
- [x] `nixpkg-gemini`: reference pattern for two-stage Bun packaging.
- [x] `nixpkg-claude-code`: reference pattern for preferring upstream native binaries.
- [x] `nixpkg-codex`: reference pattern for preferring upstream native binaries.
- [x] `nixpkg-canopy`: reference pattern for Bun single-executable packaging.
- [x] `nixpkg-mulch`: reference pattern for Bun single-executable packaging.
- [x] `nixpkg-seeds`: reference pattern for Bun single-executable packaging.
- [x] `nixpkg-trellis`: reference pattern for Bun single-executable packaging.
