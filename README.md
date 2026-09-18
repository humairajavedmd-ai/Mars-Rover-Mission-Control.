## Task 2: Mission Control Sends Change Requests

### Change Request CR-01 — Emergency Safety
* **Original Requirement (FR-04):** The rover shall enter Safe Mode when a critical battery or thermal condition is detected.
* **Updated Requirement (FR-04):** The rover shall enter Safe Mode **within 3 seconds** when battery temperature exceeds the critical threshold or battery capacity falls below the defined emergency level.
* **Impact Analysis:** 
  * Adds a strict timing constraint (3 seconds) to the safety system.
  * Converts a high-level safety requirement into a hard real-time functional requirement.
  * Requires real-time battery voltage and thermal sensor monitoring with high priority execution threads.

---

### Change Request CR-02 — Mission Expansion
* **Original Requirement (NFR-04):** The system shall support communication with multiple rovers simultaneously.
* **Updated Requirement (NFR-04):** The system shall support at least **20 simultaneously connected rovers**.
* **Impact Analysis:** 
  * Makes the non-functional requirement measurable and testable.
  * Increases server-side bandwidth and resource allocation demands for Mission Control.
  * Requires scalable network architecture (e.g., connection pooling, asynchronous I/O) to manage 20 parallel data streams.

---
### Change Request CR-03 — Security Upgrade
* **Original Requirement (NFR-02):** Only authenticated Mission Control operators shall be permitted to issue rover commands.
* **Updated Requirement (NFR-02):** The system shall require authenticated and **role-authorized** operators to issue commands.
* **Impact Analysis:** 
  * Upgrades basic authentication to Role-Based Access Control (RBAC).
  * System must now verify not only *who* the operator is, but also *what actions* their assigned role allows (e.g., Driver vs. Payload Specialist).
  * Requires identity management database integration and role-permission checks for every incoming command.
