# Release Notes

**Aircraft:** Pathfinder

**Hardware Revision:** 1.1 (ESC's inside frame without Heatsinks)

**PX4 Firmware:** 1.14.0

**Configuration Version:** 20260515-1

**Release Date:** 2026 05 15

**Repository Tag:** Pond & Qik2026

**Status:**

[] Development
[] Internal Test
[] Release Candidate
[x] Field tested
[] Production

---

# Overview

This is the drone and configuration that was flown in Pond and Qik in April and May 2026. This release establishes the baseline flight configuration for engineering validation.

Has a known issue of thermal currpution of the barometric pressre reading and not using acctual ambiant air pressure (always assumes 15 degrees celcious) this is a big issue when the outisde air id acctuatrrly minus 25degrees and the internal temperature has climbed to plus 50 degrees

---

# Configuration Summary

| Component         | Version |
| ----------------- | ------- |
| PX4 Firmware      | 1.14.0        |
| Parameter File    | 20260515 Pathfinder HW1.1 PX4-1.14.0        |
| Hardware Revision | 1.1        |
| Airframe          | pathfinder (Franky)        |
| Flight Controller | Pix32 V6       |
| ESC Hardware      | APD F120  |
| ESC Firemware     | Unknown |
| PDB               | Holybro PM07 |
| GPS               | Holybro H-RTK Unicore UM982       |
| Telemetry         | MicoAir        |
| Optical Flow      | MicoAir Optical Flow & Range Sensor MTF-02P     |
| Range Sensor      | MicoAir Optical Flow & Range Sensor MTF-02P     |
| Payload           | Towing sled & Tom's radar        |

---

# New Features

* High rate logging
* Mag only for startup
* New MicrAir OPtical flow and range sensor MTF-02P  from MTF-01P that had an 70cm offset over snow
* 10 degree Motor tilt
* Baseline for everything else

---

# Configuration Changes

Example:

* Increased RTL altitude from 30 m to 50 m.
* Reduced maximum tilt angle to improve stability.
* Updated battery failsafe thresholds.
* Improved EKF tuning.
* Increased logging rate.

---

# Hardware Changes

Document any hardware changes associated with this release.

Example:

* Updated ESC mounting.
* Relocated GPS.
* Improved enclosure cooling.
* Added vibration isolation.
* Revised antenna placement.

---

# Validation

Completed Tests

[x] Bench Test
[x] Hover Test
[x] Position Hold
[x] RTL
[x] Mission Flight
[x] Thermal Test (with damage to heat shrink due to over heating inside case)
[x] Endurance Flight (with damage to heat shrink due to over heating inside case)
[x] Payload Test

Additional validation performed:

---
none
---

# Performance Summary

| Metric              | Result |
| ------------------- | ------ |
| Hover Stability     | Great after motors were angles and compass was set to initilize only  |
| Flight Time         | 30 minutes       |
| Min operating Temperature | -25 celcious   |
| Maximum Temperature | -25 celcious       |
| GPS Performance     | Good       |
| RTL Performance     | Great       |
| Telemetry Range     | Great       |
| Payload Operation   | Great       |

---

# Compatibility

Compatible With

* Hardware Revision(s): all Pathfinders
* Battery: all
* Payload: all
* Remote Controller: MicoAir only
* Ground Control Software: all

Not Compatible With

* Remote Controller: ExpressLRS

---

# Upgrade Notes

NA
---

# Known Limitations

* Thermal curruption of the Barometric pressure sensor
* ESCs over heating on prolong flight
* Very sensitive to iceing
* testing above 0°C ambient not yet completed.

---

# Related Documents


---

# Approval

Prepared By: Carl Thibault 2026 07 06

---

Reviewed By: NA

---

Approved By: NA

---
