# Differential Amplifier (Cadence)

This project involves the design, simulation, and analysis of a **differential amplifier** using **Cadence Virtuoso**. It focuses on frequency response analysis and includes calculation of key performance parameters such as **Bandwidth** and **Unity Gain Bandwidth**.

---

## Abstract

The differential amplifier is a core analog circuit used in operational amplifiers and signal processing systems. This project involves simulating the differential pair using Cadence tools, analyzing its AC response, and calculating essential frequency-domain parameters.

---

## Theory 🧠

### Differential Amplifier Basics
A differential amplifier amplifies the difference between two input signals. It is widely used as the input stage of operational amplifiers due to its high common-mode rejection ratio (CMRR) and good linearity.

---

### ➤ Differential Gain (A<sub>vd</sub>)

The differential-mode gain is defined as:

\[
A_{vd} = \frac{V_{out}}{V_{in+} - V_{in-}}
\]

- If the AC magnitude is 1V at `vin+` and `vin-` is grounded, then:

\[
A_{vd} = |V_{out}|
\]

Or in decibels (dB):

\[
A_{vd(dB)} = 20 \cdot \log_{10}(A_{vd})
\]

---

### ➤ Bandwidth (BW)

Bandwidth is the frequency range over which the gain remains constant (within -3 dB of maximum gain):

\[
BW = f_{H} - f_{L}
\]

Where:
- \( f_H \) = Upper cutoff frequency (gain drops by 3 dB)
- \( f_L \) = Lower cutoff frequency

---

### ➤ Unity-Gain Bandwidth

The **Unity-Gain Bandwidth** is the frequency at which the gain becomes 1 (0 dB):

\[
\text{UGBW} = \text{frequency at which } |A_{vd}| = 1
\]

---

### ➤ Common-Mode Gain (A<sub>vc</sub>)

Common-mode gain measures how much of the same signal applied to both inputs appears at the output:

\[
A_{vc} = \frac{V_{out}}{V_{in+} = V_{in-}}
\]

Ideally, \( A_{vc} = 0 \)

---

### ➤ Common-Mode Rejection Ratio (CMRR)

CMRR indicates how well the amplifier rejects common-mode signals:

\[
\text{CMRR} = \frac{A_{vd}}{A_{vc}}
\quad \text{or in dB:} \quad
\text{CMRR}_{dB} = 20 \cdot \log_{10} \left( \frac{A_{vd}}{A_{vc}} \right)
\]

Higher CMRR = better differential performance.

---

### ➤ Gain from Device Parameters

In long-channel approximation, the differential gain can also be estimated using device parameters:

\[
A_{vd} = g_m \cdot R_D
\quad \text{where} \quad
g_m = \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{th})
\]

Or,

\[
g_m = \frac{2I_D}{V_{ov}} = \frac{2I_D}{V_{GS} - V_{th}}
\]

---

> 💡 All these parameters are verified using Cadence Virtuoso Spectre simulation with AC analysis.


## Simulation Details

- **Technology:** 180nm CMOS
- **Tool:** Cadence Virtuoso (Spectre Simulator)
- **Analysis:** AC Sweep
- **Output Node:** `vo`
- **Input Type:** Differential AC input with small signal

---

## Results

| Parameter              | Value         |
|------------------------|---------------|
| Differential Gain (Ad) | Depends on Bias |
| **3dB Bandwidth**          | **177 MHz** |
| **Unity Gain Bandwidth** | **1.2112 GHz** |

>  The Unity Gain Bandwidth was found by plotting the AC response of the amplifier and identifying the frequency at which the magnitude of gain drops to 0 dB.

---

## Differential Amplifier Project - Image Summary

| Image                            | Description                                 |
|----------------------------------|---------------------------------------------|
| ![Differential Amplifier Schematic](Images/Differential%20Amplifier%20Schematic.png) | Complete schematic of the differential amplifier. |
| ![Differential Amplifier TB](Images/Differential%20Amplifier%20TB.png) | Testbench setup used for simulation. |
| ![nmos1 details](Images/nmos1%20details.png) | Characteristics/details of the first NMOS transistor. |
| ![nmos2 details](Images/nmos2%20details.png) | Characteristics/details of the second NMOS transistor. |
| ![pmos details](Images/pmos%20details.png) | Characteristics/details of the PMOS transistor. |
| ![Simulation Tab](Images/Simulation%20Tab.png) | Screenshot of the simulation configuration or environment. |
| ![Transient Response](Images/Transient%20Response.png) | Time-domain response showing output vs time. |
| ![AC Response](Images/AC%20Response.png) | Frequency response of the amplifier (gain vs frequency). |
| ![DC Response](Images/DC%20Response.png) | DC sweep analysis showing biasing behavior. |

---

## Discussion

- The amplifier shows a **wide frequency response**, suitable for high-speed analog front ends.
- The gain begins to drop past a few MHz, with unity gain observed at **1.2112 GHz**.
- Further bandwidth refinement is possible by optimizing transistor sizing and bias current.

---



