# Commissioning Blockers and Incidents
Media capture times for the commissioning evidence are recorded in the [Evidence Index](05-evidence-index.md).

## Generator initial commissioning - no start

### Objective

Commission the generator before using it as an upstream source for later power-continuity testing.

### Observed sequence

- The generator was prepared with fuel and engine oil.
- No external electrical load was connected during the starting attempts.
- Several starting attempts had already been made with the choke engaged.
- After fuel flow was confirmed, subsequent attempts were made with the control in the RUN position.
- The engine did not start successfully during the recorded commissioning attempt.

### Decision

I stopped the commissioning attempt rather than escalating into component-level modification or disassembly on a new unit.

### Root cause

Not confirmed.

The available observations are not sufficient to assign the failure to a specific component.

### Status

Generator-supported power-continuity testing remains deferred pending replacement or successful recommissioning.

### Evidence

- [`generator no-start-attempt.mp4`](../media/commissioning/generator/generator%20no-start-attempt.mp4)

## KPS DCM300LEAK measurement instrument - mechanical defect

### Objective

Use the clamp meter as part of the electrical validation before extending the generator and power-chain tests.

### Observation

The clamp jaw showed visible mechanical misalignment and did not close correctly.

Because of that condition, I did not treat the instrument as suitable for trustworthy leakage-current measurement.

### Decision

Testing that depended on leakage-current measurement was deferred.

### What this does not establish

This does not establish an electrical leakage fault in the lab or generator chain.

The failed dependency was the measurement capability itself.

### Status

Warranty and replacement handling were started.

### Evidence

- [`kps-clamp-jaw-misalignment-redacted.mp4`](../media/commissioning/kps-dcm300leak/kps-clamp-jaw-misalignment-redacted.mp4)
- [`kps-clamp-jaw-misalignment-closeup-redacted.jpeg`](../media/commissioning/kps-dcm300leak/kps-clamp-jaw-misalignment-closeup-redacted.jpeg)


## Unexpected WAN interruption during power testing

### Context

During the later Grid -> BLUETTI -> UPS test sequence, Internet connectivity was unexpectedly lost.

The power test was stopped rather than continuing into another failure stage while the network state was uncertain.

### Decision

I did not use this run to claim WAN continuity or successful multi-WAN failover.

Working connectivity was restored by using a direct Starlink Ethernet connection.

### Root cause

Not confirmed.

The available evidence does not establish whether the interruption originated from the ISP path, the UDR7 WAN state, another upstream network condition, or timing coincident with the power test.

No causal claim is assigned to the BLUETTI or UPS.

### Evidence

- [BLUETTI state during interrupted run](../media/power-continuity/interrupted-run/bluetti-state-during-interrupted-run.jpeg)

Detailed test sequencing is documented in [Power Continuity Tests](03-power-continuity-tests.md).
