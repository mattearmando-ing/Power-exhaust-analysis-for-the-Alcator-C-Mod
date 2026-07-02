# Analysis of Power Exhaust in Alcator C-Mod Tokamak

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Plasma Physics](https://img.shields.io/badge/Field-Fusion%20Energy-purple)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Jupyter](https://img.shields.io/badge/Tool-Jupyter%20Notebook-orange)
![Docker](https://img.shields.io/badge/Environment-Docker-blue)
![Simulation](https://img.shields.io/badge/Code-B2%20SOLPS-red)

## 📖 Overview

This project presents a comprehensive numerical analysis of the edge plasma and power exhaust problem in the **Alcator C-Mod** tokamak, one of the most compact high-field fusion devices ever built. The goal was to evaluate the viability of the divertor under realistic operational conditions and determine whether the machine could sustain high-power discharges without melting its plasma-facing components.

The work follows a complete diagnostic workflow:

1. **Magnetic Field Reconstruction** – Poloidal & Toroidal field mapping from SOLPS/B2 output.
2. **Geometry Extraction** – Major radius, minor radius, X‑point location, elongation.
3. **Scrape‑Off Layer (SOL) Profiling** – Density, temperature, and pressure decay lengths at the OMP.
4. **Heat Flux Calculation** – Parallel transport, flux expansion, and target projection.
5. **Detachment Assessment** – Two‑point model validation and pressure balance analysis.

## 🔬 Key Features

- **Device:** Alcator C‑Mod (High‑field compact tokamak, \(B_T \approx 5.4 \, \text{T}\), \(R_0 \approx 0.675 \, \text{m}\)).
- **Fusion Plasma:** Deuterium, edge power \(P_{SOL} = 3.6 \, \text{MW}\).
- **Transport Regime:** High‑field, high‑density edge (\(n_{sep} \approx 1.0 \times 10^{20} \, \text{m}^{-3}\)).
- **Target Analysis:** Detailed two‑point model assessing pressure drop, particle flux, and recombination losses.
- **Software Environment:** Jupyter Notebook running inside a **Docker** container with dedicated Python libraries for edge plasma analysis (`sptools`).

## 📊 Key Results

| Parameter | Estimated Value | Significance |
| :--- | :--- | :--- |
| **Major Radius** | `0.675 m` | Compact aspect ratio \(R/a = 3.0\) |
| **Minor Radius** | `0.225 m` | Highly elongated plasma \(\kappa \approx 1.78\) |
| **Connection Length** | `≈ 3.5 m` | Long field lines due to X‑point geometry |
| **Safety Factor** | `q ≈ 3.4` | Marginally stable edge configuration |
| **Density Decay Length** | `λ_n ≈ 3 mm` | Extremely steep gradient (high confinement) |
| **Temperature Decay Length** | `λ_T ≈ 3 mm` | Thermal transport strongly suppressed |
| **Power Decay Length** | `λ_q ≈ 1.2 mm` | Heat deposited in a < 2 mm channel |
| **Parallel Heat Flux (OMP)** | `≈ 1765 MW/m²` | Unmitigated flux (attached regime) |
| **Target Heat Load (Attached)** | `≈ 138 MW/m²` | 14× tungsten engineering limit |
| **Target Heat Load (High Recycling)** | `≈ 10 MW/m²` | At safety limit, requires detachment |
| **Detachment Status** | **High Recycling** | Pressure conserved; not yet detached |

> **⚠️ Critical Finding:** The unmitigated heat flux would destroy the divertor instantly. Operation is only possible in the **High Recycling regime**, which reduces the load to the engineering limit (\(\sim 10 \, \text{MW/m}^2\)). However, this is still marginal, demonstrating that full **detachment** is necessary for safe, sustained operation in Alcator C‑Mod.

## 🛠️ Technologies & Tools

- **Computational Environment:** Python 3.x inside a **Docker** container (`jupyter/datascience-notebook`).
- **Data Analysis & Visualization:**  
  - `matplotlib` & `numpy` for 2D field plotting and numerical integration.  
  - `sptools` (custom library) for reading B2/SOLPS output files and mesh handling.
- **Simulation Framework:** B2.5/SOLPS (SOLPS‑ITER) edge plasma code.
- **Physics Analysis:** Custom implementation of the **Two‑Point Model** for detached divertor characterization, including sheath transmission, flux tube compression, and recombination energy contributions.

## 📄 Full Report

For a detailed description of the analytical methods, flux‑tube analysis, and pressure balance calculations, please refer to the  
[Full Project Report](https://raw.githubusercontent.com/mattearmando-ing/[nome-repository]/main/PEX_s353526_Armando_Matteo.pdf).

---

*Project developed for the "Power Exhaust" module – Fusion Physics Course – Aalto University / Politecnico di Torino (Academic Year 2025/2026).*
