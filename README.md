# Autonomous Solar-Powered Embedded Monitoring System (Raspberry Pi)

Python code for a Raspberry Pi 4 to read temperature from a **DS18B20** sensor and trigger GPIO outputs (e.g., alarm/indicator) based on configurable thresholds. This repository contains the embedded monitoring component used within a larger off-grid, solar-powered demonstration system.

## Features
- Reads DS18B20 temperature via 1-Wire interface
- Logs/prints temperature readings at a fixed interval
- Triggers GPIO outputs (siren/light) when thresholds are exceeded
- Minimal setup: dependencies listed in `requirements.txt`

## Hardware
- Raspberry Pi 4
- DS18B20 temperature sensor (1-Wire)
- Buzzer/siren and red indicator LED
- Jumper wires / breadboard

## Wiring (Raspberry Pi)
**DS18B20**
- VDD → 3.3V (Pin 1)
- GND → GND (Pin 9)
- DATA → 1-Wire GPIO (set in code)

**Optional outputs**
- GPIO output pin → siren/light control circuit input
- Output ground → GND

> Note: If you are switching a siren/light, do not drive loads directly from the GPIO as it will not work.

## Software Setup
1. Enable 1-Wire interface on the Raspberry Pi.
2. Install dependencies:
   ```bash
   pip3 install -r requirements.txt

## Repository Structure
- main.py — entry point (recommended)
- temperature.py — DS18B20 read utilities / experiments
- requirements.txt — dependencies

## Configuration
**Adjust in code (or convert to CLI/env vars if desired):**
- sampling interval
- temperature threshold
- GPIO pin assignment

## Troubleshooting
**DS18B20 not detected:**
- verify 1-Wire is enabled
- check wiring and ground
- confirm sensor shows up under /sys/bus/w1/devices/

**GPIO output not switching:**
- verify pin numbering mode (ensure numbering consistency with BCM vs BOARD)

## Credits
- Clement Wu (EE, UC Irvine) - Embedded system implementation and electrical integration
- Jerome Foronda (ME, San Jose State University) - Component sourcing and procurement, mechanical prototyping
- Isabella Greiner (ME, UC Davis) & Gabriella Acosta (ME, San Jose State University) - Physical layout design and implementation