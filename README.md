# Class-A Power Amplifier — 90 mW / 8 Ω

## Overview

Design and analysis of a **single-ended Class-A power amplifier** designed to deliver approximately **90 mW into an 8 Ω load** using a low supply voltage.

The project focuses on **transistor biasing, Q-point selection, maximum output power, power dissipation, and the theoretical 25% efficiency ceiling of a conventional resistively loaded Class-A amplifier.**

---

## Specifications

| Parameter | Value |
|---|---:|
| Supply Voltage (VCC) | 2.4 V |
| Load Resistance (RL) | 8 Ω |
| Target Output Power | 90 mW |
| Quiescent Current (ICQ) | 150 mA |
| Quiescent VCE (VCEQ) | 1.2 V |
| Collector Voltage (VC) | 1.35 V |
| Emitter Voltage (VE) | 0.15 V |
| Base Voltage (VB) | 0.85 V |

---

## Key Calculations

### 1. Output Voltage

Required output power:

$$
P_{out} = 90\,mW = 0.09\,W
$$

For an 8 Ω load:

$$
V_{out,rms} = \sqrt{P_{out}R_L}
$$

$$
V_{out,rms} = \sqrt{0.09 \times 8}
$$

$$
\boxed{V_{out,rms} = 0.849\,V}
$$

Peak output voltage:

$$
V_{out,peak} = \sqrt{2}\,V_{out,rms}
$$

$$
\boxed{V_{out,peak} \approx 1.2\,V}
$$

Therefore:

$$
V_{out,pp} = 2V_{out,peak}
$$

$$
\boxed{V_{out,pp} \approx 2.4\,V}
$$

---

### 2. Output Current

Peak output current:

$$
I_{out,peak} = \frac{V_{out,peak}}{R_L}
$$

$$
I_{out,peak} = \frac{1.2}{8}
$$

$$
\boxed{I_{out,peak} = 150\,mA}
$$

For maximum symmetrical Class-A operation:

$$
\boxed{I_{CQ} = 150\,mA}
$$

The quiescent current is therefore calculated from the required output power rather than chosen arbitrarily.

---

### 3. Q-Point

For maximum symmetrical voltage swing:

$$
V_{CEQ} \approx \frac{V_{CC}}{2}
$$

With:

$$
V_{CC} = 2.4\,V
$$

we obtain:

$$
V_{CEQ} = \frac{2.4}{2}
$$

$$
\boxed{V_{CEQ} = 1.2\,V}
$$

Therefore the Q-point is:

$$
\boxed{Q = (V_{CEQ},I_{CQ}) = (1.2\,V,150\,mA)}
$$

---

### 4. Maximum Output Power

The maximum sinusoidal output power is:

$$
P_{out,max} =
\frac{V_{out,peak}^2}{2R_L}
$$

$$
P_{out,max} =
\frac{1.2^2}{2 \times 8}
$$

$$
\boxed{P_{out,max} = 90\,mW}
$$

Thus, the design meets the required **90 mW output power**.

---

### 5. DC Input Power

The DC power drawn from the supply is:

$$
P_{DC} = V_{CC}I_{CQ}
$$

$$
P_{DC} = 2.4 \times 0.15
$$

$$
\boxed{P_{DC} = 360\,mW}
$$

---

### 6. Efficiency

Efficiency is:

$$
\eta = \frac{P_{out}}{P_{DC}}\times100
$$

At maximum output:

$$
\eta =
\frac{90}{360}\times100
$$

$$
\boxed{\eta = 25\%}
$$

Therefore, the conventional resistively loaded Class-A amplifier approaches its theoretical **25% maximum efficiency at full output**.

---

## Transistor Biasing

The selected DC voltages are:

$$
V_C = 1.35\,V
$$

$$
V_E = 0.15\,V
$$

Therefore:

$$
V_{CE} = V_C - V_E
$$

$$
V_{CE} = 1.35 - 0.15
$$

$$
\boxed{V_{CE} = 1.2\,V}
$$

For the base voltage:

$$
V_B = 0.85\,V
$$

Therefore:

$$
V_{BE} = V_B - V_E
$$

$$
V_{BE} = 0.85 - 0.15
$$

$$
\boxed{V_{BE} = 0.70\,V}
$$

---

## Quiescent Power Dissipation

Even when there is no input signal, the transistor continues conducting the quiescent current.

Therefore:

$$
P_Q = V_{CEQ}I_{CQ}
$$

$$
P_Q = 1.2 \times 0.15
$$

$$
\boxed{P_Q = 180\,mW}
$$

This is one of the major characteristics of a Class-A amplifier: **significant power is dissipated even when no signal is being amplified.**

---

## Efficiency vs Output Level

As the output level increases, the output power increases while the quiescent DC power remains approximately constant.

| Output Voltage | Output Power | Ideal Efficiency |
|---:|---:|---:|
| 0% | 0% | 0% |
| 25% | 6.25% | 1.56% |
| 50% | 25% | 6.25% |
| 75% | 56.25% | 14.06% |
| 100% | 100% = 90 mW | **25%** |

This demonstrates why Class-A efficiency is poor at low output levels and approaches the theoretical 25% limit only at maximum output.

---

## Why Class-A?

- Transistor conducts for the entire **360°** of the input cycle.
- No crossover distortion.
- Simple and highly linear operation.
- High quiescent power dissipation.
- Low theoretical efficiency for a conventional resistive-load configuration.

---

## Project Workflow

1. Calculate required output voltage and current.
2. Determine the Class-A Q-point.
3. Design the transistor bias network.
4. Build the amplifier circuit.
5. Simulate the circuit.
6. Verify the 90 mW output target.
7. Measure DC and AC power.
8. Calculate efficiency over different output levels.
9. Compare the results with the theoretical 25% limit.

---

## Expected Results

| Parameter | Expected Value |
|---|---:|
| Supply Voltage | 2.4 V |
| Load | 8 Ω |
| Output Power | ≈ 90 mW |
| Peak Output Voltage | ≈ 1.2 V |
| Peak Output Current | ≈ 150 mA |
| Quiescent Current | ≈ 150 mA |
| Q-Point VCE | ≈ 1.2 V |
| DC Power | ≈ 360 mW |
| Maximum Theoretical Efficiency | 25% |
| Quiescent Dissipation | ≈ 180 mW |

---

## Documentation

Detailed theory, calculations, transistor biasing analysis, and viva preparation are provided in the accompanying project documentation.

> **Note:** Final resistor/component values should be determined from the actual circuit topology and verified through simulation and measurement.
