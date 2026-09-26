# Project 003 - Multi-Source Power Continuity (In Progress)

The solar input reached 376 W in my saved readings. Since then, the project has progressed into UPS battery-operation and source-transfer testing. The full generator-supported backup-power chain remains untested.

I started the power work with an EcoFlow 400W Portable Solar Panel and a BLUETTI Elite 200 V2 power station at my home lab in Gozo, Malta. I recorded input power, battery state of charge and thermal images before moving on to UPS continuity, source-transfer and generator commissioning.

Status: In progress  
Solar observation: 17 September 2026  
Power continuity tests: 25 September 2026  
Record updated: 26 September 2026

![Portable solar panel deployed on the terrace](media/setup/solar-panel-deployed.jpg)

## What I found so far

- The saved solar-charging readings show PV input between 349 W and 376 W.
- The battery display rose from 87% to 97% across the recorded solar session. The final capture shows 0 W PV input.
- Grid input and AC/DC output were displayed as 0 W in those solar captures, so that stage observed charging without a recorded external load.
- I photographed the panel arrangement and used a Testo 860i to observe the power station, cable connection, input area and panel surface.
- A controlled UPS grid-loss and recovery test completed with 129/129 successful LAN ping replies and 0% packet loss.
- A manual UPS source-transfer test from direct grid input to BLUETTI AC output completed with 217/217 successful LAN ping replies and 0% packet loss.
- A later upstream power-chain run was stopped after an unexpected WAN outage introduced an uncontrolled variable.
- Generator-supported testing remains incomplete because the generator did not start during initial commissioning.
- Leakage-current validation remains deferred because the KPS DCM300LEAK clamp meter developed a mechanical jaw-alignment problem.

The solar results are snapshots from one session, not a continuous power log or a maximum-output benchmark. The LAN continuity results apply only to the tested local network path and do not by themselves demonstrate WAN or Internet continuity. Full runtime and generator-supported continuity have not yet been measured.

## Read the work

- [Solar charging baseline](docs/01-solar-charging-baseline.md): setup, recorded settings, input readings, SOC progression and measurement limits.
- [Thermal observations](docs/02-thermal-observations.md): paired visual and thermal observations from the initial solar-charging stage.
- [Power continuity tests](docs/03-power-continuity-tests.md): UPS grid-loss testing, manual source transfer and the interrupted upstream test.
- [Commissioning blockers and incidents](docs/04-commissioning-blockers-and-incidents.md): generator no-start, KPS measurement-equipment defect and the unexpected WAN interruption.
- [Evidence index](docs/05-evidence-index.md): links between the test records and the published photos and videos.

## Current state

| Work | State |
| --- | --- |
| Solar panel to power station | Initial charging observation completed; 349-376 W recorded |
| Thermal inspection | Initial visual and thermal observations completed |
| BLUETTI supplying the UPS | Manual source-transfer test completed |
| UPS grid-loss battery operation and recovery | Completed; tested LAN path remained reachable with 129/129 replies and 0% packet loss |
| Grid-to-BLUETTI UPS source transfer | Completed; tested LAN path remained reachable with 217/217 replies and 0% packet loss |
| Upstream grid-loss run through BLUETTI and UPS | Attempted but stopped after an unexpected WAN interruption introduced an uncontrolled variable |
| WAN / Internet continuity | Not validated by the current power tests |
| Daewoo GDA2500Di commissioning | Initial start unsuccessful; root cause not confirmed |
| Generator-supported power chain | Deferred pending successful generator commissioning |
| Leakage-current measurement | Deferred because of KPS DCM300LEAK mechanical jaw defect |
| Critical-load runtime | Not yet measured |

## How this fits the lab

[Project 000](../project-000-baseline) establishes the physical baseline.  
[Project 001](../project-001-wireless-cellular-rf) records connectivity observations.  
[Project 002](../project-002-network-failure-recovery) focuses on network failure and recovery.  

Project 003 tests the power paths those systems depend on and separates power continuity from network and WAN behavior.

The project has now moved from baseline observation into controlled failure and source-transfer testing. The next stages are to complete generator commissioning, validate the remaining power-chain transitions under controlled conditions, and measure critical-load runtime separately from WAN behavior.

`NORMAL -> FAILURE -> DEGRADED -> RECOVER -> VERIFY`

Failure is inevitable. Design the resilience.
