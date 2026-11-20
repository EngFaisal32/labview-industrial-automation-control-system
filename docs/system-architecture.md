# System Architecture and Operation

The application is a **LabVIEW 2020 software simulation** of a conveyor control and monitoring system. Its Front Panel has six tabs: **Operator Login**, **Machine Control**, **Sensor Monitoring**, **Alarm Management**, **Event History**, and **Administration / Settings**.

## Functional flow
1. An operator authenticates and receives role-specific permissions.
2. A START command is evaluated against authentication, machine state, operating permissives, and fault conditions.
3. An accepted command transitions the simulated motor to RUNNING, with an RPM gauge and associated current/temperature readouts.
4. Simulated measurements are evaluated against warning and trip limits.
5. An abnormal condition can trigger fault status, stopping indication, alarm registration and command restrictions.
6. A cleared cause and separate authorized acknowledgment/reset are required in the described recovery flow.
7. Authentication, machine transitions and alarm-related activity are recorded in a CSV-style audit history.

The project report describes operating-state concepts **INITIALIZATION, IDLE, READY, RUNNING, STOPPING, FAULT, RESETTING**. Screenshots show some, but not all, transitions.

**Limit:** No complete final VI/Block Diagram was available for independent architecture audit. This page documents intended and screenshot-observed functionality, not a reconstructed internal code implementation.
