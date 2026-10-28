# Seam Runner

[![License: GPL-3.0-or-later](https://img.shields.io/github/license/alessandroiori/seam-runner-releases?label=License)](LICENSE)
[![Latest release: v1.5.1](https://img.shields.io/github/v/release/alessandroiori/seam-runner-releases?label=Latest%20release&color=007ec6)](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v1.5.1)
[![Extension](https://img.shields.io/badge/extension-1.5.1-informational)](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v1.5.1)
[![Core](https://img.shields.io/badge/core-0.0.21-informational)](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v1.5.1)

**Design multi-part 3D-printable molds with free partition lines** — Blender extension for SFX workflows: sculpt in **ZBrush**, mold layout and partition lines in **Blender**, export back to ZBrush when needed.

This repository publishes **installable builds only** (GitHub Releases). It is **public**; anyone can download releases. **Development source** lives in the private monorepo `seam-runner` (same license). **Maintainer:** Alessandro Iori.

---

## Table of contents

- [About](#about-seam-runner)
- [What you get today](#what-you-get-today-v151)
- [System requirements](#system-requirements)
- [License](#license-and-legal)
- [Download](#download-a-release)
- [Verify SHA-256](#verify-the-download-sha-256)
- [Install](#install-in-blender)
- [Quick start](#quick-start)
- [Testing](#acceptance-testing)
- [Troubleshooting](#troubleshooting)
- [Release history](#release-history)
- [Authors](#authors)
- [Support](#support)

---

## About Seam Runner

- **Blender extension** (`seam_runner`) — UI and operators
- **Geometry core** (`seam_runner_core`, bundled wheel) — NumPy, no Blender API

Install the **pre-built zip** from **Releases**. You do not need Python or a compiler on your machine.

**GitHub access:** you do **not** need to be a repository collaborator to download from this **public** repo. The maintainer may invite a **client** as collaborator only for support or private mirrors — not automated agents or bots.

---

## What you get today (v1.5.1)

**Federico workflow release** — blade sporgenza, rinforzo cilindrico, preset numerico, bulloni su mesh flangia (from **1.5.0**), import unità file. See **`RELEASE.md`** and **`TESTING.md`** on the release.

| Included | Not included yet |
| --- | --- |
| **Build full layout**, **extend flange**, **apply to rims**, **Build reinforcement** | Optional flange subdiv in-panel (**1.5.2**) |
| **Blade extend** (10 mm default) + Solidify 0.3 mm | Full Stampi-only operators |
| **Apply Federico preset**; **Alt+right-click** remove anchor | Silicone volume, Pro licensing (Fase 2+) |
| ZBrush import/export, mold bundle, file **unit** selector (Slice B/D9) | Windows sign-off for Alt+RMB (macOS tested) |
| Mesh bolt band + core **0.0.21** (Blender 5.2 / Python 3.13) | |

Use **[TESTING.md](https://github.com/alessandroiori/seam-runner-releases/releases/latest)** on the release you install (latest installable: **v1.5.1**). After install: **enable Seam Runner** in **Preferences → Extensions**, then **quit Blender completely** and reopen (loads bundled core).

---

## System requirements

| Item | Requirement |
| --- | --- |
| **OS (acceptance)** | **Windows x64** (same zip also installs on **macOS** and **Linux**) |
| **Blender (recommended)** | **[5.2.3 LTS](https://www.blender.org/download/)** (acceptance); manifest min **4.5.0** |
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

1. **[Releases](https://github.com/alessandroiori/seam-runner-releases/releases)** → open **v1.5.1** (or latest with a **`seam_runner-*.zip`** asset).
2. Under **Assets**, download:

   | Asset | Purpose |
   | --- | --- |
   | **`seam_runner-1.5.1.zip`** | Install in Blender |
   | **`seam_runner-1.5.1.zip.sha256`** | Optional integrity check |
   | **`RELEASE.md`**, **`TESTING.md`** | Notes and checklist |

   Use **`seam_runner-….zip`**, not GitHub’s auto-generated **“Source code (zip)”** (that is this repo’s README/LICENSE snapshot, not the add-on).

3. CLI: `gh release download v1.5.1 -R alessandroiori/seam-runner-releases`

---

## Verify the download (SHA-256)

**Windows (PowerShell):** `Get-FileHash -Algorithm SHA256 .\seam_runner-1.5.1.zip`
**macOS / Linux:** `shasum -a 256 seam_runner-1.5.1.zip`

Match the `.sha256` file from the **same** release.

---

## Install in Blender

1. Install **[Blender 5.2.x LTS](https://www.blender.org/download/)** (or maintainer-approved version).
2. **Edit → Preferences → Get Extensions → Install from Disk…**
3. Select **`seam_runner-1.5.1.zip`** — **do not unzip**.
4. **Enable Seam Runner** in **Preferences → Extensions**.
5. **Quit Blender completely** and reopen (loads bundled core **0.0.21**).

---

## Quick start

1. **3D Viewport** → **N** → **Seam Runner**.
2. **Project → Set up project (mm)** (or import with **Millimetres on import**).
3. **Import → Import from ZBrush** (OBJ / PLY / STL); set **File unit** if needed.
4. **Lines → Add partition line → Edit anchors** (Enter to rebuild; **Alt+right-click** to remove an anchor).
5. **Flanges → Apply Federico preset** (optional) → **Build full layout** (or step through parts).
6. **Build reinforcement** after bolts; **Import → Export mold bundle**.

Panel should show **Seam Runner 1.5.1** and **Core 0.0.21** (after restart).

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
| **Install fails** | Blender ≥ 4.5; unmodified zip; try 5.2.x LTS. |
| **Extension not in panel** | **Preferences → Extensions** → enable **Seam Runner**. |
| **Core version banner** | Quit Blender fully after install/update; reinstall zip if needed. |
| **Wrong panel version** | Reinstall from the correct release tag. |

---

## Release history

| Version | Summary |
| --- | --- |
| [**v1.5.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v1.5.1) | Blade ext, reinforcement, Federico preset, Alt+RMB anchors; core **0.0.21** |
| **v1.5.0** (monorepo only; install **v1.5.1**) | Mesh bolt band, import file units; core **0.0.20** |
| [**v1.4.4**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v1.4.4) | Apply hide, legacy extend message, in-memory core restart banner; core **0.0.15** |
| [**v1.1.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v1.1.0) | Join rims + valve gap; TESTING A–M; core 0.0.12 |
| [**v1.0.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v1.0.0) | **Fase 1 exit** — B12.9 discard internal, TESTING A–K |
| [**v0.10.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.10.0) | Rim trim reliability (solver fallback, clearance mm) |
| [**v0.9.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.9.0) | Rim trim MVP + D01 hollow heuristic |
| [**v0.8.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.8.1) | Flange aligned to bisect plane (~5 mm fix) |
| [**v0.8.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.8.0) | Consolidated B12 acceptance TESTING |
| [**v0.5.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.5.0) | **B12 experimental** — Extract valves |
| [**v0.4.2**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.4.2) | Inner depth 3 mm; setup mm preserves custom lengths |
| [**v0.4.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.4.1) | Hotfix — mm defaults, POLY curves, Solidify, export warnings |
| [**v0.4.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.4.0) | **Layout milestone** — one TESTING, build full layout |
| [**v0.3.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.3.1) | **B08–B09** keys and bolts |
| [**v0.3.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.3.0) | **B10** mold bundle export |
| [**v0.2.2**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.2.2) | **B07** rim A/B from flange |
| [**v0.2.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.2.1) | Inner depth, node weld, **B06** blade |
| [**v0.2.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.2.0) | **B05** adaptive flange sheet |
| [**v0.1.0**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.1.0) | **Phase 1** — full TESTING walkthrough + checklist |
| [**v0.0.9**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.9) | Line refine + fast surface projection on large meshes |
| [**v0.0.7**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.7) | Curved-mesh testing path; same features as 0.0.6 |
| [**v0.0.6**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.6) | Checklist, mm on import, shared nodes, surface projection |
| [**v0.0.5**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.5) | Partition lines MVP |
| [**v0.0.4**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.4) | ZBrush export |
| [**v0.0.3**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.3) | ZBrush import |
| [**v0.0.2**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.2) | Engine contract, panel foundations |
| [**v0.0.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.1) | Installable shell |

Latest installable tag **`v1.5.1`** → panel **1.5.1**, core **0.0.21**.

---

## Authors

Original software authors (development history lives in the private monorepo).

| Name | GitHub |
| --- | --- |
| **Alessandro Iori** (maintainer) | [@alessandroiori](https://github.com/alessandroiori) |
| **Federico Iori** | [@federicoiori95-debug](https://github.com/federicoiori95-debug) |

---

## Support

**Alessandro Iori** — see `maintainer` in the installed extension manifest or **`RELEASE.md`** on the release.

Canonical copies of this README, LICENSE, and NOTICES: development repo `docs/releases/` (maintainer syncs to this repo when needed).
