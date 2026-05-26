# CMOS Inverter Layout Design and Verification | Cadence Virtuoso | GPDK 45nm

A complete CMOS inverter design flow implemented using **Cadence Virtuoso** with **GPDK 45nm technology**, including schematic design, layout implementation, DRC/LVS verification, and transient simulation analysis before and after matching.

---

## Project Overview

This project demonstrates the full-custom VLSI design flow of a CMOS inverter in **45nm technology** using the **Cadence Virtuoso** environment and **GPDK45 Process Design Kit**.

The project covers:

- CMOS inverter schematic design
- Symbol creation
- Layout implementation
- Design Rule Check (DRC)
- Layout Versus Schematic (LVS) verification
- Transient simulation using Spectre ADE

---

## Tools & Technologies

- **Cadence Virtuoso 6**
- **GPDK 45nm**
- **Calibre DRC/LVS**
- **Spectre Simulator**
- **Linux Environment**

---

## Project Flow

### 1. Schematic Design

Designed CMOS inverter using:

- `PMOS_1V_LVT`
- `NMOS_1V_LVT`

Configured transistor sizing:

| Transistor | Width (W) | Length (L) |
|------------|------------|------------|
| PMOS       | 120nm      | 45nm       |
| NMOS       | 120nm      | 45nm       |

Connections:
- Gates connected together → Input
- Drains connected together → Output
- Sources and body terminals connected to VDD/GND

<img width="1920" height="1080" alt="Screenshot 2023-10-06 160353" src="https://github.com/user-attachments/assets/0c163a0b-41e3-4793-98fa-1ae9db4b046d" />

  
---

### 2. Symbol Creation

Generated inverter symbol from schematic with:
- Input pin
- Output pin
- VDD pin
- GND pin

<img width="1920" height="1080" alt="Screenshot 2023-10-06 160405" src="https://github.com/user-attachments/assets/e76d8ef2-4d2e-4e48-8de5-40407946c400" />


---

### 3. Layout Design

Implemented CMOS inverter layout using:
- `OSU_FreePDK45_scells`

Added Metal1 pins for:
- IN
- OUT
- VDD
- GND

<img width="1920" height="1080" alt="Screenshot 2023-10-10 222116" src="https://github.com/user-attachments/assets/ae95c607-5d2e-43f0-af14-8df136c979c1" />


Ensured proper routing and connectivity according to 45nm design rules.

---

### 4. Verification

#### DRC (Design Rule Check)

Performed using **Calibre DRC**.

**Result:** No design rule violations.

#### LVS (Layout Versus Schematic)

Performed LVS comparison between:
- Schematic netlist
- Layout extracted netlist

**Result:** LVS matched successfully.

<img width="1920" height="1080" alt="Screenshot 2023-10-10 230752" src="https://github.com/user-attachments/assets/b0496011-0fb9-4714-a471-5eee38318dc1" />


---

### 5. Transient Simulation

Created inverter testbench using:
- DC voltage source
- Pulse input source
- Ground reference

<img width="1920" height="1080" alt="Screenshot 2023-10-09 223510" src="https://github.com/user-attachments/assets/f62e1047-d8e8-4585-a46c-06e59966dfb1" />

Simulation performed using:
- **Spectre ADE L**

Before Matching

<img width="1920" height="1080" alt="Screenshot 2023-10-09 232151" src="https://github.com/user-attachments/assets/8edae1b7-b23f-47db-acaa-4a244ff87e58" />

After Matching
<img width="1920" height="1080" alt="Screenshot 2023-10-10 001019" src="https://github.com/user-attachments/assets/e04cbaa4-02db-4140-b4bd-cd978a68834e" />


Verified:
- Correct inverter switching operation
- Proper transient response
- Output inversion behavior

---

## Simulation Results

The CMOS inverter successfully demonstrated:

- Logic inversion
- Stable transient characteristics
- Correct CMOS switching functionality

---

##  How to Run

### 1. Start Cadence Environment

```bash
source source4virtuouso
virtuoso &
```

### 2. Open Project

- Launch Cadence Virtuoso
- Open the project library
- Load:
  - Schematic
  - Layout
  - Testbench

### 3. Run DRC & LVS

Navigate to:

```text
Calibre → Run DRC
Calibre → Run LVS
```

### 4. Run Simulation

- Launch ADE L
- Select **Spectre** simulator
- Add model library:

```bash
gpdk45nm.m
```

- Run transient analysis

---

## Learning Outcomes

- CMOS inverter design methodology
- Full-custom VLSI design flow
- Layout implementation in 45nm technology
- DRC and LVS verification flow
- Analog/transient simulation using Cadence tools

---

## Reference

This project is based on laboratory implementation using:
- Cadence Virtuoso
- GPDK45 technology
- Calibre verification flow

---
```
