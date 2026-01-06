# Autonomous Solar-Powered Embedded Monitoring System (Raspberry Pi)

Python code for a Raspberry Pi 4 to read temperature from a **DS18B20** sensor and trigger GPIO outputs (e.g., alarm/indicator) based on configurable thresholds. This repository contains the embedded monitoring component used within a larger off-grid, solar-powered demonstration system.

## Key Features
- Reads DS18B20 temperature via 1-Wire interface
- Logs/prints temperature readings at a fixed interval
- Triggers GPIO outputs (siren/light) when thresholds are exceeded
- Minimal setup: dependencies listed in `requirements.txt`

## Hardware
- Raspberry Pi 4
- DS18B20 temperature sensor (1-Wire)
- Optional: buzzer/siren and/or indicator LED(s)
- Jumper wires / breadboard

## Wiring (Raspberry Pi)
**DS18B20**
- VDD → 3.3V (Pin 1)
- GND → GND (Pin 9)
- DATA → 1-Wire GPIO (set in code)

**Optional outputs**
- GPIO output pin → siren/light control circuit input
- Output ground → GND

> Note: If you are switching a siren/light, use an appropriate driver (transistor/MOSFET/relay) and do not drive loads directly from the GPIO.

## Software Setup
1. Enable 1-Wire interface on the Raspberry Pi.
2. Install dependencies:
   ```bash
   pip3 install -r requirements.txt
