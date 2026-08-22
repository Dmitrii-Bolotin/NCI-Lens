# NCI-Lens 🔬
### 3D Viewer and Analyzer of Noncovalent Interactions

📦 **DOI:** [10.5281/zenodo.22017076](https://doi.org/10.5281/zenodo.22055369)

**NCI-Lens** is a fast, browser-based 3D molecular viewer designed for crystallographers, computational chemists, and students. It automatically detects, visualizes, and estimates the energy of a wide spectrum of noncovalent interactions (NCIs) directly from structural files. 

With the **v5.0 PRO upgrade**, NCI-Lens transforms from a geometric viewer into a powerful analytical tool featuring a full SAPT-like energy decomposition model.

🌐 **[Launch Web App](https://dmitrii-bolotin.github.io/NCI-Lens/)** *(No installation required, runs entirely in your browser)*

![NCI-Lens Interface](https://github.com/Dmitrii-Bolotin/NCI-Lens/blob/main/screenshot.png)

---

## 🚀 What's New in v5.0 (Major Physicochemical Upgrade)

*   **Advanced PRO Energy Model:** Introduced a sophisticated physicochemical model with **SAPT-like energy decomposition**. Energies are now split into Electrostatics (ES), Induction (IND), and Dispersion (DISP) components.
*   **New Interaction Types:** 
    *   **Triel π-holes:** Nucleophilic attack perpendicular to planar TrX₃ (B, Al, Ga, In, Tl).
    *   **Hypervalent multi-σ-hole donors:** Extended angular ranges for R₂I⁺, R₂Br⁺, R₃Ch⁺, and R₄Pn⁺.
    *   **Metallylenes & Astatine:** Full support for SiH₂/GeH₂ π-hole donation and At as a halogen donor.
*   **IUCr Data Export:** Export all detected contacts to a `.csv` table formatted for IUCr journals, complete with SAPT decomposition percentages (ES%/IND%/DISP%).
*   **Thermal Ellipsoids:** Visualize anisotropic displacement parameters directly from `.cif` files.
*   **Enhanced UI:** Added a global **kcal/kJ toggle**, a customizable **"Hide contacts below"** energy threshold filter, and an on-screen camera joystick.
*   **In-App Documentation:** The new **PRO window** provides a 22-section deep dive into the mathematical model, parameter tables, and 37 literature references.

## ✨ Key Features

*   **Comprehensive NCI Detection:** Automatically finds Hydrogen bonds, Halogen, Chalcogen, Pnictogen, Tetrel, Triel, Aerogen, and π-hole bonds, as well as π-stacking.
*   **Hydridic Hydrogens:** Correctly identifies H atoms bonded to low-electronegativity centers (B, Al, Si, metals) acting as nucleophiles.
*   **Crystal Walking:** Clicking a "ghost sphere" of a hidden partner atom *clones* the fragment at the contact site, allowing you to visually "walk" through infinite crystal lattices.
*   **Smart UI:** 9 individual toggle buttons for each NCI type. Dragged labels remember their positions. Pointer lines intelligently stop at the text boundary to avoid overlapping.
*   **Multi-language:** Full localization support for **English**, **Russian**, and **Portuguese**.

## 🔗 Supported Interactions

| Type | Description | Visual |
| :--- | :--- | :--- |
| **H-bond** | Classic D–H···A electrostatic + dispersion | Blue dashed |
| **Halogen** | σ-hole on Cl, Br, I, At (incl. hypervalent) | Violet dashed |
| **Chalcogen** | σ-hole on S, Se, Te, Po (incl. hypervalent) | Yellow dashed |
| **Pnictogen** | σ-hole on P, As, Sb, Bi (incl. hypervalent) | Orange dashed |
| **Tetrel** | σ-hole on C (activated), Si, Ge, Sn, Pb | Green dashed |
| **Aerogen** | σ-hole on Kr, Xe, Rn | Teal dashed |
| **Triel** | σ-hole / π-hole on B, Al, Ga, In, Tl | Pink dashed |
| **π-hole** | Carbonyls, CO₂, NO₂, perfluorinated rings, metallylenes | Magenta dashed |
| **π-stack** | Aromatic ring stacking (excluding sp³) | Green centroid lines |

## 📂 Supported File Formats

*   **`.cif`** (Full crystallographic support: unit cells, symmetry operations, anisotropic thermal ellipsoids. Intermolecular contacts across symmetry boundaries are automatically detected and glued via BFS).
*   **`.xyz`** (Standard and Chem3D, supports trajectories)
*   **`.pdb`**, **`.mol`**, **`.sdf`**

## 🖱️ Controls

*   **Rotate:** Left Mouse Button / 1-finger touch
*   **Zoom:** Scroll Wheel / Pinch
*   **Pan:** Right Mouse Button / 3-finger touch / On-screen Joystick
*   **Measure:** Click atoms sequentially (2 for distance, 3 for angle, 4 for torsion).
*   **Isolate Fragment:** Click an atom ➔ press `⛶ Fragment`.
*   **Multi-select:** `Shift + Click` atoms across different molecules, then isolate.

## ⚛️ Scientific Background & Calibration

The energy estimation model (accessible via the **PRO** button in the app) relies on empirical geometric parameters, EQeq charges, and explicit polarization/charge-transfer terms. 

*   **Calibration:** The model was calibrated against **113 literature associates** (spanning σ-hole, π-hole, and π-stacking interactions) using high-level quantum chemistry benchmarks (SAPT, DLPNO-CCSD(T), QTAIM).
*   **Accuracy:** Median absolute error is **~3 kJ/mol** for weak contacts. For stronger contacts, **60%** of the dataset shows an error of **<10%**.
*   **SAPT Decomposition:** Provisional SAPT regime switching estimates the ratio of Electrostatics, Induction, and Dispersion for every contact.
*   **Thresholds:** Interactions below the user-defined threshold (default 2 kJ/mol / 0.5 kcal/mol) are hidden to reduce visual clutter but are accounted for in the total energy sum. Contacts exceeding 150 kJ/mol are flagged as having significant covalent character.

## 👨‍🔬 Credits & Citation

Developed by **BOLLAB** (Dmitrii Bolotin).
If you use NCI-Lens in your research, please cite the repository and the underlying geometric models for σ/π-hole interactions. A comprehensive list of the 37 foundational papers used for calibration is available in the in-app **PRO** documentation window.

---
*© 2021-2026 BOLLAB. Released under MIT License.*
