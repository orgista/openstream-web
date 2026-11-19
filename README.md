<div align="center">

<img src=".github/assets/openstream-icon.png" alt="OpenStream icon" width="96">

# OpenStream Web

**The OpenStream web app, local media gateway and smart TV packages.**

[![CI](https://img.shields.io/github/actions/workflow/status/orgista/openstream-web/ci.yml?branch=main&style=flat-square&label=CI)](https://github.com/orgista/openstream-web/actions/workflows/ci.yml)
[![OpenSSF Scorecard](https://api.scorecard.dev/projects/github.com/orgista/openstream-web/badge)](https://scorecard.dev/viewer/?uri=github.com/orgista/openstream-web)
[![License: Apache-2.0](https://img.shields.io/badge/license-Apache%202.0-2ea44f?style=flat-square)](LICENSE)
[![Platforms](https://img.shields.io/badge/platforms-Web%20%C2%B7%20webOS%20%C2%B7%20Tizen%20%C2%B7%20Roku-1c1e20?style=flat-square)](#whats-here)

[orgista.com/openstream](https://orgista.com/openstream) · [Build from source](#build-from-source) · [Security](SECURITY.md) · [Apple apps](https://github.com/orgista/openstream-apple)

</div>

---

OpenStream plays media you own: your Jellyfin, Emby or Plex server, network shares (SMB), files on your device, and the
live TV playlist and guide your TV provider gives you. OpenStream does not provide, host or recommend any content; it
starts empty and plays only what you connect.

## What's here

- **`src/`** — the React web app: library, details, live TV guide, Kids Mode, player and an immersive XR viewer.
- **`server/`** — the loopback media gateway: NAS folders with range streaming, local ffmpeg transcoding, metadata and redacted logs.
- **`native/smart-tv`, `native/roku`** — TV packages built from the web app.
- **`scripts/`** — QA, TV packaging and metadata helpers.

## Build from source

You need Node 20 or newer and pnpm 10.

```bash
git clone https://github.com/orgista/openstream-web.git && cd openstream-web
pnpm install --frozen-lockfile
pnpm test
pnpm dev        # Vite plus the loopback gateway; open the launch URL it prints
pnpm build
node scripts/build-tv-packages.mjs   # smart TV staging packages
```

More in [docs/development.md](docs/development.md).

## Releases

- **Versions** follow [Semantic Versioning](https://semver.org/). A version with a suffix (`v1.4.0-beta.1`) is a pre-release.
- **Cadence:** a release when a change is ready, and at least one maintenance release a month while the project is in active development. Security fixes ship within 7 days of a confirmed report.
- **Every release** gets a `SHA256SUMS` file and a GitHub build attestation.
- **Support:** only the latest release gets fixes.

This repository is a public copy of the source, updated with each release. Full policy:
[orgista release process](https://github.com/orgista/.github/blob/main/RELEASING.md).

## Contributing

Issues and pull requests are welcome. See [CONTRIBUTING](https://github.com/orgista/.github/blob/main/CONTRIBUTING.md)
and the [Code of Conduct](https://github.com/orgista/.github/blob/main/CODE_OF_CONDUCT.md). Changes should pass CI.

## License

Apache-2.0. See [LICENSE](LICENSE). The OpenStream name and icon are not covered by the license.
