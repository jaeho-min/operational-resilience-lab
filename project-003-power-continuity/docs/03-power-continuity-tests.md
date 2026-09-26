# Power Continuity Tests
Media capture times are recorded separately in the [Evidence Index](05-evidence-index.md).

The capture timestamp identifies when a file was recorded; it does not necessarily establish the exact onset time of an observed event.

## Test 01 - UPS grid loss and recovery

### Objective

Verify whether the tested LAN path remains available when grid power to the UPS is removed and later restored.

### Test conditions

- CyberPower OLS3000EA operating ONLINE before the test
- UPS load: approximately 4%
- UPS output power: approximately 132 W
- Monitoring PC powered from a separate grid socket
- PC Wi-Fi disabled
- PC connected by Ethernet through the lab switch
- NAS and mini-PC workloads were not included in this test
- Ping target: `[LOCAL_GATEWAY]`

### Sequence

1. Continuous ping monitoring was started.
2. Grid input to the UPS was switched off.
3. The UPS entered battery operation.
4. Battery operation was maintained for approximately one minute.
5. Grid input was restored.
6. The UPS returned to normal online operation.
7. Ping statistics were recorded after recovery.

### Result

```text
Packets sent:     129
Packets received: 129
Packets lost:     0
Packet loss:      0%

Minimum RTT:      0 ms
Maximum RTT:      9 ms
Average RTT:      0 ms
```
No UDR7 or switch reboot was observed during the recorded run.

### Conclusion

The tested LAN path remained reachable throughout the UPS grid-loss and recovery sequence.
This result demonstrates continuity of the tested LAN path only. It does not by itself demonstrate WAN or Internet continuity.

### Evidence

- [UPS baseline - 132 W output](../media/power-continuity/test-01-ups-grid-loss/ups-baseline-output-132w.jpeg)
- [UPS baseline - 4% load](../media/power-continuity/test-01-ups-grid-loss/ups-baseline-load-4pct.jpeg)
- [Test 01 - UPS grid loss and recovery video](../media/power-continuity/test-01-ups-grid-loss/test-01-ups-grid-loss-recovery.mp4)


## Test 02 - UPS source transfer from grid to BLUETTI

### Objective

Verify whether the tested LAN path remains available while the UPS input source is manually transferred from direct grid power to the BLUETTI power station.

### Sequence

1. Continuous ping monitoring to `[LOCAL_GATEWAY]` was started.
2. BLUETTI AC output was enabled.
3. The UPS input was disconnected from the wall outlet.
4. The UPS entered battery operation and its battery alarm was audible.
5. The UPS input was connected to the BLUETTI AC output.
6. The UPS accepted the BLUETTI source and returned to ONLINE operation.
7. Ping statistics were recorded after the source transfer.

### Result

```text
Packets sent:     217
Packets received: 217
Packets lost:     0
Packet loss:      0%

Minimum RTT:      0 ms
Maximum RTT:      10 ms
Average RTT:      0 ms
```
No interruption of the tested LAN path was observed during the recorded source-transfer sequence.
### Conclusion

The tested LAN path remained reachable while the UPS transitioned from direct grid input, through temporary UPS battery operation, to BLUETTI AC input.
This was a manual source-transfer test. It does not demonstrate automatic BLUETTI failover during an upstream grid outage.

### Evidence

- [UPS pre-test - 4% load](../media/power-continuity/test-02-ups-source-transfer/ups-pretest-load-4pct.jpeg)
- [UPS pre-test - 131 W output](../media/power-continuity/test-02-ups-source-transfer/ups-pretest-output-131w.jpeg)
- [Test 02 - UPS grid-to-BLUETTI source transfer video](../media/power-continuity/test-02-ups-source-transfer/test-02-ups-grid-to-bluetti-source-transfer.mp4)


## Interrupted run - Internet connectivity unavailable

### Context

During the broader source-transfer and power-continuity session, Internet connectivity was found to be unavailable.

The exact onset time of the Internet connectivity loss was not established. A BLUETTI state image was captured at 17:52, but that timestamp does not establish when the network interruption began.

### What happened

When I returned to check the online connection during the testing session, Internet access was already unavailable.

Because Internet connectivity had become an uncontrolled variable, I stopped the planned progression rather than continuing directly into another failure stage.

### Decision

This observation is not used to claim Internet continuity, automatic WAN failover, or a completed upstream-grid-loss test.

Working Internet access was restored by connecting directly through Starlink Ethernet.

### Root cause

Not confirmed.

The available evidence does not distinguish between:

- the primary ISP path,
- the UDR7 WAN state,
- another upstream network condition,
- or an event coincident with the power test.

No causal claim is assigned to the BLUETTI or UPS.

### Evidence

- [BLUETTI state associated with the interrupted run](../media/power-continuity/interrupted-run/bluetti-state-during-interrupted-run.jpeg)
- [Evidence Index and capture times](05-evidence-index.md)

## Test 03 - deferred

The planned next stage was to test the UPS as the final power source by removing BLUETTI AC output after establishing the intended upstream power condition.

This stage was not completed during the controlled sequence because the unexpected loss of Internet connectivity introduced an uncontrolled variable.

No continuity result is claimed for this stage.

Status: **Deferred**
