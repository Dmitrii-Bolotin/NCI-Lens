# SigmaLens

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub release](https://img.shields.io/github/v/release/Dmitrii-Bolotin/SigmaLens)](https://github.com/Dmitrii-Bolotin/SigmaLens/releases)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.21894729-blue)](https://doi.org/10.5281/zenodo.21894729)
[![Live demo](https://img.shields.io/badge/Demo-Live-blue?logo=github)](https://dmitrii-bolotin.github.io/SigmaLens/)


**A browser-based 3D molecular structure viewer with built-in analysis of hydrogen bonds, σ-hole interactions, and π-stacking in crystal structures.**

SigmaLens is a zero-installation single-file web application designed for supramolecular chemists and crystallographers who need fast inspection of non-covalent interactions directly from CIF, PDB, MOL, SDF, and XYZ files.

![screenshot](screenshot.png)

## ✨ Key Features

### 🔬 Non-covalent interaction detection
- **Hydrogen bonds** — distance + angular criteria (D–H···A)
- **σ-hole interactions** — halogen, chalcogen, pnictogen bonds with geometric and energetic scoring
- **π-stacking** — aromatic ring stacking with coplanarity and slip-angle filters
- **Gasteiger (PEOE) partial charges** for electrostatic component
- **Lennard-Jones dispersion** contribution
- **Empirical energy estimation** (kJ/mol, ±40% accuracy)

### 🧪 Crystallography-aware
- Full **CIF parsing** with unit cell parameters and symmetry operations
- Automatic molecule reconstruction across cell boundaries
- Neighbor contacts via lattice translations
- **IUCr-format contact tables** ready for journal submission

### 📐 Measurements & visualization
- Click-to-measure **distances, angles, torsions**
- Multiple rendering modes: ball-and-stick, van der Waals, ellipsoids (anisotropic displacement), sticks
- **Fragment isolation** with ghost-sphere click-to-reveal
- Drag-and-drop label positioning
- CSV export of measurements and contacts

### 🌐 Accessibility
- **Zero installation** — runs in any modern browser
- Multilingual interface: **Русский / English / Português**
- Touch-friendly controls (tablet/mobile support)
- Three-finger pan gesture on touch devices

## 🚀 Quick Start

### Online (no installation)
👉 Open **https://Dmitrii-Bolotin.github.io/SigmaLens/** and drag a CIF/PDB/XYZ file into the window.

### Local usage
1. Download `index.html` from the [latest release](https://github.com/Dmitrii-Bolotin/SigmaLens/releases).
2. Double-click to open in your browser.
3. Click **📂 Load** or drag-and-drop your structure file.

That's it. No Python, no compilation, no dependencies.

## 📂 Supported formats

| Format | Extensions | Notes |
|--------|------------|-------|
| CIF | `.cif` | Unit cell + symmetry fully handled |
| XYZ | `.xyz` | Standard and Chem3D variants; multi-frame supported |
| PDB | `.pdb` | Standard ATOM/HETATM records |
| MOL | `.mol` | V2000 connection table |
| SDF | `.sdf` | Multiple MOL blocks parsed |

## 🧩 Energy model

For each contact the total interaction energy is computed as:

$$E_\text{total} = E_\text{electrostatic} + E_\text{dispersion} + E_\text{geometry}$$

- **H-bonds**: Coulombic term from Gasteiger PEOE charges (6 iterations), plus Lennard-Jones dispersion.
- **σ-hole contacts**: empirical donor-dependent intrinsic energy scaled by Gaussian angular decay around the optimal R–X···A angle (~170°), with exponential radial decay.
- **π-stacking**: ring-size, distance, planarity and slip-angle factors combined multiplicatively.

All energies are reported in **kJ/mol** with qualitative labels (*weak / medium / strong*).

## 🛠️ For developers

The entire application is a single HTML file using [Three.js r157](https://threejs.org/) with:

- ES modules via import map (no bundler needed)
- Spatial hashing for O(n) bond detection
- InstancedMesh for GPU-efficient rendering of thousands of atoms
- Custom Jacobi eigenvalue solver for anisotropic displacement ellipsoids
- LRU texture cache for labels

### Local development

```bash
# Just serve with any static server, e.g.:
python -m http.server 8000
# then open http://localhost:8000
```

## 📝 Citation

If you use SigmaLens in academic work, please cite:

```bibtex
@software{sigmalens,
  author  = {Bolotin, Dmitrii S.},
  title   = {SigmaLens: Browser-based analyzer of σ-hole and π-stacking interactions},
  year    = {2026},
  publisher = {GitHub},
  url     = {https://github.com/Dmitrii-Bolotin/SigmaLens},
  doi     = {10.5281/zenodo.21894729},
  version = {3.3}
}
```
