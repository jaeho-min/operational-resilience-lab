# What I will test next

The first run produced useful observations, but I need a better record of when each service stops and returns. The work below is planned or deferred; these are not completed results.

## Update from later testing

A later Project 003 power-continuity session introduced another useful network observation: Internet connectivity was found to be unavailable.

The exact onset time of the connectivity loss was not established.

The cause was not established, so the event is not being treated as evidence of a power-related network failure. I stopped the planned sequence rather than adding another test stage while the WAN state was uncertain.

Working connectivity was restored through a direct Starlink Ethernet connection. This demonstrated a manual degraded path for that situation, but it did not validate automatic or UDR7-based secondary-WAN failover.

This event reinforces the need to test LAN continuity, primary-WAN availability, secondary-WAN usability and router failover as separate conditions.

## Repeat the controlled restart

Before the next run I will record the router and application versions, the PC's exact Ethernet path, the selected camera, the active WAN and the test start time. I will use a common time reference for the restart action and the collected logs.

I will separately record:

- The final restart confirmation as T+0.
- Timestamped reachability to the local gateway and an external destination.
- First failure, subsequent successes and any further interruptions, rather than declaring recovery after one reply.
- Return of the management interface.
- A DNS lookup and a fresh web request.
- The access point and core-switch state.
- Each selected camera's LED state and first usable live view.
- Whether recording resumes, if recording is configured for that test.

I will keep complete logs and, where practical, a screen/video record with a visible clock. I will document the probe interval and timeout because those settings limit the precision of the reported timing.

The restart confirmation is the start of the experiment. The first observed service failure is a separate event. Reporting both will let me distinguish elapsed time after the action from the observed interruption interval.

I plan to repeat the run under comparable conditions and retain each result. I will report the number of runs, averages and variation for each defined milestone, including unsuccessful runs. I will not average unlike events such as management-screen return and live-video return into a single recovery figure.

## Validate the backup WAN

Starlink has already been observed to provide working Internet access when connected directly by Ethernet to a client device. However, the Starlink path remains unresolved when configured as the UDR7 secondary WAN, so router-level failover has not been validated.

The next step is to isolate the UDR7 WAN2 integration itself. I will record the relevant port assignment, address state and router status, make one change at a time, and confirm whether a downstream client can actually use Starlink through the UDR7.

Only after the secondary WAN works independently through the UDR7 will I test primary-WAN interruption while leaving the router running. That test will separately observe:

- selected WAN state
- local gateway reachability
- external reachability
- DNS resolution
- fresh web access
- any selected active sessions
- return to the primary WAN

I will define success criteria before each run, including what counts as sustained recovery.

A configured secondary WAN, a link indicator or a working direct Starlink connection will not by themselves be treated as evidence of successful UDR7 failover.

## Remaining dependencies

Two internet services do not remove the UDR7 from the path used by its downstream clients. They may also share local power, switch and cabling dependencies. Router failure, primary-WAN failure, core-switch failure and power failure need separate tests.

The phone's separate Starlink Wi-Fi connection is worth testing as a degraded working option. I will check actual tasks and time to usability, including how I return to the normal network, before treating it as a reliable procedure.

## Deferred fallback paths

| Candidate | Intended test | Current state |
| --- | --- | --- |
| Flint 2 cold standby | Start an alternate router, restore the needed configuration and reconnect selected clients | Deferred; no validated cutover time |
| USW-FLEX-2.5G-8 reduced network | Run selected essential devices when the core-switch path is unavailable | Deferred; topology and capacity still to define |
| PoE injector fallback | Supply a selected compatible AP/device independently of the core PoE switch | Deferred; complete power and data path still to test |
| Configuration recovery | Export, retain and restore a usable network configuration | Planned; no restore result |
| NAS/UPS shutdown and restart | Configure orderly shutdown, startup order and service checks | Unconfigured/deferred in this record |

The reduced network tests will define which services matter first, what equipment they need and how I return to the normal setup. Owning spare equipment is preparation; the cutover still needs to be exercised.

## Future Backlog and related work

Network segmentation remains planned. Candidate zones include infrastructure, cameras, environmental sensors, smart plugs, other IoT, guest, personal and work devices. Printer/MFP placement and the communication it requires are still to be decided. I have not completed or validated that segmentation architecture.

Project 003 owns power continuity. NAS/UPS shutdown and restart order cross-reference this network project because a powered router alone does not establish usable storage or applications. Broader backup/restore, identity access and maintenance work remain Future Backlog.

My next milestone is a repeatable record of service recovery: what failed, what continued to work, what action restored it and how I verified the result.
