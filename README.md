# Mars Rover Mission Control System

## Project Overview
This repository contains the Requirements Engineering analysis for the Mars Rover Mission Control software system, including the initial Functional & Non-Functional Requirements and the impact analysis of Change Requests (CRs).

---

## Mission 1: Engineering Notes Analysis

### Functional Requirements (FRs)
1. **FR-01 (Command Execution):** The rover shall receive and execute valid movement commands sent from Mission Control.
2. **FR-02 (Telemetry Reporting):** The rover shall continuously report its position, battery level, internal temperature, and communication link status to Mission Control.
3. **FR-03 (Command Authentication):** The system shall authenticate operator identities and validate commands before execution.
4. **FR-04 (Safe Mode Transition):** The rover shall automatically enter a low-power Safe Mode when a critical battery or thermal condition is detected.
5. **FR-05 (Execution Feedback):** Mission Control shall receive real-time or delayed command execution status/confirmations from the rover.
6. **FR-06 (Event Logging):** The system shall log all issued commands, system events, and fault alerts with UTC timestamps and Operator IDs for post-mission audit.

### Non-Functional Requirements (NFRs)
1. **NFR-01 (Performance / Latency):** Command processing on the rover shall complete within 5 seconds after reception.
2. **NFR-02 (Security):** Only authenticated operators shall be permitted to issue commands to prevent unauthorized access.
3. **NFR-03 (Reliability & Fault Tolerance):** The system shall handle temporary communication outages and maintain operational state without data loss.
4. **NFR-04 (Scalability):** The system shall support simultaneous communication with multiple exploration rovers.

---

## Mission 2: Change Requests (CRs) Analysis

### Change Request CR-01 — Emergency Safety
* **Original (FR-04):** The rover shall enter Safe Mode when a critical battery or thermal condition is detected.
* **Updated (FR-04):** The rover shall enter Safe Mode **within 3 seconds** when battery temperature exceeds the critical threshold or battery capacity falls below the defined emergency level.
* **Impact Analysis:** Adds a strict timing constraint (3 seconds) to the safety loop, converting a basic functional rule into a hard real-time safety requirement.

### Change Request CR-02 — Mission Expansion
* **Original (NFR-04):** The system shall support communication with multiple rovers simultaneously.
* **Updated (NFR-04):** The system shall support at least **20 simultaneously connected rovers**.
* **Impact Analysis:** Quantifies the scalability requirement, making it measurable and testable for software architecture load limits.

### Change Request CR-03 — Security Upgrade
* **Original (NFR-02):** Only authenticated Mission Control operators shall be permitted to issue rover commands.
* **Updated (NFR-02):** The system shall require authenticated and **role-authorized** operators to issue commands (Role-Based Access Control - RBAC).
* **Impact Analysis:** Introduces granular security; authentication confirms identity, while authorization ensures operators only execute commands within their assigned role scope (e.g., Driver, Payload Specialist).
