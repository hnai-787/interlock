# Proteus Reconstruction Guide

## Architecture

```text
NE555 1Hz Timer
↓
4-Bit Counter
↓
Traffic Logic
↓
Traffic Lights
```

The actual implementation uses D flip-flops for the counter, but the module can generally be described as a 4-bit counter.

---

## Module 1: NE555 Timer

Use:

```text
Ra = 100kΩ
Rb = 22kΩ
C = 10µF
```

Formula:

```text
T = C(Ra + 2Rb) / 1.44
```

This produces approximately a 1-second pulse.

---

## Module 2: 4-Bit Counter

The counter was built using D flip-flops.

Mapping:

```text
A = MSB
B = second bit
C = third bit
D = LSB
```

The counter generates states from:

```text
0000 to 1111
```

Alternative implementations:

```text
JK flip-flop counter
T flip-flop counter
Dedicated 4-bit counter IC
```

---

## Module 3: Traffic Logic

Inputs:

```text
A, B, C, D
```

Outputs:

```text
R1 Y1 G1
R2 Y2 G2
R3 Y3 G3
R4 Y4 G4
```

The Boolean equations are implemented using NOT, AND, and OR gates.

---

## Module 4: Traffic Lights

Use 12 LEDs:

```text
4 red
4 yellow
4 green
```

Each LED should have:

```text
330Ω resistor
```

---

## Testing Order

1. Test NE555 clock.
2. Test 4-bit counter output.
3. Test traffic logic outputs.
4. Test LED traffic lights.
5. Test full sequence.
