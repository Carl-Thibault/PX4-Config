# PX4 Configuration Repository

## Purpose

This repository contains the official PX4 configuration files, documentation, and version history for all aircraft developed by MakeTech.

During development, aircraft configurations are managed using exported PX4 parameter files (`.params`). As hardware designs mature and move toward production, these configurations will gradually transition into PX4 startup scripts to allow automatic configuration during firmware flashing.

This repository is intended to provide complete traceability between:

* Aircraft hardware revision
* PX4 firmware version
* PX4 parameter set
* Flight validation
* Production release

---

# Repository Structure

```
PX4-Configuration/
│
├── README.md
├── CHANGELOG.md
├── docs/
├── common/
├── aircraft/
├── startup_scripts/
├── archived/
└── tools/
```

## docs/

Project documentation.

Examples:

* Flashing procedures
* Calibration procedures
* Parameter philosophy
* Production migration notes
* New aircraft setup checklist

---

## common/

General documentation describing common configuration decisions such as:

* Battery settings
* EKF tuning
* GPS configuration
* MAVLink configuration
* Failsafe strategy

This directory is documentation only and does not necessarily contain parameter files.

---

## aircraft/

Contains validated configurations for each aircraft.

Example:

```
aircraft/
    Legato/
        HW-1.0/
            PX4-1.16/
                Legato-HW1.0-PX4-1.16.0.params
                Release Notes.md
                Known Issues.md
```

Aircraft configurations are organized first by hardware revision and then by PX4 firmware version.

This allows historical configurations to be reproduced exactly.

---

## startup_scripts/

Reserved for future production startup scripts.

Initially this directory will remain empty.

Once aircraft reach production maturity, validated parameter files will be converted into PX4 startup scripts.

---

## archived/

Legacy parameter files, obsolete configurations, and retired hardware revisions.

Nothing should be deleted from this repository.

Instead, superseded configurations should be moved here.

---

## tools/

Utility scripts used to compare or analyze parameter files.

Examples:

* Parameter diff tools
* Validation scripts
* Automated consistency checks

---

# Naming Convention

Parameter files should use the following format:

```
<Aircraft>-HW<Revision>-PX4-<Version>.params
```

Examples:

```
Legato-HW2.0-PX4-1.16.0.params

Legato-HW2.0-PX4-1.16.1.params

SnowSense-HW1.0-PX4-1.16.0.params
```

Avoid filenames such as:

```
test.params
new.params
final.params
latest.params
```

The filename alone should identify exactly which aircraft and firmware the configuration belongs to.

---

# Versioning Philosophy

Hardware revisions are considered the primary version.

Firmware versions are secondary.

Repository organization follows:

```
Aircraft
    Hardware Revision
        PX4 Firmware Version
```

This reflects how aircraft are identified in the field.

---

# Development Workflow

1. Assemble aircraft.
2. Flash the desired PX4 firmware.
3. Configure the aircraft using QGroundControl.
4. Perform required sensor calibrations.
5. Conduct validation flights.
6. Export the complete parameter set.
7. Save the exported `.params` file in this repository.
8. Commit the changes to Git with a descriptive message.
9. Tag validated releases as appropriate.

---

# Required Per-Aircraft Calibration

The following calibrations are generally unique to each aircraft and should be completed after loading a parameter file:

* Accelerometer
* Compass
* Level Horizon
* Radio
* Airspeed sensor (if installed)
* ESC calibration (when applicable)

These calibrations are not intended to be transferred between aircraft.

---

# Production Roadmap

Current development strategy:

```
QGroundControl Configuration

        ↓

Export Parameters (.params)

        ↓

Git Version Control

        ↓

Flight Validation

        ↓

Production Release

        ↓

PX4 Startup Scripts
```

The parameter files maintained during development will become the reference used to generate startup scripts once aircraft enter production.

---

# Git Recommendations

Create commits whenever:

* Parameters are intentionally changed.
* Hardware revisions change.
* Firmware versions change.
* Flight validation completes.

Recommended tags:

```
Legato-HW2.0-R1

Legato-HW2.0-R2

SnowSense-HW1.0-R1
```

Tags should correspond to validated aircraft releases.

---

# Long-Term Goal

This repository is intended to become the single source of truth for all PX4 aircraft configurations throughout their lifecycle.

By maintaining complete version history and documentation, any released aircraft should be reproducible years later using the associated hardware revision, firmware version, and validated parameter set.
