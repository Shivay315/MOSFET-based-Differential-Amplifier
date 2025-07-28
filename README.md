# Differential Amplifier (Cadence)

This project involves the design, simulation, and analysis of a **differential amplifier** using **Cadence Virtuoso**. It focuses on frequency response analysis and includes calculation of key performance parameters such as **Bandwidth** and **Unity Gain Bandwidth**.

---

## Abstract

The differential amplifier is a core analog circuit used in operational amplifiers and signal processing systems. This project involves simulating the differential pair using Cadence tools, analyzing its AC response, and calculating essential frequency-domain parameters.

---

## Theory

A differential amplifier amplifies the difference between two input signals and rejects common-mode signals. Key equations:

- **Differential Gain (Ad):**  
  \[
  A_d = \frac{V_{out}}{V_{in+} - V_{in-}}
  \]

- **Bandwidth (BW):**  
  The frequency range over which the gain stays within -3 dB of the maximum gain.

- **Unity Gain Bandwidth (UGBW):**  
  The frequency at which the gain becomes 1 (0 dB).

---

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



