# Power Continuity Tests

## Test 01 - UPS grid loss and recovery

### Objective

Verify whether the tested LAN path remains available when grid power to the UPS is removed and later restored.

### Test conditions

- CyberPower OLS3000EA operating ONLINE before the test
- UPS load: approximately 5%
- UPS output power: approximately 131 W
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

- [UPS baseline - 131 W output](../media/power-continuity/test-01-ups-grid-loss/ups-baseline-output-131w.jpeg)
- [UPS baseline - 5% load](../media/power-continuity/test-01-ups-grid-loss/ups-baseline-load-5pct.jpeg)
- [Test 01 - UPS grid loss and recovery video](../media/power-continuity/test-01-ups-grid-loss/test-01-ups-grid-loss-recovery.mp4)
