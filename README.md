# Seam Runner

[![License: GPL-3.0-or-later](https://img.shields.io/badge/License-GPL--3.0--or--later-blue.svg)](LICENSE)
[![Latest release](https://img.shields.io/github/v/release/alessandroiori/seam-runner-releases?label=release)](https://github.com/alessandroiori/seam-runner-releases/releases/latest)

**Design multi-part 3D-printable molds with free partition lines** — Blender extension for SFX workflows: sculpt in **ZBrush**, mold layout and partition lines in **Blender**, export back to ZBrush when needed.

This repository publishes **installable builds only** (GitHub Releases). It is **public**; anyone can download releases. **Development source** lives in the private monorepo `seam-runner` (same license). **Maintainer:** Alessandro Iori.

---

## Table of contents

- [About](#about-seam-runner)
- [What you get today](#what-you-get-today-v007)
- [System requirements](#system-requirements)
- [License](#license-and-legal)
- [Download](#download-a-release)
- [Verify SHA-256](#verify-the-download-sha-256)
- [Install](#install-in-blender)
- [Quick start](#quick-start)
- [Testing](#acceptance-testing)
- [Troubleshooting](#troubleshooting)
- [Release history](#release-history)
- [Support](#support)

---

## About Seam Runner

- **Blender extension** (`seam_runner`) — UI and operators  
- **Geometry core** (`seam_runner_core`, bundled wheel) — NumPy, no Blender API  

Install the **pre-built zip** from **Releases**. You do not need Python or a compiler on your machine.

**GitHub access:** you do **not** need to be a repository collaborator to download from this **public** repo. The maintainer may invite a **client** as collaborator only for support or private mirrors — not automated agents or bots.

---

## What you get today (v0.0.7)

| Included | Not included yet |
| --- | --- |
| Installable extension zip | Flanges, blades, keys, full mold export |
| ZBrush **import / export** (OBJ, PLY, STL) | Valve split, ZBrush step-by-step guide |
| **Partition lines** — anchors, geodesic curve, surface snap, opening axis | extensions.blender.org listing |
| Project checklist, mm setup | Paid / commercial licensing |

Use **[TESTING.md](https://github.com/alessandroiori/seam-runner-releases/releases/latest)** on the release you install (latest recommended: **v0.0.7**).

---

## System requirements

| Item | Requirement |
| --- | --- |
| **OS (acceptance)** | **Windows x64** |
| **Blender (recommended)** | **[5.2.2](https://www.blender.org/download/)** |
| **Blender (minimum)** | **4.5.0** (extension manifest) |
| **Network** | To download Blender and release assets; add-on runs offline after install |

---

## License and legal

| Topic | Detail |
| --- | --- |
| **Extension** | [GPL-3.0-or-later](LICENSE) |
| **Third parties** | [NOTICES.md](./NOTICES.md) |
| **Blender** | Separate product; not affiliated with Blender Foundation |

GPL: you may request **corresponding source** for the extension from the maintainer (see NOTICES).

---

## Download a release

1. **[Releases](https://github.com/alessandroiori/seam-runner-releases/releases)** → open **v0.0.7** (or latest).
2. Under **Assets**, download:

   | Asset | Purpose |
   | --- | --- |
   | **`seam_runner-0.0.7.zip`** | Install in Blender |
   | **`seam_runner-0.0.7.zip.sha256`** | Optional integrity check |
   | **`RELEASE.md`**, **`TESTING.md`** | Notes and checklist |

   Use **`seam_runner-….zip`**, not GitHub’s auto-generated **“Source code (zip)”** (that is this repo’s README/LICENSE snapshot, not the add-on).

3. CLI: `gh release download v0.0.7 -R alessandroiori/seam-runner-releases`

---

## Verify the download (SHA-256)

**Windows (PowerShell):** `Get-FileHash -Algorithm SHA256 .\seam_runner-0.0.7.zip`  
**macOS / Linux:** `shasum -a 256 seam_runner-0.0.7.zip`

Match the `.sha256` file from the **same** release.

---

## Install in Blender

1. Install **[Blender 5.2.2](https://www.blender.org/download/)** (or maintainer-approved version).
2. **Edit → Preferences → Get Extensions → Install from Disk…**
3. Select **`seam_runner-0.0.7.zip`** — **do not unzip**.
4. Enable **Seam Runner**; restart Blender if the sidebar tab is missing.

---

## Quick start

1. **3D Viewport** → **N** → **Seam Runner**.
2. **Project → Set up project (mm)** (or import with **Millimetres on import**).
3. **Import → Import from ZBrush** (OBJ / PLY / STL).
4. **Lines → Add partition line → Edit anchors** (Enter to rebuild).
5. Optional: **Export to ZBrush**.

Panel should show **Seam Runner** and version **0.0.7** (matches the zip you installed).

---

## Acceptance testing

Follow **`TESTING.md`** on the release page without maintainer assistance, then report results.

```python
import sys
import bpy
import numpy

print(bpy.app.version_string, sys.version.split()[0], numpy.__version__)
```

Send the maintainer that **one line**.

---

## Troubleshooting

| Problem | What to try |
| --- | --- |
| **Wrong download** | Use **`seam_runner-X.Y.Z.zip`**, not “Source code (zip)”. |
| **Browser blocked download** | Releases page, another browser, or `gh release download`. |
| **Install fails** | Blender ≥ 4.5; unmodified zip; try 5.2.2. |
| **Wrong panel version** | Reinstall from the correct release tag. |

---

## Release history

| Version | Summary |
| --- | --- |
| [**v0.0.7**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.7) | Curved-mesh testing path; same features as 0.0.6 |
| [**v0.0.6**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.6) | Checklist, mm on import, shared nodes, surface projection |
| [**v0.0.5**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.5) | Partition lines MVP |
| [**v0.0.4**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.4) | ZBrush export |
| [**v0.0.3**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.3) | ZBrush import |
| [**v0.0.2**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.2) | Engine contract, panel foundations |
| [**v0.0.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.1) | Installable shell |

Tag **`v0.0.7`** → panel **0.0.7**.

---

## Support

**Alessandro Iori** — see `maintainer` in the installed extension manifest or **`RELEASE.md`** on the release.

Canonical copies of this README, LICENSE, and NOTICES: development repo `docs/releases/` (maintainer syncs to this repo when needed).
