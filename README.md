# NCI-Lens 🔬

### 3D Viewer and Analyzer of Noncovalent Interactions

📦 **DOI:** 10.5281/zenodo.22017076 | **Version:** 5.1

**NCI-Lens** is a fast, browser-based 3D molecular viewer designed for crystallographers, computational chemists, and students. It automatically detects, visualizes, and estimates the energy of a wide spectrum of noncovalent interactions (NCIs) directly from structural files.

With the **v5.1 update**, NCI-Lens introduces unprecedented accuracy in **$\pi$-hole and $\sigma$-hole detection**, featuring advanced geometric shadow guards, SAPT-like energy decomposition, and specialized calibrations for anion-$\pi$ complexes and metallylenes.

🌐 **[Launch Web App](https://dmitrii-bolotin.github.io/NCI-Lens/)** _(No installation required, runs entirely in your browser)_

![NCI-Lens Interface](https://github.com/Dmitrii-Bolotin/NCI-Lens/blob/main/screenshot.png)

---

## 🚀 What's New in v5.1 (Advanced $\pi$-hole & Shadow Guards)

- **Advanced $\pi$-hole Hygiene & Shadow Guards:** Implemented strict geometric guards to eliminate false positives and double-counting:
  - **Reverse $n \to \pi^*$ guard:** Prevents carboxyl/ester oxygens from falsely acting as carbonyl $\pi$-acceptors.
  - **1,2-shadow & $\sigma$-donor shadow guards:** Distinguishes genuine lone-pair attacks from the geometric shadows of adjacent $\sigma$-hole bonds.
- **Angular Anomaly Calibration:** Precise tilt-axis calibrations for non-standard $\pi$-hole donors, including square-planar XeF₄ (25° tilt) and bent SeO₂ (4° tilt).
- **Lone-Pair Penalties & Metallylenes:** Energy scaling dynamically adjusts based on the donor's lone-pair count. Added massive binding energy boosts for **metallylenes** (SiH₂, GeH₂) acting as $\pi$-hole donors.
- **Anion-$\pi$ & Charge-Assisted Complexes:** Dedicated SAPT regime switching and energy multipliers for anionic nucleophiles binding to $\pi$-holes.
- **Hydridic $\to$ $\pi$ Interactions:** Full support for nucleophilic hydridic hydrogens (bonded to B, Al, Si, metals) interacting with aromatic rings and other $\pi$-systems.
- **Pentacoordinate Tetrel Bonds:** Broadened angular wells (~90–110°) to accurately model charge-assisted tetrel attacks.
- **Onium & Planar Nitrogen Exclusion:** Quaternary/planar nitrogens and covalently bound halogens are now correctly excluded from acting as $\pi$-acceptors.
- **Refined Coulomb Screening:** Optimized $\pi$-path Coulomb screening to prevent overestimation of oxoanion and nitrate contacts.

## ✨ Key Features

- **Comprehensive NCI Detection:** Automatically finds Hydrogen bonds, Halogen, Chalcogen, Pnictogen, Tetrel, Triel, Aerogen, and $\pi$-hole bonds, as well as $\pi$-stacking.
- **SAPT-like Energy Decomposition:** Energies are split into Electrostatics (ES), Induction (IND), and Dispersion (DISP) components, exportable via IUCr CSV.
- **Crystal Walking:** Clicking a "ghost sphere" of a hidden partner atom _clones_ the fragment at the contact site, allowing you to visually "walk" through infinite crystal lattices.
- **Smart UI:** 9 individual toggle buttons for each NCI type. Dragged labels remember their positions. Pointer lines intelligently stop at the text boundary to avoid overlapping.
- **Multi-language:** Full localization support for **English**, **Russian**, and **Portuguese (Brasil)**.

## 🔗 Supported Interactions

| Type | Description | Visual |
| :--- | :--- | :--- |
| **H-bond** | Classic D–H···A electrostatic + dispersion | Blue dashed |
| **Aerogen** | $\sigma$-hole on Kr, Xe, Rn | Teal dashed |
| **Halogen** | $\sigma$-hole on Cl, Br, I, At (incl. hypervalent) | Violet dashed |
| **Chalcogen** | $\sigma$-hole on S, Se, Te, Po (incl. hypervalent) | Yellow dashed |
| **Pnictogen** | $\sigma$-hole on P, As, Sb, Bi (incl. hypervalent) | Orange dashed |
| **Tetrel** | $\sigma$-hole on C (activated), Si, Ge, Sn, Pb | Green dashed |
| **Triel** | $\sigma$-hole / $\pi$-hole on B, Al, Ga, In, Tl | Pink dashed |
| **$\pi$-hole** | Carbonyls, CO₂, NO₂, perfluorinated rings, metallylenes | Magenta dashed |
| **$\pi$-stack** | Aromatic ring stacking (excluding sp³) | Green centroid lines |

## 📂 Supported File Formats

- **`.cif`** (Full crystallographic support: unit cells, symmetry operations, anisotropic thermal ellipsoids. Intermolecular contacts across symmetry boundaries are automatically detected and glued via BFS).
- **`.xyz`** (Standard and Chem3D, supports trajectories)
- **`.pdb`**, **`.mol`**, **`.sdf`**

## 🖱️ Controls

- **Rotate:** Left Mouse Button / 1-finger touch
- **Zoom:** Scroll Wheel / Pinch
- **Pan:** Right Mouse Button / 3-finger touch / On-screen Joystick
- **Measure:** Click atoms sequentially (2 for distance, 3 for angle, 4 for torsion).
- **Isolate Fragment:** Click an atom ➔ press `⛶ Fragment`.
- **Multi-select:** `Shift + Click` atoms across different molecules, then isolate.

## ⚛️ Scientific Background & Calibration

The energy estimation model (accessible via the **PRO** button in the app) relies on empirical geometric parameters, EQeq charges, and explicit polarization/charge-transfer terms.

- **Calibration:** The model was calibrated against **113 literature associates** (spanning $\sigma$-hole, $\pi$-hole, and $\pi$-stacking interactions) using high-level quantum chemistry benchmarks (SAPT, DLPNO-CCSD(T), QTAIM).
- **Accuracy:** Median absolute error is **~3 kJ/mol** for weak contacts. For stronger contacts, **60%** of the dataset shows an error of **<10%**.
- **Thresholds:** Interactions below the user-defined threshold (default 2 kJ/mol / 0.5 kcal/mol) are hidden to reduce visual clutter but are accounted for in the total energy sum. Contacts exceeding 150 kJ/mol are flagged as having significant covalent character.

## 👨‍🔬 Credits & Citation

Developed by **BOLLAB** (Dmitrii S. Bolotin).
If you use NCI-Lens in your research, please cite the repository and the underlying geometric models for $\sigma$/$\pi$-hole interactions. A comprehensive list of the 37 foundational papers used for calibration is available in the in-app **PRO** documentation window.

---

_© 2021-2026 BOLLAB. Released under MIT License._
