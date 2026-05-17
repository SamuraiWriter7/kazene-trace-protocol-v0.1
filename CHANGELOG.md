# Changelog

All notable changes to Kazene Trace Protocol will be documented in this file.

This project follows a simple versioning approach during the early specification phase:

- `v0.x` for experimental and draft specifications
- `v1.0` for the first stable public specification
- Patch updates for corrections, clarifications, and validation fixes

---

## [0.1.0] - 2026-05-17

### Added

- Initial release of Kazene Trace Protocol v0.1.
- Added `schemas/trace-record-v0.1.schema.json`.
- Added `examples/trace-record.sample.json`.
- Added GitHub Actions validation workflow:
  - `.github/workflows/validate-specs.yml`
- Added repository overview in `README.md`.
- Added one-page overview:
  - `docs/one-page-overview.md`
- Added boundary documentation:
  - `docs/relationship-to-structure-fingerprint.md`
  - `docs/relationship-to-royalty-os.md`
  - `docs/rsl-bridge-notes.md`
  - `docs/c2pa-inspired-provenance-notes.md`
- Added `LICENSE`.
- Added `CITATION.cff`.
- Added this `CHANGELOG.md`.

### Defined

- Trace Protocol as an evidence layer, not a judgment layer.
- Trace Record as the core machine-readable object.
- Relationship between Trace Protocol and Structure Fingerprint.
- Relationship between Trace Protocol and Royalty OS.
- RSL bridge position as documentary and non-executable in v0.1.
- C2PA-inspired provenance position without implementing C2PA directly.
- Risk metadata as a required safeguard against overclaiming.

### Non-Goals Clarified

Kazene Trace Protocol v0.1 does not:

- prove legal ownership,
- enforce royalties,
- determine copyright infringement,
- make final origin judgments,
- implement RSL,
- implement C2PA,
- or trigger payment obligations.

### Notes

This release establishes the minimum public specification for recording structural trace evidence in AI-era creative works.

Trace Protocol v0.1 records the path of the wind.

It does not claim ownership of the wind.
