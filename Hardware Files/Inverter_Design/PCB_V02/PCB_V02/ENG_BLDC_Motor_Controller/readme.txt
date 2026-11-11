750 W AC-Fed PMSM/Servo Motor Inverter Prototype
The motor drive board is a compact 230 VAC input, 750 W-class three-phase inverter prototype designed for PMSM and servo motor control. The power stage is based on the Infineon IKCM10H60GAXKMA1 intelligent power module, integrating a 600 V / 10 A three-phase IGBT inverter, gate-drive circuitry, bootstrap functionality, under-voltage protection, fault signaling, and internal temperature sensing in a single package. This approach significantly simplifies the power stage compared with a discrete six-switch inverter architecture.
The AC input is rectified by a GBJ2506-F 25 A / 600 V bridge rectifier and filtered by two 470 µF / 450 V DC-link capacitors, producing a nominal DC bus of approximately 325 VDC from a 230 VAC supply. A 5 Ω / 8.5 A NTC inrush-current limiter is included at the AC input to reduce the initial charging current of the DC-link capacitors.
An independent auxiliary supply is derived directly from the AC input using a 230 VAC to 12 VAC PCB transformer, followed by a DB107 full-wave bridge rectifier and a 1000 µF filtering capacitor. This supply provides approximately 15 VDC for the IKCM10H60GA gate-driver circuitry. Three bootstrap networks, each using 10 µF and 0.1 µF capacitors, provide the floating high-side driver supplies.
The board provides two low-side phase-current measurements using 5 mΩ shunt resistors and ZXCT181 bidirectional current-sense amplifiers with a fixed gain of 20 V/V. A buffered 1.65 V reference allows bipolar phase-current measurement with a 3.3 V external ADC. The third phase current can be reconstructed in software from the two measured currents. DC-bus voltage sensing is also provided through a high-voltage resistor divider for connection to an external controller ADC.
The inverter is intended to be controlled by an external STM32-based control board. Six logic-level PWM inputs provide independent high-side and low-side control of the three inverter phases, while separate analog outputs provide U-phase current, V-phase current, and DC-bus voltage feedback. This keeps the power board independent of the motor-control processor and allows different control platforms and FOC algorithms to be evaluated.
Features
- 230 VAC nominal input
- Approximately 325 VDC nominal DC-link voltage
- 750 W-class PMSM / servo motor inverter
- Infineon IKCM10H60GAXKMA1 600 V / 10 A intelligent power module
- Integrated three-phase IGBT bridge and gate drivers
- GBJ2506-F 25 A / 600 V input bridge rectifier
- Isolated transformer-derived ~15 V auxiliary gate-driver supply
- Three external bootstrap capacitor networks
- Two-phase low-side current sensing
- Six external PWM control inputs
- External STM32 / DSP / motor-control platform interface
- Three-phase U/V/W motor output