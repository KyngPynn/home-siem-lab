# Home SIEM Lab

A small SIEM for my home network, built with **Splunk Enterprise**, to practice monitoring Windows authentication events that matter in enterprise security.

## Overview
- **SIEM**: Splunk Enterprise on Windows
- **Log source:** Windows Event Logs from my desktop via local input
- **Focus:** Authentication monitoring (successful and failed logons)

## Detections
| Event ID | Meaning | Why it matters |
|----------|---------|----------------|
| 4625 | Failed logon | Repeated failures can indicate password guessing |
| 4624 | Successful logon | Helps spot unusual accounts, logon types, or times |

The SPL searches are in [`/queries`](queries/).

## Dashboards
![Cleared Logs](ClearLogs.png)
![Successful logons](SuccessfulLogins.png)

## What I learned
- How Windows logs authentication events and how to search them with SPL
- How to turn a search into a dashboard panel

## Next steps
- Add more log sources (e.g., Sysmon, router syslog) as well as including more machines than the local host
- Create alerts for repeated failed logons
- Test detections with safe simulated activity
