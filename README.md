# PCB Hotplate Project (KiCad)
## PCB Layout:
![PCB](Layout.png)
## Schematic: 
![Schematic](SCH.png)
## 3D Model:
![3D Modle](3d.png)
## Overview

This project is a custom designed PCB hotplate for reflow soldering, built around an Arduino Nano. The board reads real time temperature through an analog LMT85 sensor and displays live readings on an I2C OLED screen, with two push buttons for user control. The heating element is not a discrete part. It is the copper PCB trace itself, laid out in a serpentine pattern across roughly 3.4 meters of 1.3 mm wide, 1 oz copper. At room temperature that trace measures about 1.3 ohms, which would pull over 9 A at 12 V if driven at full duty cycle. Since copper resistance rises with temperature, the trace is self limiting: current settles toward 5 to 6 A as it heats past 200 degrees C. Heating is switched using a low side IRFB7545 power MOSFET, driven through a PN2222A transistor for proper gate level switching, with Schottky diode protection and bulk capacitance across the power rail to maintain stability during high current switching events. Firmware manages duty cycle to stay within the 5 A fuse and supply rating, especially during the cold start ramp.

## Objectives

Design schematic in KiCad

Create custom PCB layout with the heating element integrated directly into copper

Handle higher current safely across a wide range of trace resistance as it heats

Separate power and control sections

Apply proper trace width for the heating load and calculate expected current draw

## Tools Used

KiCad

ERC and DRC checks

PCB layout editor

3D viewer

## System Design

The board includes:

Power input section

Heating element output

Control circuit

Switching device (MOSFET or transistor)

Protection components

Power traces are wider to handle higher current.
Signal traces are separated to reduce noise.

## Design Considerations

Calculated trace width based on expected current

Added thermal relief on pads

Placed high current components close together

Kept control logic isolated from heating path

Used ground plane for stability

## Skills Demonstrated

Schematic capture

PCB layout design

Power electronics basics

Trace width calculation

Design rule verification

Component placement strategy

## What I Learned

Current affects trace width directly

Layout affects heat distribution

Component placement affects performance

ERC and DRC checks prevent costly mistakes

## Possible Improvements

Add temperature sensor feedback

Add PID temperature control
