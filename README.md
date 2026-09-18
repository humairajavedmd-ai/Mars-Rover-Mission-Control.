#  Mars Rover Mission Control System

##  Mission 'Analyze the Engineering Note'

### Functional Requirements (FRs)
1. **FR-01 (Command Processing):** The system shall receive and execute valid movement commands sent from Mission Control.
2. **FR-02 (Telemetry Reporting):** The rover shall continuously report its current position, battery level, internal temperature, and communication status to Mission Control.
3. **FR-03 (Authentication & Access Control):** The system shall allow only authenticated Mission Control operators to issue commands.
4. **FR-04 (Command Validation):** The system shall detect and reject invalid or unauthorized commands.
5. **FR-05 (Automated Safe State):** The rover shall automatically enter Safe Mode upon detecting critical battery or thermal conditions.
6. **FR-06 (Execution Status Feedback):** Mission Control shall receive command execution status and confirmation responses.
7. **FR-07 (Event Logging & Audit):** All issued commands and critical rover events shall be logged with a timestamp and Operator ID for audit purposes.

---

### Non-Functional Requirements (NFRs)
1. **NFR-01 (Performance & Latency):** Command processing on the rover should complete within 5 seconds after a command is received.
2. **NFR-02 (Reliability & Fault Tolerance):** The system shall continue operating despite temporary communication interruptions and long propagation delays.
3. **NFR-03 (Scalability):** The system should support simultaneous communication with multiple rovers.
4. **NFR-04 (Security):** The system shall enforce security controls to prevent unauthorized command execution and ensure data integrity over the communication link.
