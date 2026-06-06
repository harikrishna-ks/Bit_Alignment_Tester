# Bit Alignment Tester

## Overview

The Bit Alignment Tester is a digital electronics project designed to verify the alignment and propagation of serial data bits through an 8-bit shift register. The system uses a 555 Timer as a clock generator, a 74HC14 Schmitt Trigger Inverter for signal conditioning, and a 74HC164 Shift Register for serial-to-parallel data conversion.

The output is displayed using LEDs, allowing real-time visualization of bit movement and alignment.

---

## Features

- Regulated 5V power supply using LM7805
- Clock pulse generation using NE555 Timer
- Signal conditioning using 74HC14 Schmitt Trigger
- Serial-to-parallel conversion using 74HC164
- LED-based bit position indication
- Simple and educational digital logic implementation
- Designed using Altium Designer Professional 26.4.1

---

## System Block Diagram

```text
12V DC Input
      │
      ▼
 LM7805 Regulator
      │
     +5V
      │
 ┌───────────┐
 │ DIP Switch│
 └─────┬─────┘
       │
       ▼
    74HC14
 Signal Conditioner
       │
       ▼
    74HC164
 Shift Register
       ▲
       │
    NE555
 Clock Generator
       │
       ▼
    LEDs
```

---

## Components Used

| Component | Quantity |
|------------|----------|
| LM7805 Voltage Regulator | 1 |
| NE555 Timer IC | 1 |
| 74HC14 Hex Schmitt Trigger Inverter | 1 |
| 74HC164 8-Bit Shift Register | 1 |
| DIP Switch | 1 |
| LEDs | 8 |
| 330Ω Resistors | 8 |
| 10kΩ Resistors | 3 |
| 100kΩ Resistor | 1 |
| 0.33µF Capacitor | 1 |
| 0.1µF Capacitors | 2 |
| 10µF Capacitors | 2 |
| DC Barrel Jack | 1 |

---

## Working Principle

### Power Supply
A 12V DC input is provided through a DC barrel jack. The LM7805 voltage regulator converts the input voltage into a regulated 5V supply required by the digital ICs.

### Clock Generation
The NE555 timer is configured in astable mode to generate continuous clock pulses. These pulses drive the clock input of the shift register.

### Data Input
A DIP switch provides serial data input. The signal passes through the 74HC14 Schmitt Trigger inverter to eliminate noise and improve signal quality.

### Data Shifting
The conditioned signal is fed into the 74HC164 shift register. On each clock pulse, the data shifts one position forward.

### Output Display
The outputs Q0–Q7 of the shift register are connected to LEDs through current-limiting resistors. The LED pattern visually indicates the current bit alignment.

---

## Circuit Connections

### LM7805

| Pin | Connection |
|------|------------|
| IN | 12V Input |
| GND | Ground |
| OUT | +5V Supply |

### NE555 Timer

| Pin | Connection |
|------|------------|
| 1 | GND |
| 8 | +5V |
| 4 | +5V |
| 3 | Clock Output |
| 2 | Connected to Pin 6 |
| 6 | Connected to Pin 2 |
| 5 | 0.01µF to GND |
| 7 | Timing Network |

### 74HC14

| Pin | Connection |
|------|------------|
| 14 | +5V |
| 7 | GND |
| 1 | Data Input |
| 2 | Output to 74HC164 |

### 74HC164

| Pin | Connection |
|------|------------|
| 14 | +5V |
| 7 | GND |
| 1 | DSA |
| 2 | DSB |
| 8 | Clock Input |
| 9 | Master Reset (+5V) |
| 3-13 | LED Outputs |

---

## PCB Design

**Software Used:** Altium Designer Professional 26.4.1

### Design Flow

1. Schematic Capture
2. Component Annotation
3. ERC Validation
4. PCB Layout Creation
5. Component Placement
6. Routing
7. DRC Validation
8. Gerber Generation

---

## Applications

- Digital Electronics Education
- Shift Register Demonstration
- Serial Communication Learning
- Embedded Systems Training
- Laboratory Experiments

---

## Repository Structure

```text
Bit-Alignment-Tester/
│
├── Schematic/
│   └── Bit Alignment Tester.SchDoc
│
├── PCB/
│   └── Bit Alignment Tester.PcbDoc
│
├── Gerber/
│
├── Images/
│   ├── Schematic.png
│   └── PCB.png
│
├── BOM/
│   └── Bill_of_Materials.xlsx
│
└── README.md
```

---

## Future Improvements

- Variable clock frequency control
- Microcontroller integration
- LCD display interface
- Automatic test pattern generation
- USB-powered operation

---

## Author

**Hari Krishna**

Digital Electronics & PCB Design Project

Designed using **Altium Designer Professional 26.4.1**

---

## License

This project is released for educational and academic purposes.
