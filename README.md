# Bare-Metal Robot Car — ATmega328p

A joystick-controlled robot car running on an **ATmega328p**, with every peripheral driver written from scratch — no Arduino libraries. Built for the Microprocessors course (supervised by Dr. Ahmed Salem).

The point of the project was to understand the microcontroller at the register level: how the hardware actually drives the motors, reads the joystick, and protects itself.

## What's inside

Custom drivers, each as its own module with a clean interface:

| Module | What it does |
|---|---|
| `GPIO` | Register-level digital I/O driver (config / interface / private / program layers) |
| `JOYSTICK` | Reads the analog joystick via the **ADC** and maps it to direction + speed |
| `MOTOR` | PWM speed and direction control for the two DC motors |
| `BATTERY` | Monitors battery voltage and warns when it drops below **8 V** |
| `LED` | Status indication |
| `BIT_MATH` / `STD_Types` | Bit-manipulation macros and fixed-width type definitions |

The joystick's analog signals are read through the ADC and translated into real-time motor commands, so the car responds smoothly to direction changes, while a voltage check keeps the hardware safe.

## Build

Open the project in **Microchip Studio** (`XC8Application2.atsln`) and flash it to the ATmega328p. Wiring is documented in `WIRING_MAP.md`.

Microprocessors course team project — Faculty of Engineering, Alexandria University.
