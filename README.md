# 4DOF Robotic Arm – Manual Joint Control System (Simulink + Stateflow + Arduino)

This repository contains a complete manual joint-control interface for a 4-DOF robotic arm.
The system is implemented using **MATLAB/Simulink**, **Stateflow**, and **automatic Arduino code generation**, and validated using **SimulIDE** for hardware-in-loop testing.

The user can rotate through joints (J1–J4), adjust the selected joint using a potentiometer, and confirm the updated angle. Servo motors respond in real time according to the Stateflow logic.

--------------------------------------------------------------------------------

## 🚀 System Features

- Manual selection of joints (J1 → J4)
- Potentiometer-based angle adjustment (0° → 180°)
- Confirmation button to read the new angle
- Safe switching logic with timers and debouncing
- Servo motor output for each joint
- LED indicators showing current active joint
- Full validation using SimulIDE virtual Arduino

--------------------------------------------------------------------------------

## 🎛️ Inputs & Outputs

### Inputs
- **SelectJointsForward** – go to the next joint
- **SelectJointsBackward** – go to the previous joint
- **Potentiometer (A1)** – angle control  
- **Confirm button** – read analog input for active joint

### Outputs (Arduino pins)
- J1 servo → **Pin 10**  
- J2 servo → **Pin 9**  
- J3 servo → **Pin 6**  
- J4 servo → **Pin 5**

State LEDs:
- state1 → Pin 2  
- state2 → Pin 4  
- state3 → Pin 7  
- state4 → Pin 8  

--------------------------------------------------------------------------------

## 🖥️ SimulIDE Hardware-in-Loop Testing

The project includes a full SimulIDE circuit (`project1.sim1`) allowing real-time testing with:

- Servo motors  
- Potentiometer  
- Push buttons (Forward / Backward / Confirm)  
- LEDs for state indication  
- Arduino Uno  

Screenshots included:
- `Screenshot 2025-10-27 222056.png`
- `Screenshot 2025-10-28 192236.png`
- `Screenshot 2025-10-30 003419.png`

These images show the working simulation setup.

```
4DOF_Robotic_Arm/
│
├── RobotArm.slx
├── RobotArm.slxc
├── RobotArm.hex
├── RobotArm.elf
├── RobotArm.eep
├── project1.sim1
├── Screenshot_*.png
└── README.md

```
## 🛠️ Tools Used

- MATLAB / Simulink
- Stateflow
- Embedded Coder for Arduino
- SimulIDE (hardware-in-loop testing)
- Arduino Uno
- Servo motor actuation

--------------------------------------------------------------------------------

## ▶️ How to Run

1. Open **RobotArm.slx** in Simulink.
2. Click *Build* to generate Arduino firmware:
   - RobotArm.hex  
   - RobotArm.elf  
   - RobotArm.eep  
3. Open **SimulIDE** and load `project1.sim1`.
4. Flash *RobotArm.hex* to the virtual Arduino.
5. Rotate joints using:
   - Forward button  
   - Backward button  
   - Potentiometer (angle)  
   - Confirm button  
6. Observe servo movements + state LEDs.

--------------------------------------------------------------------------------

## 👤 Author

**Ali Zein Khalifeh**  
Politecnico di Torino – Model-Based Software Design

--------------------------------------------------------------------------------

