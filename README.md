# Seam Runner

[![License: GPL-3.0-or-later](https://img.shields.io/badge/License-GPL--3.0--or--later-blue.svg)](LICENSE)
[![Latest release](https://img.shields.io/github/v/release/alessandroiori/seam-runner-releases?label=release)](https://github.com/alessandroiori/seam-runner-releases/releases/latest)

**Design multi-part 3D-printable molds with free partition lines** — a Blender extension for practical effects (SFX) workflows: high-resolution sculpts in **ZBrush**, mold layout and lightweight cutters in **Blender**, boolean work back in ZBrush on the original mesh.

This repository publishes **installable builds only** (GitHub Releases). It is **private**; the maintainer grants GitHub access to clients and collaborators. Development source is maintained separately under the same license ([GPL-3.0-or-later](LICENSE)).

---

## Table of contents

- [About Seam Runner](#about-seam-runner)
- [What you get today (v0.0.1)](#what-you-get-today-v001)
- [System requirements](#system-requirements)
- [License and legal](#license-and-legal)
- [Get access](#get-access)
- [Download a release](#download-a-release)
- [Verify the download (SHA-256)](#verify-the-download-sha-256)
- [Install in Blender](#install-in-blender)
- [Quick start](#quick-start)
- [Acceptance testing](#acceptance-testing)
- [Troubleshooting](#troubleshooting)
- [Release history](#release-history)
- [Support](#support)

---

## About Seam Runner

Seam Runner helps you plan **rigid, multi-part 3D-printable molds** by drawing **partition lines** on a mesh surface in Blender. The product separates:

- A **pure-Python core** (`seam_runner_core`, NumPy, no Blender API) for geometry logic
- A **Blender extension** (`seam_runner`) for UI and operators

You install the **pre-built extension zip** from this repository’s **Releases** page. You do **not** need Python, `pip`, or a compiler on your machine.

---

## What you get today (v0.0.1)

| Included in **v0.0.1** | Not included yet |
| --- | --- |
| Installable extension zip | Partition lines, flanges, blades, keys |
| Sidebar panel with product **name** and **version** | Accounts, licensing gates, paid features |
| Documented install and test checklist | Public listing on extensions.blender.org |

Treat **v0.0.1** as a **Phase 0A shell**: confirm install and UI before mold features ship in later versions.

---

## System requirements

| Item | Requirement |
| --- | --- |
| **OS (client acceptance)** | **Windows x64** |
| **Blender (recommended)** | **[5.2.2](https://www.blender.org/download/)** — reference version at release time |
| **Blender (minimum)** | **4.5.0** (declared in extension manifest) |
| **Hardware** | Same as Blender for your projects |
| **Network** | Internet to download Blender and GitHub release assets; the add-on does not require online access for **v0.0.1** |
| **GitHub account** | Required to access this **private** repository |

Use the **exact Blender patch** the maintainer confirms for your milestone (often **5.2.2**). Newer **5.2.x** patches may work but should be reported during acceptance testing.

---

## License and legal

| Topic | Detail |
| --- | --- |
| **Extension license** | [GNU General Public License v3.0 or later](LICENSE) (`SPDX:GPL-3.0-or-later`) |
| **Full license text** | [LICENSE](./LICENSE) in this repository |
| **Bundled components & runtime deps** | [NOTICES.md](./NOTICES.md) |
| **Blender** | Separate download; governed by Blender’s license. **Seam Runner** is not affiliated with the Blender Foundation. |

If you received only a zip file, you may still request **corresponding source** for GPL-covered parts from the maintainer (see [NOTICES.md](./NOTICES.md)).

---

## Get access

1. Ask the maintainer to add your **GitHub username** as a **collaborator** on **seam-runner-releases** (this repo only — not the development monorepo).
2. Sign in to GitHub in your browser.
3. Open **https://github.com/alessandroiori/seam-runner-releases** — you should see this README and **Releases**.

---

## Download a release

1. Go to **[Releases](https://github.com/alessandroiori/seam-runner-releases/releases)** (or use the badge above).
2. Open the version you need (e.g. **[v0.0.1](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.1)**).
3. Under **Assets**, download:

   | Asset | Purpose |
   | --- | --- |
   | **`seam_runner-0.0.1.zip`** | Blender extension (install from disk) |
   | **`seam_runner-0.0.1.zip.sha256`** | Optional integrity check |
   | **`RELEASE.md`** | Version-specific install notes |
   | **`TESTING.md`** | Acceptance checklist |

4. Prefer **Releases** over CI artifacts for production client installs (stable link, attached docs).

**Browser blocked the download?** Use [GitHub CLI](https://cli.github.com/):  
`gh release download v0.0.1 -R alessandroiori/seam-runner-releases`

---

## Verify the download (SHA-256)

Compare the hash of the zip with the `.sha256` file from the **same** release.

**Windows (PowerShell):**

```powershell
Get-FileHash -Algorithm SHA256 .\seam_runner-0.0.1.zip
```

**macOS / Linux:**

```bash
shasum -a 256 seam_runner-0.0.1.zip
```

The digest must match the first field in the `.sha256` file.

---

## Install in Blender

1. Install **[Blender 5.2.2](https://www.blender.org/download/)** (or maintainer-approved version) on **Windows x64**.
2. Start Blender.
3. **Edit → Preferences → Get Extensions**.
4. **Install from Disk…** (wording may vary slightly).
5. Select **`seam_runner-0.0.1.zip`** — **do not unzip** the extension archive yourself.
6. Enable **Seam Runner** if it is disabled.
7. Restart Blender once if the sidebar tab does not appear.

Detailed notes for this version: open **`RELEASE.md`** on the release page.

---

## Quick start

After install:

1. Open the **3D Viewport** (default layout is fine).
2. Press **N** to open the sidebar.
3. Open the **Seam Runner** tab.
4. Confirm the panel shows:
   - **Seam Runner**
   - **0.0.1**

No other buttons or mold tools are expected in **v0.0.1**.

---

## Acceptance testing

Follow **`TESTING.md`** on the release page **without assistance** from the maintainer, then report results.

Capture Blender, Python, and NumPy versions — Blender **Scripting → Run Script**:

```python
import sys
import bpy
import numpy

print(bpy.app.version_string, sys.version.split()[0], numpy.__version__)
```

Send the maintainer the **one line** of output. Use **`numpy.__version__`** (not `numpy.version`).

---

## Troubleshooting

| Problem | What to try |
| --- | --- |
| **Cannot see repo or Releases** | Log in to GitHub; confirm collaborator invite on **seam-runner-releases**. |
| **Browser: “Dangerous download blocked”** | Use **Releases** download, another browser, or `gh release download`. |
| **Install from disk fails** | Blender **≥ 4.5**; use the unmodified release zip; try **5.2.2**. |
| **No Seam Runner tab** | Enable extension in **Get Extensions**; restart Blender. |
| **Wrong version in panel** | You may have installed an older zip — download the correct tag from **Releases**. |

Include screenshots, exact Blender version, and the Scripting one-liner when contacting support.

---

## Release history

| Version | Summary |
| --- | --- |
| [**v0.0.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.1) | Phase 0A shell — installable extension, name/version panel |

Semantic versioning: **`vMAJOR.MINOR.PATCH`** tags match the extension version without the `v` prefix (tag **`v0.0.1`** → panel **0.0.1**).

---

## Support

Contact the **maintainer** named in the release **`RELEASE.md`** or in the extension manifest (`maintainer` field inside the installed add-on).

For maintainers: canonical copies of this README, [LICENSE](./LICENSE), and [NOTICES.md](./NOTICES.md) live in the development repository under `docs/releases/` — sync them to this repo when requirements or legal notices change.
