<!-- ---
layout: post
title: "Buttons and LEDs"
date: 2025-03-07
categories: projects audio
---

Audio equipment is snake oil. A family member bemoaned the excessive cost of a simple MIDI footswitch box, and I offered to build an alternative. It's essentially Baby's First Arduino Project - use buttons for input, LEDs as indicators, and serial communication sprinkled on top. Right?

## Board Selection - How many pins?

Right. We need one GPIO pin per LED, and one GPIO pin per footswitch. We *could* alternatively design around latching footswitches and wire them in-line with the LEDs to half the required GPIO. I've decided to keep them separate to allow the independent use of the LEDs for status and config information - more on that later. It's worth noting, also, that input matrixing can sometimes cut down on the required GPIO significantly as well. Fewer inputs benefit less from matrixing, however, as is the case with my six-switch design: A 2x3 input matrix would only save a single GPIO pin.

Just like the rest of the project, MIDI (and serial connections in general) is an extremely prolific and well-documented beginner topic. Software considerations can be abstracted away with one of the countless MIDI libraries, and hardware requirements are nearly identical for all of them: We need one TX pin for MIDI out, and one RX pin for MIDI in. To match the MIDI hardware spec, we only need a diode, an optocoupler, and a handful of resistors. I personally chose to use an Adafruit MIDI Featherwing simply to save space and waste less time on laying out my proto board.

If we omitted the DIN-5 and TRS connectors, and instead used only USB or BLE for MIDI communication, and also used a 2x3 input matrix for the footswitches, we could run the whole device off of a single Seeed Xiao. Something like an Unexpected Maker TinyS3, 

A <abbr title="A passive electrical component that limits current flow.">resistor</abbr> is used to control current.

A MOSFET is a type of transistor that amplifies or switches electronic signals.

*[MOSFET]: Metal-Oxide-Semiconductor Field-Effect Transistor

A _<span class="tooltip" data-tooltip="A passive component that resists current flow.">resistor</span>_ controls current.


| :-------- | ------: |
|Part                                                | Cost                |
| Unexpected Maker FeatherS3 with u.Fl antenna:      | $22.50              |
| MIDI FeatherWing:                                  | $6.95               |
| 6x Momentary Footswitches:                         | $9.69 ($20.99/lot 13)  |
| u.Fl to SMA Antenna Extension:                     | $1.76 ($8.78/lot 5)   |
| 6x Panel Mount LED Holders:                        |$1.32 ($10.99/lot 50)   |
| 2x Panel Mount DIN-5 Jacks:                        |$4.00 ($7.99/lot 4)    |
| 2x Panel Mount 3.5mm TRS Jacks:                    |$1.58 ($7.88/lot 10)    |
| 1590DD Aluminum Enclosure:                         |$16.89               |
| FeatherWing Doubler:                               |$7.50                |
| Total:                                             |$72.19 ($110.47)     |

 
/n
Additional
Stepped Drill Bit Set: $28.97
M6x0.5 Machine Tap: $6.99
 -->