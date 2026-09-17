# Operational Resilience Lab

Most home labs are built to stay online.

I built this one to find out how it fails, what keeps working, and whether recovery can actually be verified.

![Operational Resilience Lab](project-000-baseline/media/overview/lab-overview.jpg)

This is a home lab I built on Gozo, a small Mediterranean island. It covers infrastructure, networking, power, physical safety, environmental monitoring, and recovery.

The physical baseline is in place, but the system is still a work in progress. Starlink failover remains unresolved. The X-Sense sensor deployment is still offline. Solar input has been observed, but the full generator-to-battery-to-UPS chain has not yet been tested.

I document what worked, what failed, and what still needs testing.

## Operating model

NORMAL -> FAILURE -> DEGRADED -> RECOVER -> VERIFY

## Projects

### [Project 000: The Baseline](project-000-baseline/README.md)

Before testing failover and recovery, I needed a physical environment I could work in, inspect, and maintain.

This project covers the room conversion, equipment layout, cable routing, environmental controls, and initial safety preparations.

Further project records will be added as they are prepared for publication.
