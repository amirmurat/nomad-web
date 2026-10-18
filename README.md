# Nomad — iPhone Web Playtest

This public repository hosts **only compiled Godot Web export files**. The original game source remains private in `amirmurat/nomad`.

The game is exported using Godot 4.7.1, single-threaded WebGL 2 Compatibility. Touch controls are included for iPhone Safari.

**Status:** Publishing pipeline setup in progress. The live URL will be `https://amirmurat.github.io/nomad-web/` after the first successful deployment and Pages activation.

## Deployment architecture

1. The private game repository builds the real Godot project in GitHub Actions.
2. A narrowly scoped GitHub fine-grained personal access token authorizes the private workflow to push **only compiled `build/web/` files** to this public repository's `site` branch.
3. This public repository's Pages workflow publishes the `site` branch via GitHub Actions.

Do not copy game source code, credentials or repository metadata into this public repository. Web assets are inherently downloadable by site visitors.

To enable automated publishing, see `PUBLISH_SETUP.md`.
