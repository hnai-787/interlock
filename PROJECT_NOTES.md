# Project Notes

## Source

Migrated from `air-university-cybersecurity-projects/projects/4-way-traffic-signal-controller`
into this workspace as an independent project on 2026-09-07.

## Cleanup decisions

None needed — no build output or sensitive content in the source folder.

## Assumptions

None beyond what's stated in the README.

## Remaining work

None identified.

## 2026-09-08: Made demo-ready instead of adding adaptive-timing software

### Decision and why

The initial plan for this rebuild pass (consistent with the other 13
projects) was to add a software layer modeling adaptive/traffic-
responsive signal timing, as a "sharper angle" beyond the fixed 16-second
cycle. The project owner pushed back: this is a Digital Logic Design
project whose entire value is demonstrating discrete hardware/circuit
skills, and it depends on physical hardware that can't be meaningfully
extended by adding unrelated software in this session. Grafting a
software adaptive-control layer onto a discrete counter-and-decoder
circuit wouldn't showcase more hardware skill — it would just be a
different, unrelated project stapled on. Agreed, and changed direction:
instead of adding new functionality, this pass makes the existing,
already-solid project genuinely demo-ready.

### What was actually done

- **Cross-checked the truth-table spreadsheet against `REPORT.md`'s
  state table programmatically** (`openpyxl`, all 16 states) — confirmed
  a perfect match, not just visual similarity.
- **Verified every simplified Boolean equation in
  `design/4way-signal-truth-table.xlsx` actually reproduces its own
  column's truth-table values**, evaluating each equation against the
  counter inputs (A/B/C/D) for all 16 states — 0 mismatches. This had
  never been checked before; the spreadsheet's equations were previously
  taken on faith.
- **Verified the one real safety property this design should have**:
  no state ever activates more than one road's green signal
  simultaneously — checked across all 16 states, 0 violations.
- **Reviewed the referenced media/screenshots** (hardware photos, a
  Proteus block-diagram screenshot) directly for content and for any
  stray personal information (given a real redaction was needed in
  Project #7's screenshots) — found nothing to redact here.
- **Added `DEMO.md`**: a timed, ~5-minute live-demo script (what to show,
  in what order, a 30-second pitch, anticipated questions and honest
  answers -- including exactly how to answer "why not make it adaptive"),
  so this project can actually be presented, not just read.
- **Added `CHANGELOG.md`** (this project didn't have one yet).
- Updated `README.md`/`REPORT.md` to report the two new verifications
  performed and to document the adaptive-timing decision above as a
  deliberate, explained choice rather than an unexplained gap.
- Set `project.yaml`'s `portfolio.featured` to `true` — the project
  owner's own framing ("showcasing digital circuits and hardware
  knowledge") is a genuine, distinct skill area worth surfacing
  prominently in the portfolio alongside the software-heavy projects.

### Verification performed

Both new checks (`equations vs. truth table`, `no-double-green safety
property`) were run with a real Python script against the actual
`.xlsx` file's actual cell values — not asserted from reading the
spreadsheet by eye. See the two new rows in `REPORT.md` §11.

### Remaining work / honest limitations

Unchanged from the original — see `README.md` "Limitations". No new
hardware or simulation work was performed; this pass is documentation
and verification only, which matches what was actually asked for.
