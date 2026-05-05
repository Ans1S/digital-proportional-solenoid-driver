<p align="center">
	<img src="01_images/kit_1.webp" alt="KIT" height="52"/>
	&nbsp;&nbsp;&nbsp;&nbsp;
	<img src="01_images/Woodward_LOrange_Logo_1.webp" alt="Woodward L'Orange" height="52"/>
	&nbsp;&nbsp;&nbsp;&nbsp;
	<img src="01_images/IPEK_Logo_1.webp" alt="IPEK" height="52"/>
</p>

<h1 align="center">Digital Proportional Solenoid Driver</h1>
<p align="center"><strong>Embedded power electronics showcase for digital current control of proportional solenoid valves.</strong></p>

<p align="center">
	<img src="https://img.shields.io/badge/STM32H7-Bare%20Metal-03234B?logo=stmicroelectronics&logoColor=white" alt="STM32H7"/>
	<img src="https://img.shields.io/badge/PCB-KiCad%209.x-314CB0?logo=kicad" alt="KiCad"/>
	<img src="https://img.shields.io/badge/Control-Hysteresis%20%7C%20PID-0B7285" alt="Control"/>
	<img src="https://img.shields.io/badge/Interface-Ethernet%20Web%20UI-087F5B" alt="Ethernet Web UI"/>
	<img src="https://img.shields.io/badge/Scope-Public%20Portfolio-212529" alt="Portfolio"/>
</p>

<p align="center">
	<img src="01_images/Titelbild.webp" alt="Digital proportional solenoid driver overview" width="820"/>
</p>

---

## 🎓 Project Snapshot

This repository is a compact public showcase of my master's thesis project: a custom high-current driver platform for proportional solenoid valves. The system was built to compare digital current-control strategies on real hardware and benchmark them against an analog reference.

---

## ✨ Highlights

<table align="center">
<tr>
<td align="center"><strong>⚡ Multi-Channel PWM</strong><br/>Independent actuator channels with a wide usable frequency range</td>
<td align="center"><strong>🛡️ High-Side Power Stage</strong><br/>LTC7001 gate driver with MOSFET output stage for solenoid loads</td>
<td align="center"><strong>🎯 Precision Current Sensing</strong><br/>INA253A3 and MCP3565R measurement path for control and validation</td>
</tr>
<tr>
<td align="center"><strong>🧠 Bare-Metal Firmware</strong><br/>STM32H7 service architecture without RTOS overhead</td>
<td align="center"><strong>🌐 Ethernet Telemetry</strong><br/>Browser-based live dashboard for lab use and diagnostics</td>
<td align="center"><strong>💾 Persistent Calibration</strong><br/>Stored correction data for repeatable current measurements</td>
</tr>
<tr>
<td align="center"><strong>🧲 Solenoid Profiles</strong><br/>Parameter sets for actuator-specific behavior and test setup</td>
<td align="center"><strong>📈 Control Comparison</strong><br/>Hysteresis, PID, and analog reference evaluated on the same hardware</td>
<td align="center"><strong>🔬 Measurement Workflow</strong><br/>Prototype bring-up, calibration, test bench data, and result analysis</td>
</tr>
<tr>
<td align="center"><strong>🧰 Flash & Calibration Tooling</strong><br/>Guided setup workflows for firmware deployment and device-specific calibration</td>
<td align="center"><strong>🚀 Application-Oriented Integration</strong><br/>Support tooling that moves the platform beyond a pure lab prototype</td>
<td align="center"><strong>⚙️ Engineering Usability</strong><br/>Designed for repeatable setup, validation, and practical handover</td>
</tr>
</table>

---

## 🛠️ What I Built

- ⚡ A multi-channel digital driver for proportional magnetic actuators.
- 🧩 A custom KiCad PCB with MCU, Ethernet, measurement chain, and power stage.
- 🧠 Bare-metal STM32 firmware for PWM, ADC, control loops, calibration, and diagnostics.
- 🌐 A browser-based interface for live telemetry, parameterization, and test support.
- 🧰 A calibration script and guided flash tool to support practical device setup and application-oriented integration.
- 📈 Measurement workflows to compare hysteresis control, PID control, and an analog reference.

---

## 🌐 Web Interface

<p align="center">
	<img src="01_images/WebInterface.webp" alt="Browser-based telemetry and configuration interface" width="820"/>
</p>

The web interface made the prototype practical in the lab: live values, control settings, calibration views, and diagnostic information were available directly from a browser. In this public repository, operational details are intentionally kept high-level.

---

## 🧰 Integration Tooling

An important part of the project was not only the control hardware itself, but also the tooling around it. A calibration script and a guided flash tool were used to make firmware deployment, parameter transfer, and device setup more application-oriented and easier to integrate into real engineering workflows.

---

## 🔌 Hardware Prototype

> **Current hardware platform: Prototype P0.3** — final hardware revision.

<table>
<tr>
<td align="center"><img src="01_images/Top_P0.3.webp" alt="Prototype P0.3 top side" width="390"/><br/><sub>P0.3 top: STM32H7, Ethernet PHY, power stage, measurement path</sub></td>
<td align="center"><img src="01_images/Bottom_P0.3.webp" alt="Prototype P0.3 bottom side" width="390"/><br/><sub>P0.3 bottom: status LEDs and resistor network</sub></td>
</tr>
</table>

<table align="center">
<tr>
<th>Area</th>
<th>Implemented with</th>
<th>Purpose</th>
</tr>
<tr>
<td align="center">Control MCU</td>
<td align="center"><strong>STM32H750VBT6</strong></td>
<td>Real-time control, acquisition, and communication</td>
</tr>
<tr>
<td align="center">Current feedback</td>
<td align="center"><strong>INA253A3 + MCP3565R</strong></td>
<td>Precise current measurement for control and validation</td>
</tr>
<tr>
<td align="center">Power output</td>
<td align="center"><strong>LTC7001 + AGM12N10A</strong></td>
<td>High-side switching of proportional solenoid loads</td>
</tr>
<tr>
<td align="center">Connectivity</td>
<td align="center"><strong>LAN8742A Ethernet PHY</strong></td>
<td>Telemetry, diagnostics, and browser-based interaction</td>
</tr>
</table>

---

## 📈 Control Comparison

<table align="center">
<tr>
<th>Strategy</th>
<th>Main idea</th>
<th>Why it mattered</th>
</tr>
<tr>
<td align="center"><strong>Hysteresis</strong></td>
<td>Switch inside a defined current band</td>
<td>Fast, robust, simple behavior</td>
</tr>
<tr>
<td align="center"><strong>PID</strong></td>
<td>Closed-loop control with defined PWM behavior</td>
<td>Tunable response and fixed-frequency operation</td>
</tr>
<tr>
<td align="center"><strong>Analog reference</strong></td>
<td>Established non-digital baseline</td>
<td>Practical benchmark for evaluation</td>
</tr>
</table>

---

## 🗺️ Roadmap

- ✅ Hardware P0.1 (Nov 2025) and **P0.2** (Jan 2026) manufactured
- ✅ Bring-up and validation of P0.1 (Jan 2026) and P0.2 (Feb 2026)
- ✅ Firmware baseline completed: HAL, PWM, ADC + DMA, Ethernet
- ✅ Control strategies implemented (hysteresis, PID, analog) - March 2026
- ✅ Measurement series recorded - March 2026
- ✅ **Validation against the analog reference** completed - April 2026
- ✅ Final revision **P0.3** ordered - May 2026
- 🛠️ Integration into test bench systems

---

## 🧠 Skills Demonstrated

<table align="center">
<tr>
<td align="center"><strong>Embedded C</strong><br/>Bare-metal STM32H7 services</td>
<td align="center"><strong>PCB Design</strong><br/>KiCad, power stage, sensing path</td>
<td align="center"><strong>Control Engineering</strong><br/>Hysteresis, PID, actuator behavior</td>
</tr>
<tr>
<td align="center"><strong>Measurement</strong><br/>ADC chains, calibration, validation</td>
<td align="center"><strong>Networking</strong><br/>Ethernet telemetry and web UI</td>
<td align="center"><strong>System Thinking</strong><br/>Prototype, tooling, tests, documentation</td>
</tr>
</table>

---

## 📁 Repository Scope

This is a public, documentation-focused portfolio repository. It summarizes the technical work without publishing the full private development repository, detailed internal tooling, or complete experimental data.

<p align="center"><sub>Master's thesis project at <strong>KIT IPEK</strong> in cooperation with <strong>Woodward L'Orange</strong>.</sub></p>
