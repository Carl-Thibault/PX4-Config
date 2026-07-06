# Changelog

All notable changes to the PX4 Configuration Repository will be documented in this file.

The format is based on *Keep a Changelog*, and this repository follows semantic versioning for repository releases where practical.

## Types of Changes

* **Added** – New aircraft, documentation, scripts, or features.
* **Changed** – Modifications to existing parameters or documentation.
* **Deprecated** – Features or configurations scheduled for removal.
* **Removed** – Deleted or retired configurations.
* **Fixed** – Corrections to parameter values or documentation.
* **Security** – Changes affecting system security or operational safety.

---

## [Unreleased]

### Added

* Initial repository structure.
* Documentation framework.
* Aircraft directory structure.
* Startup script directory reserved for future production use.
* Common configuration documentation.
* Utility tools directory.

### Changed

* Nothing yet.

### Fixed

* Nothing yet.

---

## [1.0.0] - 2026-07-06

Initial release of the PX4 Configuration Repository.

### Added

* Standard repository layout.
* README documentation.
* Versioning strategy based on hardware revisions.
* Parameter file naming convention.
* Development workflow documentation.
* Production migration roadmap.
* Calibration guidelines.
* Git tagging recommendations.

### Notes

This release establishes the repository structure that will be used for all future PX4 aircraft development.

Current workflow:

* Configure aircraft in QGroundControl.
* Export complete parameter set.
* Validate through flight testing.
* Commit parameter file to Git.
* Transition mature configurations to PX4 startup scripts during production.

Future releases will begin adding aircraft-specific parameter files, validation reports, and production startup scripts.
