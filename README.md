# Heat Assisted Incremental Sheet Metal Forming (HA-ISF) for Ti6Al4V

## 📌 Project Overview
This project investigates **Heat Assisted Incremental Sheet Metal Forming (HA-ISF)** of **Ti6Al4V (Grade 5 Titanium Alloy)** using **Abaqus/Explicit simulations**. The study focuses on how elevated temperatures improve formability, stress distribution, and thickness retention compared to room-temperature forming.

The work explores **tool design, toolpath generation, thermal-mechanical coupling, and Johnson–Cook material modeling** to replicate real-world forming conditions.

---

## 🎯 Objectives
1. **Comprehensive Parameter Exploration**  
   - Study wall angles (20°, 45°, 60°), forming depths (9.5–69.5 mm), step-over distances (0.25–0.5 mm), and mass scaling factors.  
   - Identify optimal parameters for maximizing formability while minimizing defects.

2. **Temperature-Dependent Material Behavior**  
   - Compare yield/flow stress reduction at 600 °C vs. 25 °C.  
   - Validate Johnson–Cook plasticity and damage models for thermal effects.  
   - Assess geometric accuracy and thickness distribution.

3. **Stress & Thickness Analysis**  
   - Evaluate Von Mises and principal stress states.  
   - Compare sine law predictions with simulation results.  
   - Identify thinning zones and propose mitigation strategies.

4. **Simulation Methodology Refinement**  
   - Optimize mass scaling factors for computational efficiency.  
   - Develop best practices for toolpath integration and thermomechanical coupling.

---

## 🧪 Material Properties (Ti6Al4V)
| Property | 25 °C | 600 °C |
|----------|-------|--------|
| Yield Strength (A, MPa) | 1000 | 620 |
| Hardening Constant (B, MPa) | 780 | 220 |
| Hardening Exponent (n) | 0.47 | 0.28 |
| Thermal Softening Exponent (m) | 1.02 | 1 |
| Young’s Modulus (GPa) | 113.8 | 80 |
| Density (tonne/mm³) | 4.43 × 10⁻⁹ | 4.43 × 10⁻⁹ |

---

## ⚙️ Simulation Setup
- **Software**: Abaqus/Explicit, SolidWorks, Fusion 360  
- **Workpiece**: Ti6Al4V plate (150 × 150 × 1 mm), exposed area 80 × 80 mm  
- **Tool**: Hemispherical tip, Ø4 mm (rigid body)  
- **Toolpath**: Spiral trajectory, generated via Fusion 360 + G-Code Ripper  
- **Feed Rate**: 2000 mm/min (33.33 mm/s)  
- **Meshing**: S4R shell elements, 1 mm refined region  
- **Contact**: μ = 0.1, finite sliding formulation  

---

## 📊 Simulation Matrix
| Job ID | Depth (mm) | Temp (°C) | Step-over (mm) | Wall Angle (°) | Peak Stress (MPa) | Min Thickness (mm) |
|--------|------------|------------|----------------|----------------|------------------|--------------------|
| 2 | 9.5 | 600 | 0.25 | 20 | 749.5 | 0.913 |
| 3 | 39.5 | 600 | 0.5 | 45 | 689.1 | 0.485 |
| 4 | 39.5 | 600 | 0.5 | 45 | 810.7 | 0.575 |
| 5 | 59.5 | 600 | 0.5 | 60 | 729.3 | 0.349 |
| 6 | 59.5 | 25 | 0.5 | 60 | 1628 | 0.370 |
| 7 | 69.5 | 25 | 0.5 | 60 | 1687 | 0.353 |

---

## 🔑 Key Findings
- **Stress Reduction**: ~56% lower Von Mises stress at 600 °C compared to 25 °C.  
- **Wall Angle Effect**: Increasing wall angle raises forming stress (6% increase at 45°→60°).  
- **Depth Limitation at Room Temp**: At 25 °C, forming stalled at ~39 mm despite deeper targets.  
- **Thickness Retention**: Heated forming retained ~0.5 mm thickness, vs. 0.35 mm at room temp.  
- **Force Reduction**: Z-direction forming forces dropped by 62–67% at elevated temperature.  

---

## 📌 Implications
- **Thermal Assistance is Essential**: Room temperature forming fails beyond 40 mm depth.  
- **Improved Thickness Uniformity**: Heating reduces thinning and improves accuracy.  
- **Design Guidelines**: Sine law thickness predictions are reliable under elevated temperatures.  
- **Tooling Recommendations**: Ceramic / WC-Co coated tools advised for high-temperature ISF.  

---

## 🚀 Future Work
- Coupled thermo-mechanical simulations with localized heating sources (laser/induction).  
- Adaptive meshing for accuracy vs. computational efficiency.  
- HA-ISF prototype with induction heating & IR pyrometry.  
- Experimental validation via 3D-DIC strain measurement and microstructural analysis.  
- ML-driven multi-objective optimization (formability vs. energy vs. surface finish).  

---

## 📚 References
- Literature on Johnson–Cook parameters for Ti6Al4V.  
- Prior studies on HA-ISF showing 40–55% formability gains.  
- Experimental validation of sine law predictions under elevated temperatures.  

---
## 📂 Repository Contents
```plain text
├── 📄 Report/ # Full project report (PDF/Word)
├── 🛠️ SolidWorks/ # CAD models of tools (20°, 45°, 60°)
├── 🎯 Fusion360_Toolpaths/ # Spiral toolpath G-code and trajectory files
├── 📊 Excel_Data/ # Toolpath coordinate extraction & conversion
├── 🖼️ Images/ # Simulation plots, CAD renders, thickness/stress graphs
├── 🧪 Abaqus_Files/ # Input decks (.inp), amplitude definitions, job files
└── README.md # This file
```
---
## 🔹 Author  
👤 **Priyanshu Singh**  
- 🎓 IIT Ropar | Mechanical Engineering  
- 🔧 Skills: Abaqus, SolidWorks, OpenFOAM, Fusion, Ansys, Arduino IDE, Linux  
- 📧 Email: priyanshusingh04112003@gmail.com  
- 🌐 [LinkedIn](https://www.linkedin.com/in/priyanshu-singh-a47033265) | [YouTube](https://youtube.com/@theunfilteredguyy)  

---
⭐ If you like this project, don’t forget to **star the repo**!

---
