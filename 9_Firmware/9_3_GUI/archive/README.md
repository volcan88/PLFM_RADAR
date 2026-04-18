# Archived GUI versions (GUI_V1 … GUI_V6)

These files are **historical prototypes** and are kept here only for reference
and for git-blame archaeology. **They are not supported and should not be run.**

The active, supported GUI is:

- `../radar_dashboard.py` — board bring-up dashboard (FT2232H reader, real-time
  R-D heatmap, CFAR overlay, waterfall, host commands, HDF5 recording)
- `../radar_protocol.py` — protocol layer (packet parsing, command building,
  FT2232H connection, data recorder, acquisition thread)
- `../smoke_test.py` — board bring-up smoke test host script

## Why these are archived

- Mixed evolutionary steps: each of GUI_V1 … GUI_V6 bolted on a new feature on
  top of the previous one, rather than replacing it. Having all nine files in
  the main GUI directory made it unclear which one is current.
- The `Opcode` values used in several of these older files predate the RTL
  command-decoder alignment done in PR #1 and will therefore send the **wrong**
  bytes to the FPGA. Do not copy opcode logic out of these files.
- `GUI_V5.py` and `GUI_V6.py` contain a placeholder Google Maps API key
  (`"YOUR_GOOGLE_MAPS_API_KEY"`). Keeping the files out of the main directory
  reduces the chance of a real key being committed there by accident.

## Version notes (from the original `GUI_versions.txt`)

| File | Notes |
|------|-------|
| `GUI_V1.py` | First prototype |
| `GUI_V2.py` | Added STM32 USB CDC |
| `GUI_V3.py` | Added pitch to STM32 USB packet; pitch correction for elevation; Google Maps, real-time target plot, chirp duration 2 |
| `GUI_V4.py` | Added pitch correction |
| `GUI_V4_2_CSV.py` | GUI_V4 with CSV logging |
| `GUI_V5.py` | Added Mercury color scheme |
| `GUI_V5_Demo.py` | GUI_V5 in demo mode |
| `GUI_V6.py` | Added USB3 FT601 support |
| `GUI_V6_Demo.py` | GUI_V6 in demo mode |
| `GUI_V6.gif` | Animated demo capture of GUI_V6 |
