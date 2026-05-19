# Forward Scattering Anisotropy Factor ($g$) Calculator & 3D Visualizer

A professional Python-based computational suite designed for biomedical optics, photonics, and tissue characterization research. This repository provides a two-fold solution to evaluate light-tissue interactions: an automated Graphical User Interface (GUI) to calculate the optical asymmetry parameter ($g$-factor) from raw experimental data, and an interactive 3D visualizer to model scattering cone transitions across cleared and native biological media.

---

## 1. Core Software Suite Features

This repository now contains two primary interactive components:

1. **Anisotropy Factor Calculator (`anisotropy_calculator.py`):**
   * **Automated Excel Parsing:** Dynamically reads sheet structures and offers a user-friendly dropdown mapping system for angular domain ($	heta$) and intensity arrays ($I(	heta)$).
   * **Dual-Direction Asymmetry Compensation:** Automatically segments and evaluates independent profiles for positive ($	heta \ge 0^\circ$) and negative ($	heta \le 0^\circ$) domains to neutralize systemic laboratory alignment errors or beam decentration offsets.
   * **Data Cleaning & Export:** Filters out non-finite entries (`NaN`, `inf`), verifies constraints, and exports publication-ready analytical Excel summary sheets and plots.

2. **3D Scattering Visualizer (`3d_scattering_visualizer.py`):**
   * **Real-time Geometric Manipulation:** Uses `matplotlib.widgets` (Sliders, TextBoxes, RadioButtons) to dynamically adjust cone lengths, base radii, and tissue block spatial properties.
   * **Interactive Annotation Deck:** Features an active canvas tracking engine allowing real-time dragging, font resizing, and color modifications of plot captions.
   * **Instant Export Pipeline:** Saves clean, high-resolution visual simulations (`forward_scattering_cones.png` at 300 DPI) for presentations or papers with a single click.

---

## 2. Theoretical & Mathematical Background

### 2.1. The Anisotropy Factor ($g$)
In radiative transport theory, the directionality of photon redirection after a single collision event is characterized by the scattering phase function $p(	heta)$. The anisotropy factor ($g$) represents the expected value of the cosine of the scattering angle:

$$g = \langle \cos	heta 
angle = \int_{4\pi} p(	heta) \cos	heta \, d\omega$$

### 2.2. Discrete Implementation Logic
The software suite translates this continuous integration into a discrete, intensity-weighted average formulation to handle experimental goniometer data directly:

$$g = rac{\sum_{i} I(	heta_i) \cos(	heta_i)}{\sum_{i} I(	heta_i)}$$

This calculation captures the critical "scattering barrier" transition, mapping how optical clearing agents (OCAs) rearrange structural collagen fiber matrices to narrow scattering profiles from native tissue states ($g  pprox 0.78$) up to highly forward-directed regimes ($g  pprox 0.96 - 0.97$).

---

## 3. Environment Setup & Installation

Ensure you have a modern Python environment installed. You can install all necessary scientific computing and data visualization dependencies via `pip`:

```bash
pip install numpy pandas matplotlib openpyxl
```

### Dependencies Breakdown:
* `numpy`: Advanced trigonometric array processing and numerical integration.
* `pandas` & `openpyxl`: Automated data structuring, cleaning, and spreadsheet I/O.
* `matplotlib`: Multi-planar 3D surface rendering, widget tracking, and scientific plotting.

---

## 4. How to Run

### Run the Data Calculator:
```bash
python anisotropy_calculator.py
```
*Select your raw data sheet via the interactive dialog window to process and export the calculated $g_{pos}$, $g_{neg}$, and compensated $g_{avg}$ factors.*

### Run the Interactive 3D Visualizer:
```bash
python 3d_scattering_visualizer.py
```
*Use the real-time sliders to simulate the scattering cone narrowing effect and adjust the layout directly on the interface.*

---

## 📖 Related Publication
The mathematical logic, data processing pipeline, and geometric principles underlying this toolkit were utilized and validated in our peer-reviewed research regarding soft tissue biomaterials. If you use this tool or visualization model in your work, please consider citing our paper:

> **"Modulation of Optical Anisotropy in Soft Tissue Biomaterials Using Optical Clearing Agents: Implications for Structural Characterization and Biomedical Applications."** > *Progress in Biomaterials (2024)*.  
> **Authors:** Saeed Ziaee, Mohammad Ali Ansari, Mehrdad Kalhori, Kamyab Hassani, Mohammad Hossein Naddaf, Valery V. Tuchin.  
> **DOI:** [10.57647/pibm.2024.132412](https://doi.org/10.57647/pibm.2024.132412)

---

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
_Crafted by Mehrdad Y. Kalhori, straight out of the Wild West of Lorestan, Iran 🤠_
