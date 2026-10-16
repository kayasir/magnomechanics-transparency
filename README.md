# Python source for Part 2

Kerr and cross-drive reconstruction of multimode transparency in cavity magnomechanics

Authors: Kashif Ammar Yasir and Wu-Ming Liu. Source version: 8.0.0.

## Run this paper

This archive is self-contained. Its run_all.py is fixed to Part 2; no paper-selection argument is needed. Shared numerical helper modules are included locally. The equations, numerical settings and solver modules are unchanged from the combined version-8 source release.

Extract the ZIP before running it. The commands below must be run from the extracted Part_II_BU16094A_Code_v8 directory, which contains requirements.txt and run_all.py.

Windows, using a Miniforge/conda terminal:

```bat
conda create -n pra-part2 -c conda-forge python=3.12 poppler pip
conda activate pra-part2
python -m pip install -r requirements.txt
python run_all.py --out output
```

Linux/macOS, with Python 3.12 and Poppler installed:

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python run_all.py --out output
```

Poppler supplies pdftops for EPS export. A complete run may take several minutes or longer. The scripts calculate the figures, CSV plotting arrays and JSON diagnostics inside output/. Subsequent runs overwrite generated files in the selected output directory. No external numerical input dataset or proprietary software is required.

## Source files

- run_all.py: runs this paper's figure, validation and control routines.
- model.py: parameter definitions, mean fields, Jacobian, stationary-state reconstruction and linear response.
- algebraic_check.py: polynomial elimination and physical-root verification.
- figures.py and spectra.py: numerical plotting functions and export helpers.
- validate.py: independent root, Jacobian and response checks.
- controls.py: mechanism and limiting-case controls.
- physical_checks.py: dimensional equations and finite omitted-coupling controls.
- submission_checks.py: numerical tolerance, grid and additional physical checks.
- schematic.py: original Figure 1(a) plus the vector technical diagram in Figure 1(b).
- assets/Fig1a_part2.jpg: this paper's original physical illustration; it is not numerical input data.

Set S is parameters(2); set D overrides are explicit in spectra.py and controls.py. The source uses two mode-selective mechanical channels and the full real drift matrix. Figure 3 uses Kerr values 0, 2, 4, 6, 9, 12; Figure 4 uses cross-drive ratios 0, 1, 3, 4, 6, 8. Magnified panels use the same spectra without offsets or individual normalization. Figure 5 compares Kerr 0 versus 12 and cross drive 0 versus 8 on one transmission scale. Figure 6 scans bare photon–magnon coupling; the self-consistent source-power scan is a separate control.

All solver rates are dimensionless angular-frequency ratios. Full-precision definitions in the source take precedence over rounded printed tables. Stable states require maximum real drift eigenvalue below -1e-8. The Supplemental Material defines the physical scaling and the scope of the controls. Numerical consistency does not establish device-specific antenna calibration, mode profiles, anisotropy or heating. See VERIFICATION.md for the executed checks and their limits.

## Separate repository upload

Upload Part_II_BU16094A_Code_v8.zip as this paper's software record at https://zenodo.org. Select Software and use the title "Code for Kerr and cross-drive reconstruction of multimode transparency in cavity magnomechanics". Enter Kashif Ammar Yasir and Wu-Ming Liu as creators, and 8.0.0 as the version. Publish with public file access and cite that record's version-specific DOI in this paper. Use the other paper's separate ZIP for its separate record. Replace the pending DOI and pending-deposit wording in the corresponding manuscript and response after publication.

The archive contains source and supporting illustration assets, not precomputed numerical datasets or submission correspondence. The MIT license applies to source code. The author-provided illustration retains its provenance and existing rights. CITATION.cff provides citation metadata; insert the actual software DOI when available. No public deposit is represented as having been completed by preparing this archive.

Official upload guidance: https://help.zenodo.org/docs/deposit/create-new-upload/
