# The Starlink secondary-WAN attempt

Starlink provided internet when connected directly to my laptop through Ethernet. I then tried to use it as the UDR7 backup WAN, but the router did not reach a working secondary-WAN state.

That difference is the reason I kept this attempt in the project. The service working on its own did not complete the backup path for the lab.

## Configuration and observations

![Recorded WAN and port configuration](../media/wan-status.jpg)

| Item | Recorded state |
| --- | --- |
| Primary service | Melita, WAN1, port 4, Online |
| Intended backup | Starlink, WAN2, port 2, Offline |
| WAN mode | Failover Only |
| Port 2 link display | GbE |
| Starlink WAN address display | No IPv4 or IPv6 address shown |
| IPv4 configuration in my notes | Automatic / DHCP |
| IPv6 configuration in my notes | Disabled |

The screenshot shows a GbE link on the assigned backup port while WAN2 remains Offline. IPv6 being blank is consistent with it being disabled; it is not a separate diagnosis. The absence of a displayed IPv4 address and the offline state are observations, not proof of a particular root cause.

The displayed uptime percentages have no observation window attached in this excerpt. I am not using them as a measured availability result or SLA.

## What I tried

1. I checked standalone Starlink Ethernet with the laptop and obtained internet access.
2. I tried Starlink on UDR7 port 3 and then on WAN-capable port 2. I did not obtain a working secondary-WAN state in the recorded attempts. The screenshot documents the port 2 configuration.
3. In an earlier restart attempt, the UDR7, Melita WAN1 and U7 Pro returned online, and browsing worked again. Starlink still remained offline. That was a separate qualitative observation, not a second timed 3:50 result.

The standalone check showed that internet access through the tested Starlink path was possible at that time. It did not establish every cable, port or configuration condition for the later router integration.

## Outcome

I stopped this attempt with the integration unresolved. There is no successful automatic WAN-failover result in this record.

Configuration, address assignment, port roles and software behavior are areas to investigate. I have not isolated one as the cause. I also have not established whether the problem is reproducible under a fully documented, unchanged setup.

The next step is to get WAN2 independently usable by the router and verify client traffic through it. Only then will I test primary-link failure and return to the primary path.

## Later operational observation

During a later Project 003 power-continuity session, Internet connectivity was found to be unavailable while the UDR7 secondary-WAN path was still unresolved.

The exact onset time of the connectivity loss was not established.

I restored working Internet access by connecting directly through Starlink Ethernet. This provided a usable manual fallback for that situation, but it did not validate WAN2 operation or automatic failover through the UDR7.

The available evidence does not establish the cause of the connectivity loss, so this event is not being used to assign a failure cause to the router, ISP, or power chain.

## Why the separate phone connection matters

The phone's automatic connection to Starlink Wi-Fi, described in [the reboot observations](01-reboot-observations.md), bypassed the unresolved router integration. It gives me a candidate manual/client fallback path to test further, but it does not provide the same recovery behavior for wired lab equipment.

I need to answer two questions separately: can I personally get back online, and can the routed lab services recover through the intended backup path?

## Relationship to connectivity testing

Standalone Wi-Fi, wired speeds and subscription-plan context belong primarily to [Project 001](../../project-001-wireless-cellular-rf/README.md). This incident record uses the standalone result as context for the failed integration. It does not duplicate the speed comparison or treat throughput as proof of failover.
