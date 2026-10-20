# Third-party and runtime notices

Seam Runner is licensed under **GNU General Public License v3.0 or later** (`SPDX:GPL-3.0-or-later`). See [LICENSE](./LICENSE).

## Components shipped inside the extension zip

| Component | Role | License |
| --- | --- | --- |
| **Seam Runner** add-on (`seam_runner`) | Blender UI shell and extension metadata | GPL-3.0-or-later |
| **seam_runner_core** Python wheel | Pure-Python core bundled in the zip | GPL-3.0-or-later (same work) |

The zip is built so it does **not** bundle NumPy or other third-party Python wheels; those come from the Blender installation at runtime.

## Runtime dependencies (not included in the zip)

You must install these separately:

| Software | Role | License (typical) |
| --- | --- | --- |
| **[Blender](https://www.blender.org/)** | Host application | GPL-3.0-or-later (Blender) |
| **Python** | Embedded in Blender | PSF License |
| **NumPy** | Bundled with Blender’s Python | BSD-3-Clause (version depends on Blender build) |

Check your Blender build for exact component versions (see the environment script in the distribution README).

## Trademarks

**Blender** is a registered trademark of the Blender Foundation. **Seam Runner** is not affiliated with, endorsed by, or sponsored by the Blender Foundation.

## Source code

Under the GPL, recipients of the extension may request corresponding source for the GPL-licensed portions. Contact the **maintainer** listed in the release’s `RELEASE.md` or in the extension manifest inside the zip.
