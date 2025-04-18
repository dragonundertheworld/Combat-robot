# Eternity Fighting Robot Design

A comprehensive design for a 1v1 “Eternity” fighting robot developed by the University of Electronic Science and Technology of China. This project covers mechanical architecture, drive and attack systems, electronics & control, innovative features, and iterative testing & optimization.

---

## Table of Contents

- [Eternity Fighting Robot Design](#eternity-fighting-robot-design)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Mechanical Design](#mechanical-design)
    - [Drive System](#drive-system)
    - [Attack Mechanism](#attack-mechanism)
  - [Electronics \& Control](#electronics--control)
    - [Communication \& Remote Control](#communication--remote-control)
    - [Motor \& Power Components](#motor--power-components)
    - [Main Controller \& Safety](#main-controller--safety)
  - [Innovations \& Materials](#innovations--materials)
    - [Structural Innovations](#structural-innovations)
    - [Material \& Armor](#material--armor)
    - [Modular Architecture](#modular-architecture)
  - [Testing \& Optimization](#testing--optimization)
  - [Team \& Roles](#team--roles)
  - [Build \& Assembly Instructions](#build--assembly-instructions)
  - [License \& Acknowledgements](#license--acknowledgements)

---

## Project Overview

“Eternity” is a compact, four-wheel platform with deployable legs (“4‑wheel 4‑joint” configuration).  
- **Modes**:  
  - **Wheeled mode** for high-speed traversal  
  - **Quasi‑static climbing mode** for stair and obstacle engagement  
- **Climbing cycle**: Approach → Lift → Traction → Reset  
- Maintains stability by keeping at least three “legs” (wheels) in contact with the ground.

---

## Mechanical Design

### Drive System

- **Configuration**: Two‑wheel differential drive  
- **Key Attributes**:
  - Stability
  - Speed control
  - Maneuverability
  - Reliability

### Attack Mechanism

- **Primary Weapon**: Vertical spinner (“tip‑over” rotor)  
- **Supplementary**: Wedge‑style pusher  
- **Advantages**:
  - High-impact vertical blows
  - Low‑profile wedge can lift opponent’s center of gravity  
- **Trade‑offs** vs. horizontal spinners & drum weapons:
  - Reduced “self‑impulse” risk
  - Simpler fabrication and lower cost  
- **Operator Training**: Minimizes precision demands and maximizes damage output.

---

## Electronics & Control

### Communication & Remote Control

- **Technology**: LoRa (Semtech SX1276/78)  
- **Module**: ATK‑LORA  
- **Benefits**:
  1. Long‐range (several kilometers)
  2. Low power consumption
  3. Compact form factor  
- **Interface**: UART

### Motor & Power Components

| Component             | Specification                     |
|-----------------------|-----------------------------------|
| **Weapon Motor**      | M3508 (no gearbox)  
   - Rated Voltage: 24 V  
   - No‑load Speed: 9,158 rpm  
   - Max Torque: 0.15 Nm |  
| **Weapon ESC**        | C620 Brushless Controller  
   - Weight: 35 g  
   - Voltage: 24 V  
   - Signal: CAN & PWM  
   - Dimensions: 49.4×25.8×11.5 mm |  
| **Drive Motors**      | 2 × Hub motors |  
| **Battery**           | FPV LiPo 3S (11.1 V, 1,300 mAh, 110 C) |


### Main Controller & Safety

- **MCU**: X‑mind C1  
  - Drives up to 5 motor channels via PWM  
  - On‑board screw switch & 3S battery input  
- **CAN Bridge**: F103C8T6  
  - Converts PWM → CAN for ESCs  
- **Safety Systems**:
  1. **Unlock Card**: Limits weapon output to ≤10% if missing  
  2. **Signal Loss Protection**: C8T6 cuts motor commands on remote disconnect  

---

## Innovations & Materials

### Structural Innovations

- **Mortise & Tenon**: “Exposed dovetail” connection for weapon module  
- **Invert Walk**: Weapon top edge co‑planar with wheels when flipped, enabling upside‑down driving

### Material & Armor

- **Weapon Blades**:
  - Manganese steel, 6 mm thick, comma‑shaped tip  
- **Armor**:
  - TPU shell for energy absorption  
- **Tires**:
  - 55 mm high‑friction “camelback” profile

### Modular Architecture

- **Interchangeable Modules**:
  - Rapid swapping of drive, weapon, or armor packs  
  - Simplified maintenance & upgrade paths

---

## Testing & Optimization

1. **Version 1** – Proof‑of‑concept CAD & basic drive tests  
2. **Version 2** – Refined frame geometry, improved stability  
3. **Version 3** – Acrylic & 3D‑printed prototypes for live arena trials  
4. **Identified Issues**:
   - Excessive overall height  
   - Simplistic armor  
   - Lack of flip resistance  
   - Crowded internal layout  
5. **Optimizations**:
   - Lowered chassis center of gravity  
   - Redesigned armor geometry & thickness  
   - Integrated anti‑flip skids  
   - Re‑routed electronics into wedge cavity for space efficiency

---

## Team & Roles

| Member   | Role                                   |
|----------|----------------------------------------|
| 曹知寒   | Lead mechanical design; assembly       |
| 刘天羽   | Electronics design & control tuning    |
| 王启宇   | Mechanical assembly; secondary design; driver |
| 王浩宇   | Team operations & coordination         |
| **Advisors** | 何瑜, 彭倍                         |

---

## Build & Assembly Instructions

1. **Prerequisites**:  
   - CAD software for 3D model viewing (e.g., SolidWorks, Fusion360)  
   - 3D printer or CNC for prototypes  
2. **Mechanical Assembly**:  
   - Fabricate chassis plates, dovetail fixtures  
   - Install drive & weapon motors with gear mounts  
   - Attach TPU armor panels  
3. **Electrical Wiring**:  
   - Wire X‑mind C1 → F103C8T6 → ESCs (CAN bus)  
   - Route battery & LoRa antenna  
4. **Software Setup**:  
   - Flash microcontroller firmware (STM32CubeIDE)  
   - Configure LoRa remote pairing  
5. **Trial Runs**:  
   - Verify drive control & weapon spin under no‑load  
   - Test safety interlocks (unlock card, signal loss)  
   - Full‑power arena tests with soft obstacles

---

## License & Acknowledgements

- This design is the property of the UESTC.  
- **Disclaimer**: Do not reproduce, distribute, or sell without permission.

