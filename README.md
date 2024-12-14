

# SCARA Robot (PRRR Configuration)

## Overview  
This repository contains the design, build process, and control of a 4-DoF SCARA robot. The robot features a prismatic joint and three revolute joints (PRRR configuration) and is designed for precise pick-and-place tasks. It includes a functional GUI, real-time control, and an Arduino-based system for motor control.

<p align="center">
  <img src="https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/1.jpg" alt="SCARA Robot" width="50%">
</p>
<p align="center">
    <em>Figure 1: Final SCARA Robot</em>
</p>

---

## 1. Introduction  
This SCARA robot is developed for industrial pick-and-place applications. The manipulator consists of:  
- A **prismatic joint** for vertical motion.  
- **Three revolute joints** for horizontal movements and rotation.  
- A **gripper** for handling square and round objects.  

The robot is controlled using an Arduino Uno and stepper motors through a CNC shield. The GUI simplifies user interaction, making the robot versatile for various tasks.  

---

## 2. Final Outcome  
The SCARA robot successfully performs pick-and-place tasks with smooth motion and precise control.  

![Final Robot](https://uniofmora-my.sharepoint.com/:v:/g/personal/maduwanthalhh_20_uom_lk/EcbVCx1UGktHjuAvCzXrOrEBrMkzmncUZcdw_dYVqHNYQA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=yIhCYn)  
*Figure 2: Final Robot Outcome*  

---

## 3. Building Process  

### **3.1 Frame**  
The frame provides stability for the entire setup. Made of lightweight aluminum, it ensures durability and precise movements.  

![Frame](insert-frame-photo-link-here)  

### **3.2 Joint 1: Prismatic Joint**  
The prismatic joint allows vertical motion and is powered by a lead screw mechanism coupled with a stepper motor.  

![Joint 1](insert-joint1-photo-link-here)  

### **3.3 Joint 2: Revolute Joint**  
The revolute joint enables horizontal rotation for broader workspace coverage.  

![Joint 2](insert-joint2-photo-link-here)  

### **3.4 Joints 3 and 4**  
These joints control finer rotations, including gripper orientation for precise object handling.  

![Joint 3 and 4](insert-joint3and4-photo-link-here)  

---

## 4. Wiring  
The wiring connects stepper motors, the CNC shield, and the Arduino Uno. Important points:  
- Use shielded cables for stepper motors to reduce noise.  
- Ensure correct polarity for stepper motor connections to avoid direction reversal.  
- Power supply: A 12V DC supply powers the entire system.  

---

## 5. Homing Sequence  
The homing sequence ensures that the robot starts from a known position:  
1. The prismatic joint retracts to the lowest position.  
2. Each revolute joint rotates to its home angle.  
3. Limit switches provide feedback to confirm positions.  

---

## 6. Pick and Place Application  
The robot is programmed to pick objects from a defined source and place them in a target location.  
1. Move to the pick position using the prismatic and revolute joints.  
2. Grip the object using the servo-controlled gripper.  
3. Transition to the target location and release the object.  

![Pick and Place](insert-pick-and-place-photo-link-here)  

---

## 7. GUI  
A user-friendly GUI is developed using **Processing**.  

### **Features**  
- Joint control via sliders and buttons.  
- Position control for end-effector coordinates.  
- Real-time feedback for joint angles and positions.  
- Gripper control for opening/closing actions.  

![GUI](insert-gui-photo-link-here)  

---

## 8. Bill of Materials  
| Item                  | Quantity | Description                      |  
|-----------------------|----------|----------------------------------|  
| Aluminum Frame        | 1        | Main structure                  |  
| Stepper Motors        | 4        | NEMA 17 motors                  |  
| Servo Motor           | 1        | For gripper control             |  
| CNC Shield            | 1        | Stepper motor driver interface  |  
| Arduino Uno           | 1        | Microcontroller                 |  
| Power Supply          | 1        | 12V, 5A                        |  
| Bearings              | 4        | For smooth joint motion         |  
| Screws and Nuts       | -        | For assembly                    |  

---

## 9. 3D Printed Parts  
The following components were 3D printed:  
- Gripper mechanism  
- Motor mounts  
- Joint covers  

All STL files are available in the `/3D-Printed-Parts` folder.  

---

## 10. Code Explanation  
The robot is programmed in Arduino, with the following key functions:  
- **Forward Kinematics**: Calculate the end-effector position based on joint values.  
- **Inverse Kinematics**: Determine joint angles for a given position.  
- **Control Algorithms**: Stepper motor control and speed adjustment.  
- **Gripper Control**: Open/close the servo-controlled gripper.  

The `code` folder contains:  
- `main.ino`: The primary Arduino sketch.  
- `functions.h`: Helper functions for kinematics and control.  

---

## 11. References  
- SCARA Robot Design Basics: [Link](https://example.com)  
- Arduino CNC Shield Documentation: [Link](https://example.com)  
- Processing Language for GUI: [Link](https://example.com)  

---

Feel free to raise issues or contribute improvements to this project!


![image](https://github.com/user-attachments/assets/e73a0e8b-2da9-4d07-ae71-0554e8a4b6c6)

