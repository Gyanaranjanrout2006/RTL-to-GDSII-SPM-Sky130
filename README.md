# RTL-to-GDSII Physical Design of Serial-Parallel Multiplier (SPM)

An end-to-end ASIC physical design implementation of a Serial-Parallel Multiplier (SPM) architecture using the open-source **OpenLane** flow targeting the **SkyWater 130nm CMOS (`sky130A`)** Process Design Kit.

---

## 📌 Project Overview
- **Circuit Architecture:** Serial-Parallel Multiplier (Hardware Multiplier for DSP/ALU applications)
- **Technology Node:** SkyWater 130nm (`sky130A`) High-Density Standard Cells (`sky130_fd_sc_hd`)
- **EDA Framework:** OpenLane (OpenROAD, Yosys, ABC, Magic VLSI, OpenSTA)
- **Sign-Off Status:** 
  - 0 DRC Violations (Clean Magic DRC)
  - 0 LVS Violations
  - 0 Timing Slack Violations (Zero Setup & Hold violations at typical corner)

---

## ⚙️ ASIC Implementation Flow
1. **Logic Synthesis:** Synthesized RTL into Sky130 standard cells using Yosys & ABC.
2. **Floorplanning & PDN:** Configured core/die boundaries, pin placements, and robust VDD/VSS power grid stripes.
3. **Standard Cell Placement:** Global placement for wirelength minimization followed by legal detailed placement.
4. **Clock Tree Synthesis (CTS):** Balanced clock tree insertion using TritonCTS to minimize skew and latency.
5. **Routing:** Global routing and detailed multi-layer interconnect routing via TritonRoute.
6. **Physical Sign-Off:** Automated tapeout checks including Magic DRC, Antenna rule checks, and Static Timing Analysis (OpenSTA).

---

## 🔍 Layout Inspection in KLayout

### Top-Level Core Layout
![SPM Full Core](SPM_Full_Core.png)

### Standard Cell Rows & Routing Interconnects
![SPM Zoomed Cells](SPM_Zoomed_Cells.png)

---

## 📁 Repository Deliverables
- `spm.gds`: Final tapeout-ready GDSII stream file.
- `SPM_Physical_Design_Report.pdf`: Comprehensive technical design documentation.
- `SPM_Full_Core.png` & `SPM_Zoomed_Cells.png`: High-resolution physical verification screenshots.

---

## 🛠️ Environment & Tools
- **OS:** Windows 11 with WSL2 (Ubuntu 24.04 LTS)
- **Container Engine:** Docker Desktop
- **Design Tools:** OpenLane, OpenROAD, Yosys, KLayout v0.30
