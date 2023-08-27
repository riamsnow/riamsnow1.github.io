---
title: "Syringe Pump"
excerpt: "This syringe pump is capable of dispensing liquid at a minimum rate of 1 uL/min and maximum rate of 10 uL/min."
header:
  teaser: assets/img/Linear-Actuator-Assembly_2023-May-03_09-37-01AM-000_CustomizedView746686638_jpg.jpg
---
# Motivation
  * Syringe pumps are mechanical tools powered by motors, employed to gradually deliver fluids within a specified timeframe. Their applications are diverse, particularly in medical contexts and healthcare establishments, where they are utilized to dispense medications and other compounds. They also find utility in research environments for tasks such as microfluidic experiments, biomedical studies, and chemical analyses.

  * The advantages of syringe pumps encompass the prevention of contamination by minimizing the risk of fluid transfer between syringes. Furthermore, they facilitate the pumping of highly viscous fluids and exhibit a high degree of precision.

  * While the underlying concept of syringe pumps is relatively straightforward, ready-made choices available on the market can be costly, with prices reaching several hundred dollars.


# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6e364dfa52f909527c?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

# Operating Procedures
  * Once plugged in, the initial flow rate can be set by turning the potentiometer clockwise/counter-clockwise.
  * Press the black latching button to start/pause dispersal of liquid.
  * To adjust initial position of syringe, use the two red push buttons to advance/retract the syringe. Note: This operation can only be completed while the syringe pump is idle.
  * The syringe pump will stop automatically once dispersal is complete. Press the black latching button to put the pump in idle mode and retract the syringe to resume use.

# Off-the-shelf parts

|                                   Component                                   | Image |
|:-----------------------------------------------------------------------------:|:-----:|
|             200mm lead screw with 2mm pitch and 2mm lead (Qty: 1)             |   ![](/assets/img/lead-screw.png)             |
|                     1/4” x 8mm flexible coupling (Qty: 1)                     |   ![](/assets/img/coupler.png)                |
|                  200mm linear rod with 8mm diameter (Qty: 1)                  |   ![](/assets/img/linear-rod.png)             |
|              LM8UU Linear bearing for 8 mm diameter rod (Qty: 1)              |   ![](/assets/img/linear-bearing.png)         |
|                   2040 Aluminum Extrusion 1’ Length (Qty: 1)                  |   ![](/assets/img/aluminum-extrusion.png)     |
|                         Nema 17 Stepper Motor (Qty: 1)                        |   ![](/assets/img/stepper-motor.png)          |
| MEAN WELL RQ-65D AC-DC Power Supply Quad Output 5V 12V 24V 12V 4 Amp (Qty: 1) |   ![](/assets/img/power-supply.png)           |
|                        Arduino Mega 2560 Rev3 (Qty: 1)                        |   ![](/assets/img/arduino.png)                |
|                         A4988 Stepper Driver (Qty: 1)                         |   ![](/assets/img/stepper-motor-driver.png)   |
|                           Small Breadboard (Qty: 1)                           |   ![](/assets/img/breadboard.png)             |
|                   Panel Mount Latching Push Button (Qty: 1)                   |   ![](/assets/img/latching-button.png)        |
|                       Panel Mount Push Buttons (Qty: 2)                       |   ![](/assets/img/push-button.png)            |
|                             Limit Switch (Qty: 1)                             |   ![](/assets/img/limit-switch.png)           |
|                        RGB Common Cathode LED (Qty: 1)                        |   ![](/assets/img/rgb-led.png)                |
|                        10k Potentiometer (Qty: 1)                             |   ![](/assets/img/pot.png)                    |



# 3D Printed Parts

|                 Component                 | Image |
|:-----------------------------------------:|:-----:|
|      Syringe Wing Support (PLA)      |   ![](/assets/img/Wing_Support.png)           |
|      Syringe End Support  (PLA)      |   ![](/assets/img/Syringe_Support.png)        |
|      Carriage  (PLA)                 |   ![](/assets/img/Carriage.png)               |
|      Motor Mounting Plate  (ABS)     |   ![](/assets/img/Motor-Mounting-Plate.png)   |
|      Enclosure (PLA)                 |   ![](/assets/img/Syringe-pump-enclosure.png) |

# Wiring Schematic
<img src="/assets/img/syringepump_3.png"/>

# Arduino Code
See our Github repo [here](https://github.com/delgadjd/delgadjd.github.io/blob/develop/_portfolio/SyringePumpCode.ino).
