# 3D Two-Source Interference Simulator (Teaching Edition)

An interactive, teaching-oriented simulator for visualizing "interference from two point sources" in 3D space.
The notebook renders interference patterns on "three orthogonal faces" of a 3D domain (a “corner view”),
and provides diagnostic tools that help students connect "geometry (r₁, r₂, Δr)" to "phase (Δφ)" and to
what we observe as "fringes" in both "near-field" and "far-field (Fraunhofer)" regimes.



---

## Why this simulator?
In many optics courses, interference is first introduced on a flat screen (2D).  
This project extends that intuition into 3D by showing how fringes emerge from the "path difference"
between two spherical wavefronts, while giving students practical controls to explore:

- "Visibility/contrast" via amplitude ratio (A2/A1), coherence (γ), and polarization mismatch  
- "Fringe spacing" and its dependence on geometry (q, λ, distance)  
- "Near-field vs far-field" behavior and when Fraunhofer approximation becomes valid  
- "Incoming vs outgoing" wave convention (converging vs diverging propagation)

---

## Main visualization modes
You can switch the main rendering between:

- "Intensity (spectral-avg)"  
  Time-averaged observable intensity with optional spectral averaging (Δλ, Nλ) to demonstrate temporal coherence.
- "Field snapshot E (phase-visible)"  
  Instantaneous real-field snapshot where the "phase slider" directly changes the displayed wavefronts.
- "Path difference Δr"  
  Pure geometry: Δr = r₂ − r₁, the core driver of interference.
- "Phase map Δφ mod 2π"  
  Phase wrapped into [0, 2π) to connect phase structure to fringe formation.

---

## Teaching controls (physics knobs)
- "Wavelength": λ0, spectral width Δλ, and number of samples Nλ  
- "Source separation": q (sources at x = ±q)
- "Initial phase offset": Δφ0  
- "Amplitude ratio": A2/A1 (controls visibility; strongest learning effect when intensity scale is locked)  
- "Coherence factor": γ (reduces fringe visibility)  
- "Polarization mismatch": polarization angle (effective visibility reduction)
- "Distance decay" toggles: optional 1/r scaling in intensity or field
- "Fraunhofer approximation": far-field model switch to compare with exact geometry

---

## Probe tool (numerical diagnostics)
A probe point (green marker) can be placed on a selected face or freely in 3D.  
At the probe, the notebook reports:

- r₁, r₂, "Δr", Δr/λ  
- "Δφ" and "Δφ mod 2π"
- Local "Intensity I" (spectral-averaged) and "Field E" (snapshot)
- "Local visibility estimate" (must change with A2/A1, γ, polarization)

This is designed to support step-by-step classroom reasoning:
> “If Δr ≈ mλ → constructive (bright), if Δr ≈ (m+½)λ → destructive (dark).”

---

## Line profile + fringe spacing
A real-time 1D profile is plotted on a chosen face (e.g., I(x) on the y-face).
The simulator estimates "fringe spacing" using an FFT-based method and shows the result directly on the plot.

When in far-field geometry, the notebook also provides the standard expectation:
- "Fraunhofer fringe spacing": Δx ≈ λL/(2q)

---

## Incoming vs outgoing waves (converging/diverging)
Each source can be toggled as:
- "Outgoing (diverging)" spherical wave
- "Incoming (converging)" spherical wave

Propagation arrows can be overlaid (on the y-face) to make direction conventions visually obvious.
This is especially useful when teaching sign conventions in phase:
- Δφ = s₂ k r₂ − s₁ k r₁ + Δφ0  
where s = −1 (outgoing) and s = +1 (incoming).

---

## Compare A/B mode (side-by-side)
A dedicated "Compare A/B" button displays two panels side-by-side, e.g.:

- "A: OUT/OUT" (both waves outgoing)
- "B: IN/OUT" (wave 1 incoming, wave 2 outgoing)

This makes the effect of incoming/outgoing conventions far more visible for students.

---

## Save & reproducibility
The simulator can save:
- "PNG" of the last rendered main 3D view
- "JSON metadata" containing all parameters and UI settings used at the moment of saving  
This supports reproducible lab reports and homework submissions.

---

## Installation
### Option A) Using requirements.txt
### Crafted by Mehrdad, straight out of the Wild West of Lorestan, Iran 🤠
```bash
pip install -r requirements.txt



## License
MIT License. See `LICENSE` for details.
