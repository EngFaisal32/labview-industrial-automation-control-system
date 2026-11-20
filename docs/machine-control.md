# Simulated Conveyor and Motor Control

The Machine Control HMI has **Start conveyor** and **Stop conveyor**, operating state, simulated RPM gauge, temperature/current readouts and running/stopped/fault indicators.

## Captured normal startup
An Administrator accepted START command produced:
- State: **RUNNING**; machine message `Start accepted`
- Motor speed: **1,143.6 RPM**
- Simulated temperature: **32.524°C**
- Simulated motor current: **5.2572 A**
- Running indicator illuminated, fault indicator inactive

A separate monitoring capture showed 1,500 RPM / 70°C / 4.5 A; these observations were not simultaneous.

## Captured thermal fault
At **100°C** (90°C configured trip), the Machine Control screen showed **FAULT**, motor speed **0 RPM**, motor current **0 A**, and active stopped and fault indicators. A later capture at **83.641°C** still showed FAULT with 0 RPM and 0 A, illustrating fault-state retention and no automatic restart.

The report describes simulated acceleration/deceleration, start permissives and controlled logout/session-timeout stopping. Exact ramp constants and final VI internals were not independently checked.

*Software-simulated operation only; not physical machine stop or safety certification.*
