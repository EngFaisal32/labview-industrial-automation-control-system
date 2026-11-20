# Monitoring, Alarm Management and Fault Recovery

| Parameter | Warning | Trip |
| --- | ---: | ---: |
| Temperature | 75°C | 90°C |
| Motor current | 6 A | 9 A |

Screenshots show gauges for RPM, temperature, current, sensor validity, warning conditions and trip indication.

**Normal monitoring capture:** 1,500 RPM, 70°C, 4.5 A, sensor quality `GOOD`, no warning/trip active.

**Injected overtemperature:** 100°C → active monitoring trip, FAULT state, 0 RPM, 0 A. The machine control message calls for cooling and authorized reset. At 83.641°C the FAULT condition was still retained.

**Alarm register capture:**
- `A102 Motor overtemperature trip` — `TRIP / ACTIVE / UNACKNOWLEDGED`.
- `A107 Account lockout` — `WARNING / CLEARED / UNACKNOWLEDGED`.

The alarm table has ID, Description, Severity, State, Acknowledgment, and Timestamp UTC fields. The interface contains **Acknowledge all alarms** and **Reset fault** controls; the successful final reset flow was author-reported but **not demonstrated by the screenshots provided**.

Settings show simulated fault-injection controls for **overtemperature, overload, sensor failure, and drive fault**, plus start-permissive controls.

These are simulation alarm/interlock functions, not protection certified for real equipment.
