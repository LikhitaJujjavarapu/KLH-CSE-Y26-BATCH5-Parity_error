# README: Design and Simulation of a Digital Error Detection System Using Parity

## Overview
This repository / project package contains the resources, documentation, and simulation details for the academic project: **"Design and Simulation of a Digital Error Detection System Using Parity"**, developed for (DDCA) course.

---

## Slide Deck Overview (12 Slides)

1. **Slide 1: Title Slide**
   - Project Title, Student Names, Roll Numbers, Guide Name, Department, College, and Academic Year.
2. **Slide 2: Abstract**
   - Summary of error detection, transmission noise, parity technique, and simulation objective using Logisim.
3. **Slide 3: Introduction**
   - Fundamentals of digital communication, necessity of redundant bits, and transmitter-receiver block flow.
4. **Slide 4: Problem Statement**
   - Real-world impact of corrupted bits during transmission and visual comparison of valid vs. invalid data frames.
5. **Slide 5: Project Objectives**
   - Specific goals: parity generation, single-bit error detection, Logisim circuit simulation, and logic verification.
6. **Slide 6: System Methodology**
   - Complete stage-by-stage architecture flow: `Input Data -> Parity Generation -> Data Transmission -> Parity Checking -> XOR Logic -> LED Error Indicator`.
7. **Slide 7: Working Principle**
   - Mechanics of Even and Odd parity, mathematical XOR expressions (P = D3 ⊕ D2 ⊕ D1 ⊕ D0), and truth table logic.
8. **Slide 8: Circuit Design**
   - Complete schematic diagram using XOR gates for parity generator and parity checker modules.
9. **Slide 9: Logisim Simulation Layout**
   - Detailed component breakdown: Pin inputs, XOR tree, simulated channel noise/flip switch, parity check logic, and LED indicator status (`OFF = No Error`, `ON = Error`).
10. **Slide 10: Simulation Results & Verification**
    - Verification table with test vectors showing transmitted data, received data, and error status outputs.
11. **Slide 11: Advantages, Limitations & Applications**
    - Three-column comparative analysis detailing circuit simplicity, single-bit limitation, and real-world deployment (RAM, Networks, Buses).
12. **Slide 12: Conclusion & Future Scope**
    - Summary of project outcomes and future extensions (Hamming Codes, CRC, Hardware IC implementations).

---

## Logisim Simulation Setup Instructions

To run and verify the circuit in **Logisim**:

1. **Prerequisites:**
   - Download and install Logisim or Logisim-evolution (Java runtime required).

2. **Building the Parity Generator:**
   - Place 4 Input Pins for data bits (D3, D2, D1, D0).
   - Cascade 3 XOR gates to compute Even Parity: P = D3 ⊕ D2 ⊕ D1 ⊕ D0.
   - Bundle the 4 data bits and 1 parity bit into a 5-bit transmitted vector.

3. **Simulating Transmission Channel & Error Injection:**
   - Use controllable switches or bit-flip XOR gates to simulate noise in transit.

4. **Building the Parity Checker:**
   - Take the 5 received bits (R3, R2, R1, R0, RP).
   - Cascade XOR gates: E = R3 ⊕ R2 ⊕ R1 ⊕ R0 ⊕ RP.
   - Connect output E to an LED Pin (`High/1` = Red LED for Error, `Low/0` = Green/Off).

---

## Truth Table / Verification Matrix

| Input Data (D3..D0) | Even Parity (P) | Sent Package | Received Package | Error Check (E) | Output Status |
| :---: | :---: | :---: | :---: | :---: | :---: |
| `1010` | `0` | `10100` | `10100` | `0` | **No Error** |
| `1100` | `0` | `11000` | `11000` | `0` | **No Error** |
| `1010` | `0` | `10100` | `10000` | `1` | **Error Detected** |
| `1110` | `1` | `11101` | `01101` | `1` | **Error Detected** |


