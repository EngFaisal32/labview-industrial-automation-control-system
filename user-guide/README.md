# Industrial Operator Authentication, Machine Control & Monitoring System

**NI LabVIEW 2020 | Industrial Automation Simulation | HMI & Control Logic**

## Overview

A LabVIEW-based simulation of an industrial conveyor control system. It combines operator authentication, role-based permissions, motor Start/Stop control, simulated sensor readings, alarm handling, and event logging in one application.

This is an educational **software simulation**, not a physical PLC installation or safety-certified control system.

## Key Features

- **Operator authentication:** Login/logout, three user roles, 30-second account lockout after three failed attempts, and 60-second inactivity timeout.
- **Machine control:** Start/Stop, seven operating states, acceleration/deceleration, operating permissives, and authorized fault reset.
- **Monitoring:** Simulated motor speed (RPM), current (A), and temperature (°C).
- **Alarms:** Overload, overtemperature, sensor failure, drive faults, and unauthorized operations, with acknowledgment and fault handling.
- **Event history:** Timestamped CSV logging of logins, machine actions, and alarm events.
- **Administration:** Protected simulation settings, fault injection, and a separate 10-digit password-generator demonstration.

## Requirements

- **NI LabVIEW 2020 (64-bit)**
- No physical PLC, DAQ hardware, external DLL, or additional toolkit required for the supplied application.

## How to Run

1. Extract the complete project ZIP into a **writable local folder**. Keep the `subVIs` and `logs` folders in their original locations.
2. Open the supplied **`.lvproj`** file in LabVIEW 2020, then open the main VI.
3. Click **Run** and go to the **Operator Login** tab.
4. Sign in using one of the demonstration accounts below.
5. Open **Machine Control**. With a healthy start permissive and no active fault, press **Start**.
6. View readings in **Sensor Monitoring**, inspect alarms in **Alarm Management**, and check records in **Event History**.
7. Press **Stop** for a controlled stop, or **Exit** to stop and close the application.

## Demo Login Credentials

| Username | Password | Role |
|---|---|---|
| `operator` | `Operator2020!` | Operator |
| `maintenance` | `Maintenance2020!` | Maintenance Technician |
| `admin` | `Admin2020!` | Administrator |

**Credentials are case-sensitive and public for demonstration only. Do not reuse them for real systems.**

## User Permissions

| Action | Operator | Maintenance | Administrator |
|---|:---:|:---:|:---:|
| View monitoring and history | ✓ | ✓ | ✓ |
| Start / Stop conveyor | ✓ | ✓ | ✓ |
| Acknowledge alarms and reset eligible faults | — | ✓ | ✓ |
| Change simulation settings / inject faults | — | — | ✓ |
| Use demonstration password generator | — | — | ✓ |

## Quick Functional Test

1. Log in as `admin` and start the conveyor. Speed should approach **1500 RPM**; steady simulated current should approach **4.5 A**.
2. Open **Administration / Settings** and inject a motor overload.
3. Verify the machine enters **FAULT**, the overload alarm appears, and **Start** is blocked.
4. Acknowledge the alarm. The fault must remain active while the overload condition persists.
5. Clear the injection and perform an authorized **Reset**; confirm the machine returns to a non-running ready state.
6. Review **Event History** and `logs/events.csv` for recorded actions.

## Testing & Documentation

The project owner reported **16/16 final functional acceptance tests passed**, covering authentication, permissions, machine operation, monitoring, alarms, fault recovery, logging, and project reopening.

Additional project files, if included in the ZIP:
- `docs/Engineering_Report.pdf` — technical report
- `TEST_RESULTS.md` / `TEST_RESULTS.csv` — detailed test records
- `evidence/` — exported LabVIEW interface and diagram images

## Limitations

The conveyor, motor, and sensors are simulated. The project does **not** control physical equipment, connect to a Siemens PLC, or implement a certified emergency-stop system. Demo passwords are intentionally public, and the password-generator utility is not intended for production security.

---

**Focus areas:** LabVIEW programming · Industrial HMI · State machines · Role-based control · Interlocks · Alarm management · Event logging
