# PMSM Inverter Board

## Overview

This project is a custom-designed three-phase inverter PCB powered by a single-phase 230 V AC input. The board integrates AC/DC rectification, a high-voltage DC link, a three-phase inverter, an auxiliary power supply, and analog current and voltage measurement circuits.

The board is designed to interface with external control hardware and does not include an onboard microcontroller.

## Electrical Specifications

| Parameter | Specification |
|---|---|
| Input Voltage | 230 V AC, 50 Hz |
| DC-Link Voltage | ~325 V DC |
| DC-Link Capacitance | 940 µF (2 × 470 µF / 450 V) |
| Main Rectifier | GBJ2506-F, 600 V / 25 A |
| Inverter Module | IKCM10H60GAXKMA1 |
| Inverter Rating | 600 V / 10 A class |
| Auxiliary Transformer | 230 V to 2 × 12 V AC, 2.3 VA |
| Current Measurement | 2 × 5 mΩ shunts |
| Current Amplifiers | ZXCT181A1W6-7, 20 V/V |
| Current Measurement Sensitivity | 100 mV/A (nominal) |
| Voltage Measurement | DC-link resistor divider |
| Signal Interface | 2 × 8-pin headers |

## Hardware Architecture

**1. AC/DC Conversion**

The GBJ2506-F bridge rectifies the single-phase AC input into approximately 325 V DC. Two 470 µF capacitors provide DC-link filtering and energy storage. A 5 Ω NTC thermistor limits the initial charging current.

**2. Three-Phase Inverter**

The Infineon IKCM10H60GAXKMA1 integrates the three-phase power switches and gate drivers in a single intelligent power module (IPM). The circuit includes bootstrap capacitors, input resistors, pull-down resistors, and supply decoupling.

**3. Auxiliary Power Supply**

A BV302S12023 transformer, DB107-G bridge rectifier, and 1000 µF filtering capacitor form the low-voltage auxiliary supply stage.

**4. Current and Voltage Measurement**

Two 5 mΩ shunt resistors and ZXCT181A1W6-7 amplifiers provide phase-current measurement signals. A resistor divider measures the DC-link voltage, while an NCS20061 operational amplifier buffers the analog reference.

**5. External Connections**

- J1–J2: Three-position 5.08 mm power terminal blocks
- J3–J4: Eight-pin 2.54 mm signal headers

## Design Notes

- The inverter uses an integrated IPM instead of discrete MOSFETs and gate drivers.
- Current sensing is implemented using two low-side shunt resistors.
- The power stage and auxiliary supply use separate rectification circuits.
- The latest BOM contains 22 component types and 49 physical components.
- Component voltage and current ratings do not represent verified continuous board operating limits.
- The DC-link measurement divider, auxiliary supply characteristics, PCB safety clearances, and thermal performance require final verification before operation.

## Project Files

The schematic and BOM document the circuit architecture, component selections, electrical connections, and hardware revisions.

This README describes the PCB hardware only, excluding motor specifications and control software.
