**4DOF Robotic Arm Joint Control System (Simulink + Stateflow + Arduino)**

This project implements a manual control interface for a 4-DOF robotic arm, using MATLAB/Simulink, Stateflow, and automatic Arduino code generation.
The system allows the user to select a joint, adjust its angle, and confirm the new position, with real-time hardware-in-loop validation in SimulIDE.

**Project Overview**
*The system enables:*

Selecting one of the four robotic arm joints (J1, J2, J3, J4)

Adjusting the selected joint angle through a potentiometer

Confirming the new angle using a dedicated button

Driving servo motors connected to the Arduino

Visualizing and validating the whole system in SimulIDE

A Stateflow state machine controls transitions between joints and manages safe updates of angles.



**Two digital inputs:**

*SelectJointsForward*

*SelectJointsBackward*

*Stateflow timers ensure transitions occur only when buttons are held for the required duration.*


**Joint Angle Adjustment**

Potentiometer input on A1

Angle mapped from analog input → 0° to 180°

Confirmation button ensures accidental adjustments are avoided


**Joint Value Holding**

When switching joints:

Previously updated angles are stored and held

Only the active joint receives new angle values

Servo Motor Control


**Each joint controls a servo:**

J1 → Pin 10

J2 → Pin 9

J3 → Pin 6

J4 → Pin 5

State indicators output on:

state1 → Pin 2

state2 → Pin 4

state3 → Pin 7

state4 → Pin 8


**Hardware-in-loop Simulation (SimulIDE)**

**The controller is tested in SimulIDE with:*

4 servo motors

Potentiometer

Push buttons (Next, Previous, Confirm)

State LEDs

Arduino Uno

Real-time behavior matches Simulink outputs, validating the design.



**📁 Repository Contents**

This repository includes:

/SimulinkModel — Main Simulink and Stateflow controller

/ArduinoCode — Generated .hex and .elf files

/Images — SimulIDE circuit screenshots

Documentation of the state logic

README.md



**Technologies Used**

MATLAB / Simulink

Stateflow

Arduino Uno

SimulIDE (hardware-in-loop)

Servo Motor control

Real-time switching logic



**How to Use**

Open the Simulink model.

Generate code for Arduino using embedded coder.

Open SimulIDE and load the circuit.

Upload hex file to Arduino.

Interact using potentiometer and buttons.
