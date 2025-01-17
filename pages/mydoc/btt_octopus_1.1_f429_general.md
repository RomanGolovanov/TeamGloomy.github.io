---
title: BTT Octopus v1.1 F429 Version General Information
tags: []
keywords: 
last_updated: 17/08/2021
summary: "General information regarding the BTT Octopus v1.1 F429 Version"
sidebar: mydoc_sidebar
permalink: btt_octopus_1.1_f429_general.html
folder: mydoc
comments: false
toc: false
datatable: true
---

## Overview

This page covers any general information for the BTT Octopus v1.1 F429 Version board, which is supported from 3.4beta2.

{% include callout.html content="There are two types of BTT Octopus. One uses an STM32F446ZET6 and the other uses an STM32F429ZGT6. TeamGloomy and this port only support the STM32F429ZGT6 based boards. BTT provide a build with reduced features which can be found [here](https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0/tree/master/Firmware/RepRapFirmware/F446-OctoPus)" type="danger" %} 

### Driver Jumpers

The jumpers should be installed as below. "SPI mode Interpolation" is supported for TMC5160 drivers. "UART mode Interpolation" should be used when using smart drivers (i.e. TMC2208, TMC2209, TMC2225 and TMC2226)

{% include image.html file="btt_octopus_1.1_uart.png" alt="BTT Octopus v1.1 UART" caption="BTT Octopus v1.1 UART Driver Jumper Locations" %}  
{% include image.html file="btt_octopus_1.1_spi.png" alt="BTT Octopus v1.1 SPI" caption="BTT Octopus v1.1 SPI Driver Jumper Locations" %}  

### Initial Installation

Follow the [WiFi instructions](btt_octopus_1.1_f429_connected_wifi_8266.html) or [SBC instructions](btt_octopus_1.1_f429_connected_sbc.html)