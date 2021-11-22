---
title: Connecting a 12864 screen to an SKR v2.0
tags: []
keywords: 
last_updated: 08/09/2021
summary: "How to connect a 12864 screen to an SKR v2.0"
sidebar: mydoc_sidebar
permalink: skr_2.0_screen_12864.html
folder: mydoc
comments: false
toc: false
datatable: true
---

## Overview

The information here is aimed at connecting a Fysetc Mini v1.2 12864 display but it can also be applied to other 12864 displays (as long as they are ST7567 or ST7920 based).  

## Wiring

Connect EXP1 to EXP1 and EXP2 to EXP2.  

<ul id="profileTabs" class="nav nav-tabs">
  <li class="active"><a class="noCrossRef" href="#fysetc" data-toggle="tab">Fysetc Mini v1.2 12864</a></li>  
	<li><a class="noCrossRef" href="#reprap" data-toggle="tab">RepRapDiscount Full Graphic Smart Controller</a></li>
</ul>
  <div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="fysetc" markdown="1">

## Board.txt modifications

Add the following lines to the board.txt file

```
//Fysetc MINI 12864
lcd.encoderPinA=LCDENCA;  // B.2
lcd.encoderPinB=LCDENCB;  // E.7
lcd.encoderPinSw=LCDBTN;  // B.0
lcd.lcdCSPin=LCDEN;       // E.9
lcd.lcdDCPin=LCDCS;       // B.1
lcd.spiChannel=4;
SPI4.pins={ A.5, A.6, A.7 };
lcd.lcdBeepPin=LCDBEEP;   // C.5
led.neopixelPin=E.11;     // E.11
```

## Config.g

Add this line to config.g
```
M950 P1 C"E.10"
M42 P1 S0
G4 P500
M42 P1 S1

M918 P2 C30 F1000000 E4
M150 X1 Q1000000
M150 R255 U0 B0 P20 S1 F1
M150 R255 U0 B0 P20 S1 F1
M150 R255 U0 B0 P255 S1 F0
```

</div>

<div role="tabpanel" class="tab-pane" id="reprap" markdown="1">

## Board.txt modifications

Add the following lines to the board.txt file

```
//RepRap Discount Full Graphic Smart Controller
lcd.encoderPinA=LCDENCA
lcd.encoderPinB=LCDENCB
lcd.encoderPinSw=LCDBTN
lcd.lcdBeepPin=LCDBEEP
lcd.lcdCSPin=LCDCS
lcd.spiChannel=3
SPI3.pins={LCDD4, NoPin, LCDEN}
```

## Config.g

Add this line to config.g
```
M918 P1 E4
```

</div>

</div>

## Menu Files

Menu files must be uploaded to allow the display to generate the correct information. This can be done in two ways.
First, obtain the recommended menu files from [here](https://github.com/jadonmmiller/UltimateDuetMenuSystem/releases/)

### Method 1 - WiFi Mode only

Extract the contents of the zip file you downloaded above and place them in a folder called "Menu" on the SD card of the GTR. 

### Method 2

Activate the display using the config.g changes above.  
A side menu called "Display" should appear in DWC. Navigate to it and upload the zip file.  

### Troubleshooting

If the screen is showing artifacts/random characters on the screen, the following may improve/eliminate the issue

* Lower the SPI frequency by half. This is the F value in M918.  
* Reduce the length of the cable between the screen and the board.  
* Ensure that the cable between the screen and the board is routed away from other cables, especially motor cables.  
* Add a ferrite ring to the cable between the screen and the board.  

## Using the SD card slot on the screen

From 3.3RC3, it is possible to use the external SD card.  
To do so, add the following lines to your board.txt

```
sdCard.external.spiChannel=0
sdCard.external.csPin=A.4
sdCard.external.cardDetectPin=C.4
```
