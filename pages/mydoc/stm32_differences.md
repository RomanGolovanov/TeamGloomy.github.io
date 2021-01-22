---
title: STM32 Firmware Restrictions
tags: []
keywords: 
last_updated: 15/01/2021
summary: "Restrictions in the STM32 firmware compared to RepRapFirmware available on Duet3D hardware"
sidebar: mydoc_sidebar
permalink: stm32_differences.html
folder: mydoc
comments: false
toc: false
---

## Differences to [Duet3D's RepRapFirmware](https://github.com/Duet3D/RepRapFirmware)

* No support for 12864 Displays. Support has been added as part of release 3.2_4.  
* Configuration:
  * See [Driver Timings](https://github.com/gloomyandy/RepRapFirmware/wiki/driver-timings) for information about setting the correct timings.
  * See [Custom Commands and Gcode](https://github.com/gloomyandy/RepRapFirmware/wiki/Custom-Commands-and-GCode) for information about additional gcode and unsupported gcode.  