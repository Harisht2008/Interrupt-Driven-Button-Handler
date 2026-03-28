# Interrupt-Driven-Button-Handler
A button counter using hardware interrupts instead of polling. LED turns on after 5 presses and resets automatically.

## Components
- Elegoo Mega R3
- Push button
- LED
- 220 ohm resistor
- 10k resistor (pull-down)
- Jumper wires

## Wiring
Button → pin 2 (interrupt capable pin)
LED    → pin 10

## How It Works
attachInterrupt registers myISR to fire on every RISING edge
of pin 2. The ISR increments a volatile counter independently
of the main loop. The main loop checks the counter and turns
on the LED when it reaches 5.

## Concepts Demonstrated
- Hardware interrupt vs polling — processor responds to events
  automatically instead of checking constantly
- ISR design — kept minimal with no delay() or complex logic
- Volatile variables — prevents compiler from caching shared
  variables between ISR and main loop causing stale reads
- Interrupt independence — ISR fires even during delay() proving
  interrupts operate outside normal program flow

## Hardware Design Connection
Every processor ever made has an interrupt system. Keyboard
input, network packets, timer events — all use interrupts.
In chip verification you will encounter interrupt controllers,
priority systems, and masking logic constantly. Understanding
interrupts physically on hardware first makes those concepts
immediately intuitive when you encounter them in SystemVerilog.

## Images:
![IMG_3769](https://github.com/user-attachments/assets/3d8f3720-7b1a-4dd6-9387-ab8f57f09bd1)
![IMG_3769](https://github.com/user-attachments/assets/7e89b2a1-cc20-4aff-85a0-557cb799af90)
![IMG_3770](https://github.com/user-attachments/assets/72d7c4bb-5e24-45a4-8c9c-4e84d91e9637)

