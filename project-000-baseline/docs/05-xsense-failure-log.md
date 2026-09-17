# X-Sense registration failure log

[Back to Project 000](../README.md)

Not every part of Project 000 worked. The X-Sense deployment is retained as a failure record because local acknowledgement and application-level operation did not agree.

## Intended path

```text
Sensor -> RF -> SBS50 -> 2.4 GHz Wi-Fi -> application/cloud
```

## What happened

During device addition, the SBS50 announced that the device had been added. The application then reported a failure, and the resulting device entry remained offline.

The same overall pattern appeared across more than one device type, including smoke and leak detection devices.

## What I tried

- Repeated the addition process
- Moved the detector closer to the SBS50
- Used the detector test function
- Changed the SBS50 Wi-Fi connection
- Put the SBS50 and phone on the same 2.4 GHz Melita Wi-Fi environment
- Restarted the SBS50
- Repeated the process with more than one sensor type

## Decision

Because several device types produced a similar result, I treated a shared registration or connectivity path as a working hypothesis. I did not identify a confirmed root cause.

The subsystem remains:

```text
UNRESOLVED - DEFERRED
```

I stopped before spending more time on repeated pairing attempts without better diagnostics. The next run will capture device and application versions, timestamps, screenshots, and any available network or base-station logs.

The local `Device Added` message was not treated as success because the application-level connection was not operational.

