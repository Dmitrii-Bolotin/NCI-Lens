# NCI-Lens 🔬
### 3D Viewer and Analyzer of Noncovalent Interactions

**NCI-Lens** (former *SigmaLens*) is a fast, browser-based 3D molecular viewer designed for crystallographers, computational chemists, and students. It automatically detects, visualizes, and estimates the energy of a wide spectrum of noncovalent interactions (NCIs) directly from structural files.

🌐 **[Launch Web App](https://dmitrii-bolotin.github.io/NCI-Lens/)** *(No installation required)*

![NCI-Lens Interface](https://github.com/Dmitrii-Bolotin/NCI-Lens/blob/main/screenshot.png)

---

## 🚀 Key Features (v4.23)

*   **Comprehensive NCI Detection:** Automatically finds Hydrogen bonds, Halogen, Chalcogen, Pnictogen, **Tetrel**, **Triel**, **Aerogen**, and **π-hole** bonds, as well as **π-stacking**.
*   **Hydridic Hydrogens:** Correctly identifies H atoms bonded to low-electronegativity centers (B, Al, Si, metals) acting as nucleophiles.
*   **Advanced Energy Model:** Estimates interaction energies (kJ/mol) using a geometric model augmented with EQeq charges, polarization, charge-transfer, and metal-coordination activation.
*   **Crystal Walking:** Clicking a "ghost sphere" of a hidden partner atom now *clones* the fragment at the contact site, allowing you to visually "walk" through infinite crystal lattices.
*   **Smart UI:** 9 individual toggle buttons for each NCI type. Dragged labels remember their positions. Pointer lines intelligently stop at the text boundary to avoid overlapping.
*   **Multi-language:** Full support for English, Russian, and Portuguese.

## 🔗 Supported Interactions

| Type | Description | Visual |
| :--- | :--- | :--- |
| **H-bond** | Classic D–H···A electrostatic + dispersion | Blue dashed |
| **Halogen** | σ-hole on Cl, Br, I | Violet dashed |
| **Chalcogen** | σ-hole on S, Se, Te, Po | Yellow dashed |
| **Pnictogen** | σ-hole on P, As, Sb, Bi | Orange dashed |
| **Tetrel** | σ-hole on C (activated), Si, Ge, Sn, Pb | Green dashed |
| **Aerogen** | σ-hole on Kr, Xe, Rn | Teal dashed |
| **π-hole** | Carbonyls, CO₂, NO₂, perfluorinated rings | Magenta dashed |
| **Triel** | Electron deficiency on Boron | Pink dashed |
| **π-stack** | Aromatic ring stacking (excluding sp³) | Green centroid lines |

## 📂 Supported File Formats

*   **`.xyz`** (Standard and Chem3D, supports trajectories)
*   **`.cif`** (Full crystallographic support: unit cells, symmetry operations, anisotropic displacement parameters. Intermolecular contacts across symmetry boundaries are automatically detected).
*   **`.pdb`**, **`.mol`**, **`.sdf`**

## 🖱️ Controls

*   **Rotate:** Left Mouse Button / 1-finger touch
*   **Zoom:** Scroll Wheel / Pinch
*   **Pan:** Right Mouse Button / 3-finger touch / Joystick
*   **Measure:** Click atoms sequentially (2 for distance, 3 for angle, 4 for torsion).
*   **Isolate Fragment:** Click an atom ➔ press `⛶ Fragment`.
*   **Multi-select:** `Shift + Click` atoms across different molecules, then isolate.

## ⚛️ Scientific Background

The energy estimation model relies on empirical geometric parameters calibrated against high-level quantum chemistry benchmarks (SAPT, DLPNO-CCSD(T)). 
*   **Charges:** Calculated via a simplified Electronegativity Equalization (EQeq/Sanderson) method.
*   **Accuracy:** ~±10–15% for typical noncovalent contacts. 
*   **Thresholds:** Interactions weaker than 2 kJ/mol are hidden to reduce visual clutter. Contacts exceeding 150 kJ/mol are flagged as having significant covalent character.

## 👨‍🔬 Credits & Citation

Developed by **BOLLAB** (Dmitrii Bolotin).
If you use NCI-Lens in your research, please cite the repository and the underlying geometric models for σ/π-hole interactions.

---
*© 2021-2026 BOLLAB. Released under MIT License.*
