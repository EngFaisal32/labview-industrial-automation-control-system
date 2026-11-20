# Authentication, Role Permissions and Lockout

| Permission | Operator | Maintenance Technician | Administrator |
| --- | --- | --- | --- |
| View machine status | Yes | Yes | Yes |
| Start / Stop conveyor | Yes | Yes | Yes |
| Acknowledge alarms | Restricted | Yes | Yes |
| Reset eligible faults | Restricted | Yes | Yes |
| Modify system/monitoring settings | No | No | Yes |

The role table follows the project requirements and user-reported permission tests; individual VI-level authorization checks were not independently inspected.

## Screenshot-supported tests
- **Administrator login:** status `Authenticated`, user `admin`, access level `Administrator`; three permission indicators active.
- **Lockout:** after 3 failed attempts, `Account locked for 30 seconds`; 22 s remaining at screenshot capture; no authenticated user.

Other reported functions include logout and automatic session timeout. The separate 10-digit number generator is a demonstration utility, **not a cryptographic password generator or authentication mechanism**. No real credentials belong in the public repository.
