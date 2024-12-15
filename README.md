

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

[![Video Preview](https://via.placeholder.com/600x400)](https://github.com/user-attachments/assets/54862c45-d594-4989-866d-df16e7200ece)

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

---

### Purchase Details  
| **Buying Stores** | **Payable To** | **Invoice ** | **Date**       |  
|-------------------|----------------|---------------|----------------|  
| Zenix            | 11,890         |                |                |  
| Tronic LK        |                |               |                |  
| Asian            |                |               |                |  
| Unitech          |                |               |                |  

---

### Itemized List of Components  
| **Description**                                                                                                                                                           | **Qty** | **Unit Price** | **Total Price** |  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------|----------------|-----------------|  
| 17HS4401 NEMA 17 Stepper with wire 0.4Nm (D Shaft 5mm)                                                                                                                   | 1       | $2,300.00      | $2,300.00       |  
| 2040 V Slot Aluminium Extrusion Profile Black 1m (Basic Quality) - Length (mm): 1000mm                                                                                   | 1       | $3,900.00      | $3,900.00       |  
| GT2 (Brown Anti-Slip Toothed Cloth, Rubber with Fiberglass) 6mm Open Timing Belt 1m                                                                                      | 2       | $350.00        | $700.00         |  
| GT2 16T 16 Teeth 5mm Bore 6mm Width Timing Pulley T16B5W6 - Color: Silver                                                                                                | 1       | $120.00        | $120.00         |  
| GT2 20T 20 Teeth 5mm Bore 6mm Width Timing Pulley T20B5W6 - Color: Silver                                                                                                | 3       | $120.00        | $360.00         |  
| GT2 20T 20 Teeth 8mm Bore 6mm Width Timing Pulley T20B8W6 - Color: Silver                                                                                                | 1       | $120.00        | $120.00         |  
| GT2 6mm Closed Loop Timing Belt 200mm                                                                                                                                     | 5       | $190.00        | $950.00         |  
| GT2 6mm Closed Loop Timing Belt 400mm                                                                                                                                     | 2       | $280.00        | $560.00         |  
| Openbuilds (Type A2 with Eccentric Spacer) POM Wheel Pulley Kit for 2020 V Slot Aluminum Profiles                                                                        | 8       | $360.00        | $2,880.00       |  
| 17HS4401 NEMA 17 Stepper with wire 0.4Nm (D Shaft 5mm)                                                                                                                   | 3       | $2,300.00      | $4,600.00       |  
| CNC Shield V3 Expansion Board for Engraving Machine                                                                                                                      | 1       | $490.00        | $490.00         |  
| 8mm Insulated Braided Sleeve High Temperature Tube 1m                                                                                                                    | 1       | $120.00        | $120.00         |  
| GT2 16T 16 Teeth 5mm Bore 10mm Width Timing Pulley T16B5W10                                                                                                              | 1       | $160.00        | $160.00         |  
| GT2 20T (With Teeth) 5mm Bore 6mm Width Idler Timing Pulley B5W6 - Color: Black                                                                                          | 1       | $260.00        | $260.00         |  
| GT2 16T 16 Teeth 5mm Bore 6mm Width Timing Pulley T16B5W6 - Color: Silver                                                                                                | 2       | $120.00        | $240.00         |  
| Arduino UNO Original Development                                                                                                                                         | 1       | $2,510.00      | $2,510.00       |  
| DRV8825 Stepper Motor Driver for CNC 3D Printer                                                                                                                          | 4       | $520.00        | $2,080.00       |  
| Cable Tie 15-inch 100 pcs                                                                                                                                                 | 1       | $300.00        | $300.00         |  
| M5 35mm Stainless Steel Hex Flat Socket Head Countersunk Screw                                                                                                           | 12      | $70.00         | $840.00         |  
| M5 16mm Stainless Steel Hex Flat Socket Head Countersunk Screw                                                                                                           | 6       | $40.00         | $240.00         |  
| M3 20mm Countersunk Bolt                                                                                                                                                  | 12      | $5.00          | $60.00          |  
| M4 15mm Countersunk Bolt                                                                                                                                                  | 18      | $10.00         | $180.00         |  
| Black 10mm 1 Bag (13.5m/Bag) Spiral Wire Wrapping Tube Cable Sleeves                                                                                                      | 1       | $800.00        | $800.00         |  
| 12V 10A Power Supply                                                                                                                                                      | 1       | $2,200.00      | $2,200.00       |  
| Jumper Cables                                                                                                                                                             | 1       | $140.00        | $140.00         |  
| Other                                                                                                                                                                    | 1       | $2,000.00      | $2,000.00       |  

---

### **Total Cost**  
| **Subtotal** | $29,110.00 |  
|--------------|------------|  
| **Adjustments** | $0.00 |  
| **Final Total** | **$29,110.00** |  


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

