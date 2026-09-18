# Next measurement plan

The first pass gave me starting values. Next I will repeat the tests, calculate averages and check how much the results vary. Everything on this page is planned unless explicitly identified as an existing observation.

## 1. Repeated cellular measurements

I plan to collect at least five runs per carrier, location, phone and time window. I will repeat the sequence in more than one time window rather than treat one morning as typical service.

For each group I will report the number of attempts, successful runs, arithmetic mean, median and minimum/maximum. I will retain the individual readings and record failures separately; a failed test will not silently disappear or be assigned an invented zero-speed result. I will not pool different locations or phone models into one carrier average.

I will aim to use the same test server for paired comparisons, log any change, alternate carrier order, and leave consistent breaks between runs. I will record device/OS, SIM context, displayed network type, time zone, test server, battery/thermal state, background activity, VPN state, orientation and height. Wi-Fi will be disabled for the cellular tests.

Repeated tests consume data, so I will check allowances and choose a manageable test schedule before starting.

## 2. Other phones at the same positions

I will repeat the measurements with another phone model at the same marked positions. Where practical I will use the same SIM and service plan sequentially, document the order and avoid running competing throughput tests simultaneously.

This will be a device-and-network comparison, not proof that any difference comes from the antenna alone. Modem, band support, software, temperature and serving-network conditions may all contribute. Radio metrics such as RSRP, RSRQ and SINR will be logged where available; unavailable fields will remain blank rather than inferred from speed.

## 3. Multiple RF locations

I will expand the single rack position to other indoor positions, the outside opening and the rooftop. The survey will use repeatable positions, heights, antenna orientations, durations and settings. Different antenna setups will have separate records. I will retain raw traces/screenshots where supported and distinguish persistent features from brief observations.

## 4. Building context

I will measure selected wall/opening depths more systematically, record floor changes and door/window states, and compare nearby reference positions. The initial 20-30 cm and 40-50 cm dimensions are approximate property observations. I will not calculate material attenuation from speed tests alone.

## 5. Usable degraded service

I will define essential tasks before setting pass criteria: messaging, a voice/video call, remote administration, documentation access and a small file transfer. I will record whether these work on the fallback path, including when another transfer is running.

Thresholds will depend on the task and will be written before the test. Connection availability, time to operational service, latency under load and upload capability matter alongside headline download speed.

Router failover and recovery timing are primarily Project 002 work. These connectivity measurements will supply its baseline, not substitute for its failure tests.

## Future Backlog - not yet performed

- U7 Pro placement, 2.4/5 GHz, roaming and wired-versus-wireless reference tests.
- Cross-city cellular observations in locations such as Seoul, Valletta, Lisbon and Bucharest, using comparable location categories rather than ranking cities.
- A portable Flint 2 setup using accommodation Wi-Fi or cellular, with captive portal, repeater mode, stable internal SSID, direct-versus-router throughput, VPN on/off, reconnect and hotspot fallback tests.
- Time-to-operational: measure the sequence from unpacking and powering the router to upstream access, laptop connectivity, VPN where required, MFA and usable work services.
- Offline documents, diagrams, recovery checklists, reservations, local Git work, notes and contacts.
- Identity recovery with hardware keys, backup access and recovery codes, without publishing secrets.
- Charger/cable compatibility and portable USB power observations, cross-referenced to Project 003.

Portable RF equipment is not part of my planned airport, event or public-area testing. Travel work will use ordinary connectivity equipment on networks and devices I am authorized to use.
