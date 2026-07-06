# Flashing Procedure

## Purpose

This procedure describes the standard process for installing PX4 firmware and applying the correct configuration to a supported aircraft.

Following this procedure ensures that every aircraft is configured consistently and remains traceable to its hardware revision, firmware version, and parameter set.

---

# Prerequisites

Before beginning, verify that you have:

* Correct PX4 firmware version
* Correct aircraft parameter file (`.params`)
* USB cable suitable for data transfer
* QGroundControl installed
* Flight controller powered via USB
* Repository access to confirm the correct hardware revision

---

# Step 1 – Verify Hardware Revision

Determine the aircraft hardware revision.

Examples:

* Legato HW1.0
* Legato HW2.0
* SnowSense HW1.0

Locate the matching directory within the repository:

```text
aircraft/
    <Aircraft>/
        HW-x.x/
            PX4-x.xx/
```

Confirm:

* Hardware revision
* PX4 firmware version
* Correct parameter file

---

# Step 2 – Flash PX4 Firmware

1. Connect the flight controller to the computer.
2. Open QGroundControl.
3. Select **Vehicle Setup**.
4. Open **Firmware**.
5. Flash the required PX4 version.
6. Wait for the firmware installation to complete.
7. Reboot the flight controller if required.

Do **not** load parameters before confirming the firmware version matches the repository.

---

# Step 3 – Load Parameters

After the firmware has successfully booted:

1. Open **Parameters**.
2. Select **Tools**.
3. Choose **Load from File**.
4. Select the validated `.params` file.
5. Confirm the parameter import.
6. Reboot the flight controller.

After rebooting, reconnect QGroundControl.

---

# Step 4 – Perform Required Calibrations

The following calibrations are specific to each aircraft and shall be completed after loading parameters.

## Required

* Accelerometer
* Compass
* Level Horizon

## As Required

* Radio
* Airspeed Sensor
* ESC Calibration
* Joystick
* RC Trim

Do not copy calibration values between aircraft unless specifically documented.

---

# Step 5 – Verify Hardware

Confirm that all installed hardware is detected correctly.

Typical checks include:

* GPS lock
* Compass availability
* IMU status
* Battery monitor
* Power module
* Telemetry radio
* RC receiver
* ESC communication
* Camera trigger
* Distance sensors (if installed)

Resolve any hardware faults before proceeding.

---

# Step 6 – Safety Verification

Before arming, verify:

* Propellers removed
* Correct airframe orientation
* Battery voltage reported correctly
* GPS functioning
* Compass healthy
* No critical PX4 warnings
* Failsafes enabled
* Correct flight modes configured

The aircraft shall not be flown with unresolved critical warnings.

---

# Step 7 – Functional Test

With propellers still removed:

* Arm the aircraft.
* Verify motor outputs.
* Confirm correct motor order.
* Confirm motor rotation direction.
* Verify RC input.
* Verify telemetry.
* Verify mode switching.
* Verify disarm function.

Correct any issues before installing propellers.

---

# Step 8 – Install Propellers

Install the correct propellers.

Verify:

* Correct rotation
* Tight fasteners
* No blade damage
* Adequate clearance

Perform a final visual inspection.

---

# Step 9 – Validation Flight

Conduct an initial flight in a safe test area.

Recommended checks:

* Stable hover
* GPS position hold
* Altitude hold
* Return-to-Launch (RTL)
* Battery monitoring
* Telemetry quality
* Flight log recording

Record any observed issues for future parameter revisions.

---

# Step 10 – Documentation

After successful validation:

* Record the flight date.
* Record the aircraft serial number (if applicable).
* Record the PX4 firmware version.
* Record the parameter file used.
* Commit any parameter changes to Git.
* Update release notes if required.

---

# Troubleshooting

If unexpected behavior occurs:

1. Verify hardware revision.
2. Verify firmware version.
3. Verify the correct parameter file was loaded.
4. Reboot the flight controller.
5. Recalibrate sensors.
6. Review PX4 messages in QGroundControl.
7. Inspect hardware connections.

Never assume a parameter file is compatible with a different hardware revision unless explicitly documented.

---

# Future Production Workflow

Current development process:

```text
Flash Firmware
      ↓
Load Parameter File
      ↓
Calibrate Sensors
      ↓
Validation Flight
```

Future production process:

```text
Flash Custom Firmware
        ↓
Automatic Startup Script
        ↓
Calibration
        ↓
Validation Flight
```

Once aircraft enter production, validated parameter files will be replaced by PX4 startup scripts that automatically configure the aircraft during firmware installation.
