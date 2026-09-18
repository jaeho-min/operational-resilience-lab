# Wi-Fi, wired internet and Starlink

Starlink is part of my connectivity work because it provides a different access path from the fixed connection. Having another service, making it work on its own, and making the lab recover through it are three separate tasks.

## Work recorded so far

My initial notes record Melita and Starlink Wi-Fi tests using the same computer, position and Ookla method. They also record two wired paths:

| Service | Path used |
| --- | --- |
| Melita | Melita connection through UDR7/LAN to the laptop |
| Starlink | Starlink Ethernet directly to the laptop |

I used the direct Starlink path because the UDR7 secondary-WAN integration was unresolved. That let me observe standalone connectivity, but the different paths prevent a controlled like-for-like router comparison.

The detailed laptop test captures and exact Wi-Fi/wired figures are not included in this release. I am retaining the test history without filling in missing numbers. My notes separately record an approximate Starlink application result of 193 Mbps download, 56 Mbps upload and 28 ms latency. This is an application observation, not a replacement for the laptop results or a sustained-service guarantee.

## Installed does not mean integrated

![Starlink dish and installation](../media/starlink-installation.jpg)

The photograph records the installed dish. The outstanding question is how the lab uses that connection when another path fails.

### Reusing an existing opening

The cable passes through one of six existing ventilation holes; I did not drill them. Thick masonry and moisture are familiar concerns in Maltese homes, where mesh-covered wall vents are a common feature. I removed the existing vent cover, fitted insect-screen tape to help keep insects out, and cut a piece of sponge to cushion the cable inside the opening. I added duct tape around the cable exit through the frame and insect screen. Because this is a rental, I am keeping new holes and permanent fixings to a minimum and reusing the existing features wherever practical.

The UDR7 secondary-WAN attempt remains unresolved. A phone connecting to separately available Starlink Wi-Fi is client-side fallback, not proof that the UDR7 switched its WAN. Project 002 owns that failure/recovery investigation; this page records the connectivity dependency.

## Remaining operational weaknesses

- A usable standalone connection does not yet provide a verified automatic route for every lab client.
- Alternative access services can still share local power, cabling, routers or client dependencies. Power continuity belongs primarily to Project 003.
- A throughput test does not demonstrate session survival, DNS recovery, remote-access recovery or reliable failback.
- I have not established whether external network dependencies are independent simply because the services have different names.
- The installation photo does not measure sky obstruction, weather performance or long-duration availability. Those need their own records.

## Follow-up

I will first document working standalone paths and compare like-for-like wired and Wi-Fi configurations where practical. The U7 Pro comparison remains a later phase covering 2.4/5 GHz, placement, client link quality, roaming and wired reference performance.

Once the secondary-WAN issue is resolved, Project 002 will test a deliberately interrupted primary connection with timestamps, client probes and application checks. Successful switching, time to restored service and return to the primary connection will be reported separately. None of those future results is being marked as passed here.
