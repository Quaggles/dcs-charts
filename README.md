# dcs-charts

A central repository for all of my DCS charts, if you want notifications when new versions are released create a Github account and click the watch button in the top right corner of the page:

![image](https://user-images.githubusercontent.com/8382945/210178949-51f73346-8842-42b4-ae86-75b22b656757.png)

## Table of Contents

[Aircraft Radar Detection Ranges](https://github.com/Quaggles/dcs-charts#aircraft-radar-detection-ranges)

[Aircraft Radar Lookdown Detection Penalties](https://github.com/Quaggles/dcs-charts#aircraft-radar-lookdown-detection-penalties)

[Aircraft RCS and IR Values](https://github.com/Quaggles/dcs-charts#aircraft-rcs-and-ir-values)

# Aircraft Radar Detection Ranges

## Chart Description/Methodology

A chart showing the detection ranges of all air to air radars in DCS, all values are hand tested with the conditions listed at the top of the chart, I wrote a script to give me a [realtime debug window](https://cdn.discordapp.com/attachments/287928410687406080/1035942996622979082/unknown.png) showing me the target aircraft ranges and lookdown angles so I can test them all quickly without having to open the F10 map and use a ruler.

Modules that model Probability of Detection (Mirage 2000C and JF-17) add an extra level of complication, to measure those I have an [array of 10 aircraft flying directly towards me](https://cdn.discordapp.com/attachments/287928410687406080/1035943238256836628/unknown.png) while I'm in active pause, as they get closer I wait until I detect 1%, 50% and 100% of jets per sweep and record those ranges. All target aircraft have no payload/stores and fly at an aspect angle of 180 degrees (Directly head to head)

## Changelog/Summary

* F-15C radar correction is in 🎉 In RWS HPRF it has gained over 20nmi range which now puts it just shy of the F-14 Tomcat's RWS
* F-14's new AGC trace line now allows RIOs to spot targets that have not yet exceeded the return threshold to classify them as a target, by looking for spikes in the AGC line above the background noise I spotted a Flanker 30% farther than waiting for it to become a brick in PD Search
* After my last chart but prior to DCS 2.8 the Mirage 2000C radar had a minor reduction of detection range. This is most noticeable in the RWS Unfiltered (3-6nmi reduction)

(Click image for fullscreen)
![image](https://user-images.githubusercontent.com/8382945/210195335-8f7fad97-9655-4405-be0b-913922ea386a.png)

# Aircraft Radar Lookdown Detection Penalties

## Changelog/Summary

There has been a lot of discussion about lookdown penalties recently so I thought I'd test it all and share my results so the discussion goes beyond anecdotal experiences

All ED modules have a massive penalty that will come into effect around 1.5° and 2° lookdown angle in all PRFs ([Exact formula discovered here](https://www.reddit.com/r/hoggit/comments/who13a/dcs_2716_aircraft_radar_lookdown_penalties_chart/ij7du4h/)), as an example with the Hornet as soon as you pass that angle your detection range drops by 33% from 48nmi to 32nmi. Beyond that 2° cutoff there is no further penalty, even down to 15-30° lookdown. This behaviour has not changed since at least February 2022 (See chart notes for more details)

JF-17 also has a pretty sharp penalty in RWS HPRF past 2.5° dropping detection range by ~20% and a minor MPRF penalty that's only noticeable past 7.5°, Velocity Scan has no penalties. Most other modules have either 0 or minor penalties that won't be particularly noticeable in real world gameplay.

(Click image for fullscreen)
![image](https://user-images.githubusercontent.com/8382945/210195354-dda9879d-6b80-462a-b192-b753f5e8a057.png)

# Aircraft RCS and IR Values

Values gathered from https://github.com/Quaggles/dcs-lua-datamine

(Click image for fullscreen)
![image](https://user-images.githubusercontent.com/8382945/210195363-d8803e4b-ce1d-440c-89a6-6f863acd3d22.png)
