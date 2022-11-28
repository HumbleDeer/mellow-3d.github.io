---
title: Fly Gemini V2 General Information
tags: []
keywords: 
last_updated: 20/10/2022
summary: "General information regarding the Fly Gemini V2"
sidebar: mydoc_sidebar
permalink: fly-gemini_v2_general.html
folder: mydoc
comments: false
toc: true
datatable: true


---

## Overview

This page covers any general information for the Fly-Gemini-V2 board.  
It is currently available through [AliExpress](https://www.aliexpress.com/item/1005003536896114.html). 


### Driver Jumpers

The jumpers should be installed as below. "Common Interpolation" should be used for standalone drivers. "SPI mode Interpolation" is supported for TMC5160 drivers. "UART mode Interpolation" should be used when using smart drivers (i.e. TMC2208, TMC2209, TMC2225 and TMC2226)

{% 
include image.html 
file="fly-gemini-v2\fly_e3_jumpers.png" 
alt="Fly-Gemini V2 Driver Jumpers" 
caption="Fly-Gemini V2 Driver Jumper Locations" 
%}

### Driver Diag Pin

The driver diag pin is used for sensorless homing and stall detection.  
The Fly-Gemini-V2 **does not** have a way of disabling the diag pin as it is designed to be used with [Fly-2209 drivers](https://www.aliexpress.com/item/1005001877899893.html) which have a switch on the underside of them for disabling the diag pin.  Set the dip switch to 'ON' to enable the diag pin. 
If you plan on using endstops rather than sensorless homing and do not have the Fly-2209 drivers, you need to bend or remove the diag pin. 

### Fan Mosfets

The Fly-Gemini-V2 fan mosfets are replaceable.
Each mosfet (VS3622e) controls two of the fan outputs.
The orientation that the fan mostfet is plugged into the board doesn't matter.

{% 
include image.html 
file="fly-gemini-v2\fly_gemini_fan_mosfet.png" 
alt="Fly-Gemini-V2 Fan Mosfet" 
caption="Fly-Gemini-V2 Fan Mosfet" 
%}

### Fan Voltage

The fan voltage can be set using jumpers to either 5v, 12v and Vin.  
Set them as shown below.  

{% 
include image.html 
file="fly-gemini-v2\fly_gemini_fan_voltage.png" 
alt="Fly-Gemini-V2 Fan Voltage" 
caption="Fly-Gemini-V2 Fan Voltage"
%}

{% include important.html content="Fan2's voltage is also controlled by the above jumper and is not just Vin." %}

### Maximum Input voltage

#### Board/Bed Power

The board power input can handle voltage up to 30v.

#### Driver Power

The driver power input can handle voltage up to 62v.

{% include warning.html content="In industry, 30 volts is generally considered to be a conservative threshold value for dangerous voltage. The cautious person should regard any voltage above 30 volts as threatening, not relying on normal body resistance for protection against shock." %}

### Initial Installation

The board that you will receive doesn't have any firmware installed so when plugged into a computer, the board will show as an unidentified device.
Follow the [SBC instructions](fly-gemini_v2_sbc.html) to build an SD card with Fly OS. If you have purchased the optional [M2WE 16G eMMC & 5G Wifi board](https://www.aliexpress.us/item/3256804602300590.html) it will come with the FLY OS pre installed on the M2WE.  

{% include custom/can/sht_links.html %}