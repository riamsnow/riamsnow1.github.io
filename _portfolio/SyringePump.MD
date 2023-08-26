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
```c
/**
* Syringe pump project 
* Team Kibosh
* @author Julian Delgado
**/

#include <AccelStepper.h>
#include <FastLED.h>
#define NUM_LEDS 14
#define DATA_PIN 5

// Create Stepper object
AccelStepper stepper(AccelStepper::DRIVER, 3, 2);

// Instantiate LED, Buttons, Potentiometer
CRGB leds[NUM_LEDS];
int pot = A5;
int green = 6;
int blue = 7;
int red = 8;
int forward_button = 10;
int reverse_button = 11;

int start_button = 9;
int stop_button = 12;


// Syringe diameters
float ten_ml = 14.5;
float twenty_ml = 18.9;

// Initialize Flow Rate, Syringe
float syringe_diameter = twenty_ml;
float flow_rate = 1.5;

// Stepper Calculations - 1/16 microstepping enabled
const float pi = 3.14159;
float flowrate_mms = flow_rate * 1000.0 / 60.0;
float temp = syringe_diameter / 2.0;
float syringe_area = pi * sq(temp);
float dist_rate = flowrate_mms / syringe_area;
float steps_per_second = dist_rate * 400.0;


void setup() {
  Serial.begin(9600);
  
  FastLED.addLeds<WS2812B, DATA_PIN, GRB>(leds, NUM_LEDS);
  FastLED.setBrightness(5);

  // Set stepper speed (constant speed)
  stepper.setMaxSpeed(4000);
  
  // Initialize RGB LED
  pinMode(red, OUTPUT); // Red
  pinMode(green, OUTPUT); // Green
  pinMode(blue, OUTPUT); // Blue

  // Initialize Limit Switch
  pinMode(stop_button, INPUT_PULLUP); // Limit Switch

  // Initialize Latching Button
  pinMode(start_button, INPUT_PULLUP); // Latching Button

  // Initialize forward and Counter-forward buttons
  pinMode(forward_button, INPUT_PULLUP); // forward
  pinMode(reverse_button, INPUT_PULLUP); // Counter-forward
}

void loop() {
  
// If limit switch is pressed
  if (digitalRead(stop_button) == HIGH && digitalRead(reverse_button) == HIGH) {
    analogWrite(red, 255);
    analogWrite(green, 0);
    analogWrite(blue, 0);
    for(int dot = 0; dot < NUM_LEDS; dot++) { 
            leds[dot] = CRGB::Green; //shows RED
            FastLED.show();
            leds[dot] = CRGB::Black;
            delay(15);
        }
    
  }
  
  // Idle state before new run, can mess with potentiometer
  else if (digitalRead(start_button) == HIGH && digitalRead(forward_button) == HIGH && digitalRead(reverse_button) == HIGH && digitalRead(stop_button == LOW)) {
    analogWrite(red, 200);
    analogWrite(green, 255);
    analogWrite(blue, 0);

    // Work with Potentiometer
    float pot_value = analogRead(pot);
    flow_rate = map(pot_value, 0, 1023, 0, 20);
    Serial.print("Current flow rate (mL/min): ");
    Serial.println(flow_rate);
    int num_leds_to_map = map(pot_value, 0, 1023, 1, 15);
    for(int i = NUM_LEDS; i > NUM_LEDS - num_leds_to_map; i--) {
      leds[i] = CRGB::White;
      FastLED.show();
    }
    for(int i = 0; i < NUM_LEDS - num_leds_to_map; i++) {
      leds[i] = CRGB::Black;
      FastLED.show();
    }


    
    flowrate_mms = flow_rate * 1000.0 / 60.0;
    dist_rate = flowrate_mms / syringe_area;
    steps_per_second = dist_rate * 400.0;
    stepper.setSpeed(steps_per_second);
    
    }
  // Start button pressed, green
  else if (digitalRead(start_button) == LOW && digitalRead(forward_button) == HIGH && digitalRead(reverse_button) == HIGH && digitalRead(stop_button == LOW)) {
    stepper.setSpeed(steps_per_second);
    stepper.runSpeed();
    analogWrite(red, 0);
    analogWrite(green, 255);
    analogWrite(blue, 0);
  }
  
  // If reverse button is pressed and hasn't been pressed yet, purple
  else if (digitalRead(reverse_button) == LOW && digitalRead(forward_button) == HIGH && digitalRead(start_button) == HIGH) {
    stepper.setSpeed(-1000);
    stepper.runSpeed();
    analogWrite(red, 255);
    analogWrite(green, 0);
    analogWrite(blue, 255);
  }

  // If forward button button is pressed and hasn't been pressed yet, blue
  else if (digitalRead(forward_button) == LOW && digitalRead(reverse_button) == HIGH && digitalRead(start_button) == HIGH && digitalRead(stop_button == LOW)) {
    stepper.setSpeed(1000);
    stepper.runSpeed();
    analogWrite(red, 0);
    analogWrite(green, 0);
    analogWrite(blue, 255);
  }   
}
```
