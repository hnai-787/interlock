# Changelog

All notable changes to this project are documented here.
Format loosely follows [Keep a Changelog](https://keepachangelog.com/).

## [Unreleased]

### Added

### Changed

### Fixed

## [1.1.0] - 2026-09-08

### Added

- `DEMO.md`: a timed, ~5-minute live-demo script covering the pitch, the
  order to show the Proteus simulation and physical hardware, a video
  fallback, and honest answers to anticipated questions (including why
  adaptive/traffic-responsive timing was deliberately not added to this
  circuit).
- `CHANGELOG.md` (this file).
- Two new, programmatically-verified checks reported in `REPORT.md` §11:
  every simplified Boolean equation in
  `design/4way-signal-truth-table.xlsx` reproduces its own column's
  values across all 16 states (0 mismatches), and no state ever shows
  more than one road green at the same time (0 violations across all 16
  states).

### Changed

- `project.yaml`: `portfolio.featured` set to `true` -- this project
  showcases discrete digital-logic/hardware skills distinct from the
  software-heavy projects elsewhere in the portfolio.
- `README.md`/`REPORT.md`: documented the decision to make this project
  demo-ready rather than add an adaptive-timing software layer, and why
  (a discrete counter-and-decoder circuit has no path to accept outside
  sensor input without a fundamentally different architecture).

### Fixed
