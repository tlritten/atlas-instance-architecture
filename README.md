# atlas-instance-architecture
Interactive explainer for the ATLAS Narrative Template/Instance data flow, using a pump control system as a working example.

# ATLAS Pump Control — Narrative Template Flow

An interactive diagram explaining how ATLAS Narrative Templates and Instances work,
using a pump control system as a concrete example. Click any node to see a plain-language
explanation of what it does and how it connects to the rest of the system.

## What it shows

The diagram walks through three layers of the data pipeline:

**Layer 1 — Inputs:** How live hardware signals (runStatus, runCMD) and configuration
settings (MaxStartTimeSP, AutoEnabled) enter the system. Explains why templates carry
no I/O mappings — only instances do.

**Layer 2 — Computation:** How raw inputs are transformed into Conditions (named
booleans like StartRequested, FailedToStart) and Metrics (accumulated numbers like
TotalRunHours, FailedStartCount) using expression logic.

**Layer 3 — State & Outputs:** How conditions drive a five-state machine
(Unknown → Starting → Running → Stopping → Stopped), what each state writes to
physical I/O, and how the same conditions that power state transitions also fire
operator-facing alarms.

## Usage

Open `index.html` in any modern browser. No server, build step, or dependencies required.

- Use the **tabs** at the top to focus on one layer at a time, or view the full flow side-by-side
- **Click any node** to open the detail panel with explanations and expression examples
- The color language is consistent throughout: blue = live data, teal = settings/stable states,
  purple = conditions, coral = metrics, amber = transition states, red = alarms

## About ATLAS

ATLAS Config is a narrative-based industrial automation configuration platform by
[CrossnoKaye](https://crossnokaye.com). Narrative Templates define reusable control
logic; Instances deploy that logic against real hardware by mapping template inputs
and outputs to physical I/O points.
