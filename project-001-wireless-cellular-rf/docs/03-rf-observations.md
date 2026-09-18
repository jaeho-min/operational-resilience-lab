# Exploratory RF observations

I used a tinySA Ultra+ at one rack-shelf position below the CCTV equipment. My initial notes cover approximately one minute per band, using an external antenna recorded as ZA-048 in the setup notes. This was an exploratory scan, not a whole-building survey.

![RF measurement setup at the rack](../media/rf-rack-setup.jpg)

[Watch the short 2.4 GHz screen recording](../media/rf-rack-short.mp4). The supplied clip is approximately five seconds long; it is a short view of the changing trace, not a recording of the entire observation session.

## Initial notes

| Scan | Representative values recorded in my original notes | Observation |
| --- | --- | --- |
| Center 433 MHz, span 10 MHz | Marker near 431.496 MHz; approximately -96 to -107 dBm | I did not clearly observe a strong intermittent transmission during the brief window |
| Center 868 MHz, span 10 MHz | Marker near 863.131 MHz; approximately -93.7 to -106 dBm | I did not clearly observe a strong intermittent transmission during the brief window |
| Approximately 2.400-2.500 GHz, Ultra mode | Peaks near 2.47410 GHz / -37.8 dBm and 2.41971 GHz / -66.3 dBm | Multiple peaks were visible |

These approximate values come from my initial manual notes. They are not averages extracted from the short clip, and a changing trace need not reproduce those exact marker positions in every frame. The marker frequencies are points inside the sweeps, not identification of a specific transmitter.

## What needs improving

The antenna, its orientation and cable, nearby metal shelving, and the analyzer settings all affect what I see. I cannot compare absolute readings across these bands as if antenna response were identical, or convert these readings into calibrated field strength without the required corrections.

A quiet-looking interval does not establish that a band is unused. Brief transmissions may be missed, and a marker near the baseline is not automatically a received transmission. I have not identified an emitter or established that interference caused any cellular or sensor problem.

I also need to account for instrument behavior. The manufacturer's Ultra-mode documentation describes limitations with short, complex and wideband signals, including possible spurious responses. I will record the mode and settings and treat individual peaks cautiously. [tinySA Ultra-mode documentation](https://tinysa.org/wiki/pmwiki.php?n=TinySA4.Ultra)

The initial record does not contain a complete, consistent settings log for every band. In the next survey I will capture center/span, resolution bandwidth, sweep settings, attenuation, LNA state, detector/trace mode, spur-removal setting and calibration/self-test state, together with antenna and placement details.

## Next survey

I plan to repeat observations at the rack, elsewhere indoors, near the outside opening and on the rooftop where access is safe. I will use consistent observation durations and antenna geometry within each comparison, save settings and traces where supported, and repeat the sequence in separate time windows.

I will keep antenna comparisons separate from location comparisons so that I can tell which variable changed. Where useful, I will compare ordinary operating states of my own equipment, without assigning an RF peak to a device from frequency alone. I will not conduct intentional interference tests.

This work is about learning the local operating environment. It is not a regulatory compliance survey or a health-exposure assessment.
