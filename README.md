# Class-A Power Amplifier — 90 mW / 8 Ω

## Overview

Design and analysis of a **single-ended Class-A power amplifier** designed to deliver approximately **90 mW into an 8 Ω load** using a low supply voltage.

The project focuses on **transistor biasing, Q-point selection, maximum output power, power dissipation, and the theoretical 25% efficiency ceiling of a conventional resistively loaded Class-A amplifier.**

## Specifications

| Parameter | Value |
|---|---:|
| Supply Voltage (VCC) | 2.4 V |
| Load (RL) | 8 Ω |
| Target Output Power | 90 mW |
| Quiescent Current (ICQ) | 150 mA |
| Quiescent VCE (VCEQ) | 1.2 V |
| Collector Voltage (VC) | 1.35 V |
| Emitter Voltage (VE) | 0.15 V |
| Base Voltage (VB) | 0.85 V |

## Key Calculations

### Output Voltage

\[
V_{out,rms}=\sqrt{P_{out}R_L}
\]

\[
V_{out,rms}=\sqrt{0.09\times8}=0.849V
\]

\[
V_{out,peak}=1.2V
\]

### Output Current

\[
I_{out,peak}=\frac{V_{out,peak}}{R_L}
\]

\[
I_{out,peak}=\frac{1.2}{8}=150mA
\]

Therefore, for maximum symmetrical Class-A operation:

\[
\boxed{I_{CQ}=150mA}
\]

### Q-Point

For maximum symmetrical swing:

\[
V_{CEQ}\approx\frac{V_{CC}}{2}
\]

\[
V_{CEQ}=\frac{2.4}{2}=1.2V
\]

Hence:

\[
\boxed{Q=(1.2V,\ 150mA)}
\]

### Maximum Output Power

\[
P_{out,max}=
\frac{V_{out,peak}^2}{2R_L}
\]

\[
P_{out,max}=
\frac{1.2^2}{2\times8}
=90mW
\]

### DC Power

\[
P_{DC}=V_{CC}I_{CQ}
\]

\[
P_{DC}=2.4\times0.15=360mW
\]

### Maximum Efficiency

\[
\eta=\frac{P_{out}}{P_{DC}}\times100
\]

\[
\eta=\frac{90}{360}\times100
\]

\[
\boxed{\eta=25\%}
\]

## Transistor Biasing

The selected DC voltages are:

\[
V_C=1.35V
\]

\[
V_E=0.15V
\]

Therefore:

\[
V_{CE}=V_C-V_E=1.35-0.15=1.2V
\]

With:

\[
V_B=0.85V
\]

\[
V_{BE}=V_B-V_E=0.85-0.15=0.70V
\]

## Why Class-A?

- Transistor conducts for the entire **360°** of the input cycle.
- No crossover distortion.
- Simple linear amplification.
- Main drawback: **low efficiency and high quiescent power dissipation**.

## 25% Efficiency Ceiling

For a conventional resistively loaded Class-A amplifier:

\[
\boxed{\eta_{max}=25\%}
\]

Efficiency is low at small output levels because the amplifier continues consuming quiescent DC power even when little power is delivered to the load.

At maximum symmetrical output, the efficiency approaches the theoretical 25% limit.

## Quiescent Dissipation

Even with no input signal:

\[
P_Q=V_{CEQ}I_{CQ}
\]

\[
P_Q=1.2\times0.15
\]

\[
\boxed{P_Q=180mW}
\]

This demonstrates the characteristic Class-A behavior where the transistor dissipates significant power even when the amplifier is silent.

## Project Workflow

1. Calculate required output voltage and current.
2. Select the Class-A Q-point.
3. Design the transistor bias network.
4. Build the amplifier circuit.
5. Simulate the circuit.
6. Verify the 90 mW output target.
7. Measure DC power and output power.
8. Calculate efficiency over different output levels.
9. Compare measured results with the theoretical 25% limit.

## Results

### Expected

- Output power: **≈ 90 mW**
- Load: **8 Ω**
- Peak output voltage: **≈ 1.2 V**
- Peak output current: **≈ 150 mA**
- Maximum theoretical efficiency: **25%**
- Quiescent dissipation: **≈ 180 mW**

> **Note:** Final resistor/component values should be determined from the actual circuit topology and verified through simulation/measurement.

## Documentation

Detailed calculations, theory, biasing analysis, and viva preparation are provided in the accompanying project documentation.
