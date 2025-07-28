# Differential Amplifier (Cadence)

This project involves the design, simulation, and analysis of a **differential amplifier** using **Cadence Virtuoso**. It focuses on frequency response analysis and includes calculation of key performance parameters such as **Bandwidth** and **Unity Gain Bandwidth**.

---

## Abstract

The differential amplifier is a core analog circuit used in operational amplifiers and signal processing systems. This project involves simulating the differential pair using Cadence tools, analyzing its AC response, and calculating essential frequency-domain parameters.

---

## Theory

A **differential amplifier** amplifies the difference between two input voltages while rejecting any voltage common to both inputs. It forms the core of many analog ICs such as op-amps and comparators.

### 🔹 Differential Gain (Avd)

The differential-mode gain is defined as:

**Avd = Vout / (Vin+ − Vin−)**

- If **Vin+ = 1 V (AC)** and **Vin− = 0 V (AC grounded)**, then:

  → **Avd = |Vout|**

- To express gain in decibels (dB):

  **Avd (dB) = 20 × log₁₀(Avd)**


### 🔹 Bandwidth (BW)

Bandwidth refers to the range of frequencies over which the amplifier maintains its performance. It is defined between the −3 dB cutoff frequencies:

**Bandwidth = f_high − f_low**

- *f_high* and *f_low* are the upper and lower −3 dB points where gain drops by 3 dB from the midband gain.


### 🔹 Unity Gain Bandwidth

This is the frequency at which the **magnitude of gain becomes 1 (0 dB)**. For high-speed amplifiers, it indicates the maximum usable frequency when configured in a unity-gain feedback.


### 🔹 Common Mode Gain (Avc)

When both inputs are driven by the same signal (common-mode input), the gain is:

**Avc = Vout / Vcommon**

Where **Vcommon** is the voltage applied equally to both inputs.


### 🔹 Common Mode Rejection Ratio (CMRR)

**CMRR = Avd / Avc**

- In dB: **CMRR(dB) = 20 × log₁₀(Avd / Avc)**

A high CMRR indicates good rejection of common-mode signals (e.g., noise).


### 🔹 Input Resistance (Rin) and Output Resistance (Rout)

- **Rin** is typically high to minimize loading on the input source.
- **Rout** should be low to drive the load effectively.


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



