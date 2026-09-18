# Project 003 - Multi-Source Power Continuity(In Progress)

The solar input reached 376 W in my saved readings. The full backup-power chain is still untested.

I started the power work with an EcoFlow 400W Portable Solar Panel and a BLUETTI Elite 200 V2 power station at my home lab in Gozo, Malta. I recorded input power, battery state of charge and thermal images before moving on to the UPS and generator stages.

Status: In progress  
Solar observation: 17 September 2026  
Record updated: 18 September 2026

![Portable solar panel deployed on the terrace](media/setup/solar-panel-deployed.jpg)

## What I found so far

- The saved charging readings show PV input between 349 W and 376 W.
- The battery display rose from 87% to 97% across the recorded session. The final capture shows 0 W PV input.
- Grid input and AC/DC output were displayed as 0 W in these captures. This stage observed solar charging, without a recorded external load.
- I photographed the panel arrangement and used a Testo 860i to observe the power station, cable connection, input area and panel surface.
- Power-station output, UPS battery operation and the generator-supported chain remain planned tests.

These are snapshots from one session, not a continuous power log or a maximum-output benchmark. I have not yet measured how long this setup can keep the lab running.

## Read the work

- [Solar charging baseline](docs/01-solar-charging-baseline.md): setup, recorded settings, input readings, SOC progression and the next measurement improvements.
- [Thermal observations](docs/02-thermal-observations.md): six paired visual and thermal views, spot temperatures and the limits of this first inspection.

## Current state

| Work | State |
| --- | --- |
| Solar panel to power station | Initial charging observation completed; repeatable measurements still to follow |
| Thermal inspection | Six paired views recorded; no controlled temperature-rise test yet |
| Power station supplying an external load | Planned |
| Power station supplying the CyberPower OLS3000EA UPS | Planned |
| UPS battery operation and return to input power | Planned |
| Daewoo GDA2500Di first start and charging test | Prepared equipment; commissioning and tests still to follow |
| Generator to power station to UPS to load | Planned; no continuity result yet |
| Critical-load demand and runtime | Not yet measured |

## What I will test next

I will build the chain in stages and record each result before adding another dependency.

| Stage | Planned work | What I will record |
| --- | --- | --- |
| 1. Power station | Supply a defined test load from the BLUETTI | Output power, SOC, operating time, temperature and load behavior |
| 2. Power station and UPS | Supply the UPS and a controlled load from the BLUETTI | UPS input acceptance, input/output readings, charging demand, alarms and load stability |
| 3. UPS battery | Remove the UPS input, then restore it | Whether the load stays running, operating time, battery state and return to normal input |
| 4. Generator | Commission the generator outdoors, then test charging the power station | Startup behavior, accepted charging power, stability and the checks required by the equipment manuals |
| 5. Combined chain | Connect generator, power station, UPS and controlled load | Behavior when the upstream source is removed and restored, including any alarms, interruptions or manual actions |
| 6. Lab services | Repeat with a defined critical-load set | Network reachability, usable services, restart order and measured runtime |

Before those runs, I will define the load, acceptance criteria and stop conditions. Generator compatibility, cable ratings and the appropriate earthing/protection arrangement need to be established before connecting the staged chain.

For the lab stage, a powered device alone will not be enough. I will check whether the network and the services I need remain usable, and separately record any recovery after an interruption.

## How this fits the lab

[Project 000](https://github.com/jaeho-min/operational-resilience-lab/tree/main/project-000-baseline) establishes the physical baseline. [Project 001](https://github.com/jaeho-min/operational-resilience-lab/tree/main/project-001-wireless-cellular-rf) records connectivity observations. [Project 002](https://github.com/jaeho-min/operational-resilience-lab/tree/main/project-002-network-failure-recovery) separates network and service recovery. Project 003 will test the power paths those systems depend on.

`NORMAL -> FAILURE -> DEGRADED -> RECOVER -> VERIFY`

The solar run establishes an input baseline. The failure, transition and recovery tests come next.

Failure is inevitable. Design the resilience.
