# Seam Runner — downloads and installation

This repository contains **published builds only** (installable Blender extensions). Source code and development happen elsewhere; you only need this repo to download releases.

Sign in to GitHub with the account the maintainer invited as a **collaborator** on this repository.

---

## What you need

| Item | Detail |
| --- | --- |
| **Operating system** | **Windows x64** (Phase 0A client testing) |
| **Blender (recommended)** | **5.2.2** — [download from blender.org](https://www.blender.org/download/) |
| **Blender (minimum)** | **4.5.0** (manifest minimum; use 5.2.x unless the maintainer says otherwise) |
| **GitHub** | Access to this private repo (maintainer adds your account) |

Each release may ship its own **RELEASE.md** and **TESTING.md** files—use those for version-specific notes.

---

## Download a release (step by step)

1. Open **https://github.com/alessandroiori/seam-runner-releases**
2. Click **Releases** (right side, or under the repo title).
3. Pick the version you need (e.g. **`v0.0.1`**).
4. Under **Assets**, download:
   - **`seam_runner-0.0.1.zip`** (or the zip named for that version)
   - Optional: **`seam_runner-0.0.1.zip.sha256`** for integrity check
   - **`RELEASE.md`** and **`TESTING.md`** for that version (same page)

If **Releases** is missing, ask the maintainer—the repository may not be initialized yet.

---

## Verify the zip (optional)

Compare the SHA-256 of the zip with the `.sha256` file from the same release.

**Windows (PowerShell):**

```powershell
Get-FileHash -Algorithm SHA256 .\seam_runner-0.0.1.zip
```

The hash should match the first column in the `.sha256` file.

**macOS / Linux:**

```bash
shasum -a 256 seam_runner-0.0.1.zip
```

---

## Install in Blender

1. Start **Blender** (preferably **5.2.2** on Windows).
2. **Edit → Preferences → Get Extensions**.
3. Click **Install from Disk…** (label may vary slightly by Blender version).
4. Select the downloaded **`.zip`** (do not unzip it first).
5. Enable **Seam Runner** if it is not already enabled.
6. If the panel does not appear, restart Blender once.

---

## Confirm the extension works

1. Open the **3D Viewport** (default layout is fine).
2. Press **N** to open the sidebar.
3. Find the **Seam Runner** tab/category.
4. The panel should show:
   - **Seam Runner**
   - **0.0.1** (or the version matching your release tag)

Phase **0.0.1** is a **shell** only: name and version in the panel. Mold/partition features come in later releases.

---

## Report your environment (acceptance test)

Follow **TESTING.md** on the release page. To capture Blender, Python, and NumPy versions, run this in Blender **Scripting → Run Script**:

```python
import sys
import bpy
import numpy

print(bpy.app.version_string, sys.version.split()[0], numpy.__version__)
```

Copy the **single line** of output and send it to the maintainer. Use **`numpy.__version__`** in scripts (not `numpy.version`).

---

## Current releases

| Tag | What it is |
| --- | --- |
| [**v0.0.1**](https://github.com/alessandroiori/seam-runner-releases/releases/tag/v0.0.1) | Installable shell: panel with product name and version **0.0.1** |

When a new tag appears under **Releases**, use that tag’s assets and attached **RELEASE.md** / **TESTING.md**.

---

## Something went wrong?

- **Cannot see the repo or Releases** — you may not be logged in, or the maintainer has not added your GitHub user as collaborator.
- **Install from disk fails** — confirm Blender is **4.5+**, try **5.2.2**, and use the exact `.zip` from the release (not a re-zipped folder).
- **No Seam Runner tab** — check **Get Extensions** that the add-on is enabled; restart Blender.

Contact the maintainer with: Blender version, steps you took, screenshots, and the Scripting one-liner output above.

---

## For maintainers (not for clients)

The canonical text of this file lives in the development repository: `docs/releases/DISTRIBUTION-README.md`. After editing, copy it to **`README.md`** on **`main`** in **seam-runner-releases** so clients see it on the repo home page.
