

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
In the SCARA robot building process, I first created a metal frame. I used a metal U-bar and a circular-shaped plate, soldering them as shown in Figure 3. To hold the Z-axis motor, I also soldered a plate. Afterward, I added screw holes to the grill and created two screw holes on the Z-holder plate. Additionally, I applied a coat of paint to resist metal corrosion.  

I also created screw holes in the U-bar to secure the aluminum extrusion. After that, I added a 40×20 aluminum extrusion to the U-bar using M5 20mm screws. This aluminum extrusion ensures smooth movement of the joints along the Z-axis.  


| ![pic 6 (2)](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/metal%20frame.png) | ![pic 6 (4)](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/metal%20frame%20with%20z%20motor.png) |
|---|---|
| Metal frame | Metal frame with z motor|
<p align="center">
    <em>Figure 3: Metal Frame </em>
</p>


### **3.2 Joints**  

| ![pic 6 (2)](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/3d%20printed%20parts.png) | ![pic 6 (4)](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/Assembled%203d%20printed%20parts.png) |
|---|---|
| Some 3D printed parts | Assembled Joints | 
| ![pic 6 (3)](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/Joint%203%20gear.png) | ![pic 6 (1)](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/Joint%203%20.png)|
| Joint 3 Gears | Joint 3 Assembled |
<p align="center">
    <em>Figure 4: 3D printed parts </em>
</p>

The joints of the SCARA robot are critical for achieving precise and smooth motion. Below is a detailed breakdown of the joint-building process.  

#### **3.2.1 3D Printed Parts**  
The main part of building this robot involved printing the 3D-printed components. Printing all the parts required over 100 hours using white PLA+ material. These parts included gears, mounting plates, and structural supports.  

#### **3.2.2 Linear Motion System**  
After printing the parts, I used 8mm diameter linear motion rods to construct the gear mechanism in the joints. To enhance torque, I incorporated 3D-printed gears into all joints. Most of the gear ratios were designed as 16:1, with some using a 4:1 ratio. These gears provided precise motion and controllable movements.  

To achieve smoother motion, I added 608RS bearings. For added friction with the gears, I modified small 8mm linear rods into a D shape using a grinder. By integrating suitable GT2 6mm closed-loop timing belts, the movement of the joints became more stable and reliable.  

Additionally, I added end-stop components made from 3D-printed parts. These help the robot identify when the arm has returned to its home position.  

#### **3.2.3 Challenges**  
The main challenge was ensuring that all belts were properly tightened and controllable to maintain smooth and precise motion throughout the joints.   

#### **3.2.4 Gripper Mechanism**  
The gripper is designed to handle objects of various shapes. It features a replaceable "hold cube" part that can be customized to grip different items. The gripper is powered by an MG 995 metal gear servo motor, which is well-suited for this type of application.  

#### **3.2.5 Sliding Mechanism**  
For the sliding mechanism, I attached a 3D-printed Z-plate to a **POM Wheel Pulley Kit**, which enabled smoother vertical motion. The Z-plate and pulley system significantly improved the performance of the prismatic joint.  

[![Video Preview](https://via.placeholder.com/600x400)](https://github.com/user-attachments/assets/a7ca6ed6-09e0-49c2-beae-47ccfda04f0f)

---

## 4. Wiring  

<p align="center">
  <img src="https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/Wiring.png" width="50%">
</p>
<p align="center">
    <em>Figure 5: SCARA Robot main wiring diagram  </em>
</p>
<p align="center"> <em> Credit - how to mechatronics </em> </p>
 
The wiring connects stepper motors, the CNC shield, and the Arduino Uno. Here are the main considerations and steps followed:  

### **4.1 Motor Silence and Calibration**  
In wiring, I primarily focused on reducing motor noise. To achieve smooth motor operation, the current limit of the motor drivers was carefully adjusted. This calibration ensures precise motor activation. Setting an incorrect value can cause the motor drivers to overheat and potentially damage them. To further enhance motor precision, I adjusted the precision selector to 1/4 or 1/8 microstepping.

### **4.2 Connections and Testing**  
I connected the motor wiring as shown in the diagram and tested the connections with an oscilloscope and multimeter. Limit switches were placed at the corners of the joints' movement range to allow maximum rotational angles. After placing the limit switches, I assigned the pins for X+, Y+, Z+, and coolant functionalities.  

### **4.3 Servo Motor Powering**  
Since servo motors require a stable current, I initially tested them using the Arduino Uno with the CNC shield. However, the servo motor only received 3V from this setup, which was insufficient. To address this, I powered the servo motor separately using a 5V power supply.  

### **4.4 Power Supply Configuration**  
To power the entire system, which includes:  
- Four NEMA 17 stepper motors  
- Arduino Uno with CNC shield  
- Four motor drivers (DRV8825)  
- A servo motor  

I decided to use a 12V 10A power supply. A 12V 5A power supply would not have been sufficient to run all motors simultaneously.  

### **4.5 Cable Management**  
For clean and organized wiring, I used “Spiral Wire Wrapping Tube Cable Sleeves” and secured them with tie tags. This arrangement keeps the wires neat and minimizes clutter.  

### **4.6 Testing**  
To test all motors, I used simple Arduino code to verify their operation. This helped ensure that the motors, limit switches, and control pins were functioning as expected.  

### **4.7 Key Points**  
- **Shielded cables** were used for stepper motors to reduce electrical noise.  
- Correct polarity was ensured to avoid reversing motor directions.  
- The 12V DC power supply provided reliable power for the entire system.  
 

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

<p align="center">
  <img src="https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/GUI.jpg" alt="SCARA Robot" width="50%">
</p>

A user-friendly GUI is developed using **Processing**.  

### **Features**  
- Joint control via sliders and buttons.  
- Position control for end-effector coordinates.  
- Real-time feedback for joint angles and positions.  
- Gripper control for opening/closing actions.    

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
| 17HS4401 NEMA 17 Stepper with wire 0.4Nm (D Shaft 5mm)                                                                                                                   | 1       | Rs. 2,300.00   | Rs. 2,300.00    |  
| 2040 V Slot Aluminium Extrusion Profile Black 1m (Basic Quality) - Length (mm): 1000mm                                                                                   | 1       | Rs. 3,900.00   | Rs. 3,900.00    |  
| GT2 (Brown Anti-Slip Toothed Cloth, Rubber with Fiberglass) 6mm Open Timing Belt 1m                                                                                      | 2       | Rs. 350.00     | Rs. 700.00      |  
| GT2 16T 16 Teeth 5mm Bore 6mm Width Timing Pulley T16B5W6 - Color: Silver                                                                                                | 1       | Rs. 120.00     | Rs. 120.00      |  
| GT2 20T 20 Teeth 5mm Bore 6mm Width Timing Pulley T20B5W6 - Color: Silver                                                                                                | 3       | Rs. 120.00     | Rs. 360.00      |  
| GT2 20T 20 Teeth 8mm Bore 6mm Width Timing Pulley T20B8W6 - Color: Silver                                                                                                | 1       | Rs. 120.00     | Rs. 120.00      |  
| GT2 6mm Closed Loop Timing Belt 200mm                                                                                                                                     | 5       | Rs. 190.00     | Rs. 950.00      |  
| GT2 6mm Closed Loop Timing Belt 400mm                                                                                                                                     | 2       | Rs. 280.00     | Rs. 560.00      |  
| Openbuilds (Type A2 with Eccentric Spacer) POM Wheel Pulley Kit for 2020 V Slot Aluminum Profiles                                                                        | 8       | Rs. 360.00     | Rs. 2,880.00    |  
| 17HS4401 NEMA 17 Stepper with wire 0.4Nm (D Shaft 5mm)                                                                                                                   | 3       | Rs. 2,300.00   | Rs. 4,600.00    |  
| CNC Shield V3 Expansion Board for Engraving Machine                                                                                                                      | 1       | Rs. 490.00     | Rs. 490.00      |  
| 8mm Insulated Braided Sleeve High Temperature Tube 1m                                                                                                                    | 1       | Rs. 120.00     | Rs. 120.00      |  
| GT2 16T 16 Teeth 5mm Bore 10mm Width Timing Pulley T16B5W10                                                                                                              | 1       | Rs. 160.00     | Rs. 160.00      |  
| GT2 20T (With Teeth) 5mm Bore 6mm Width Idler Timing Pulley B5W6 - Color: Black                                                                                          | 1       | Rs. 260.00     | Rs. 260.00      |  
| GT2 16T 16 Teeth 5mm Bore 6mm Width Timing Pulley T16B5W6 - Color: Silver                                                                                                | 2       | Rs. 120.00     | Rs. 240.00      |  
| Arduino UNO Original Development                                                                                                                                         | 1       | Rs. 2,510.00   | Rs. 2,510.00    |  
| DRV8825 Stepper Motor Driver for CNC 3D Printer                                                                                                                          | 4       | Rs. 520.00     | Rs. 2,080.00    |  
| Cable Tie 15-inch 100 pcs                                                                                                                                                 | 1       | Rs. 300.00     | Rs. 300.00      |  
| M5 35mm Stainless Steel Hex Flat Socket Head Countersunk Screw                                                                                                           | 12      | Rs. 70.00      | Rs. 840.00      |  
| M5 16mm Stainless Steel Hex Flat Socket Head Countersunk Screw                                                                                                           | 6       | Rs. 40.00      | Rs. 240.00      |  
| M3 20mm Countersunk Bolt                                                                                                                                                  | 12      | Rs. 5.00       | Rs. 60.00       |  
| M4 15mm Countersunk Bolt                                                                                                                                                  | 18      | Rs. 10.00      | Rs. 180.00      |  
| Black 10mm 1 Bag (13.5m/Bag) Spiral Wire Wrapping Tube Cable Sleeves                                                                                                      | 1       | Rs. 800.00     | Rs. 800.00      |  
| 12V 10A Power Supply                                                                                                                                                      | 1       | Rs. 2,200.00   | Rs. 2,200.00    |  
| Jumper Cables                                                                                                                                                             | 1       | Rs. 140.00     | Rs. 140.00      |  
| Other                                                                                                                                                                    | 1       | Rs. 2,000.00   | Rs. 2,000.00    |  

---

### **Total Cost**  
| **Subtotal** | Rs. 29,110.00 |  
|--------------|---------------|  
| **Adjustments** | Rs. 0.00    |  
| **Final Total** | **Rs. 29,110.00** |  



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

