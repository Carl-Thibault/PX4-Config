# Calibration Procedure

## Purpose

This document defines the standard calibration procedure for PX4-based aircraft. Proper calibration ensures that sensor data is accurate and consistent across all aircraft while maintaining repeatability between hardware revisions.

Calibration should be performed:

* After flashing new firmware.
* After loading a parameter file.
* Whenever a sensor is replaced.
* After significant structural changes.
* Whenever flight behavior indicates a calibration issue.

---

# General Rules

* Remove propellers before beginning.
* Perform calibrations indoors or in a calm environment where appropriate.
* Keep the aircraft stationary unless instructed otherwise.
* Ensure the battery is adequately charged.
* Complete all required calibrations before the first flight.

---

# 1. Accelerometer Calibration

## Purpose

Calibrates the inertial measurement unit (IMU) so PX4 correctly determines aircraft attitude.

## Procedure

1. Open **Vehicle Setup → Sensors**.
2. Select **Accelerometer Calibration**.
3. Follow the prompts.
4. Place the aircraft on each requested face.
5. Hold the aircraft completely still until each position is accepted.

## Verification

* Artificial horizon matches aircraft orientation.
* No accelerometer warnings.
* Calibration completes successfully.

---

# 2. Compass Calibration

## Purpose

Determines the magnetic offsets required for accurate heading estimation.

## Procedure

1. Remove nearby ferrous objects.
2. Start **Compass Calibration**.
3. Slowly rotate the aircraft through all requested orientations.
4. Continue until calibration completes.

## Verification

* No compass errors.
* Heading changes smoothly.
* GPS heading is stable outdoors.

---

# 3. Level Horizon Calibration

## Purpose

Defines the aircraft's true level attitude.

## Procedure

1. Place the aircraft on a verified level surface.
2. Select **Level Horizon**.
3. Wait for completion.

## Verification

When sitting on a level surface, the artificial horizon should indicate level flight.

---

# 4. Radio Calibration

Required whenever a new transmitter or receiver is installed.

Verify:

* Full stick travel.
* Correct channel assignments.
* Correct switch assignments.
* No unintended inputs.

---

# 5. ESC Calibration (Typicaly Not Required)

Perform only if required by the installed ESCs.

Verify:

* All motors begin spinning together.
* Motor outputs are consistent.
* No desynchronization.

---

# 6. Airspeed Calibration (Typicaly not Installed)

Verify:

* Zero offset before airflow.
* Stable readings.
* Correct orientation.

---

# 7. Additional Sensor Calibration

As applicable:

* Distance sensors
* Optical flow
* Range finders
* Gimbals
* External magnetometers

Follow manufacturer recommendations where required.

---

# Post-Calibration Verification

After all calibrations:

* Reboot the flight controller.
* Confirm all sensors report healthy.
* Verify no calibration warnings remain.
* Verify GPS lock (if installed).
* Verify battery monitoring.
* Verify telemetry.

---

# Flight Validation

Before normal operation, perform:

* Stable hover.
* Altitude hold.
* Position hold.
* RTL test (when appropriate).

Record any abnormalities before releasing the aircraft.

---

# Recalibration Triggers

Recalibrate whenever:

* Firmware changes.
* Flight controller is replaced.
* Compass is relocated.
* GPS is relocated.
* Aircraft structure changes significantly.
* Persistent estimator warnings occur.
* Flight characteristics change unexpectedly.

Calibration data should never be copied between aircraft unless specifically documented and validated.
