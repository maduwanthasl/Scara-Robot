

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
This project focuses on building and analyzing a **SCARA (PRRR)** robot arm with **4 Degrees of Freedom (DoF)**. It combines both kinematic analysis and practical implementation, including calculations for forward kinematics, inverse kinematics, and Jacobian analysis. The project culminates in a demonstration where the robot performs precise pick-and-place tasks and can **hold objects weighing up to 0.8 kg**.

**This SCARA robot is developed for industrial pick-and-place applications.**  
The manipulator consists of:  
- **A prismatic joint** for vertical motion.  
- **Three revolute joints** for horizontal movements and rotation.  
- **A gripper** for handling square and round objects.  

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

### **5. Homing Sequence**  
The homing sequence ensures that the robot starts from a known position:  

- The prismatic joint retracts to the lowest position.  
- Each revolute joint rotates to its home angle.  
- Limit switches provide feedback to confirm positions.  

As you can see in the video, the homing sequence begins with the gripper motor (joint 3). To determine the homing position, I used limit switches along with the following code:  

```cpp
void homing() {
  // Homing Stepper3
  while (digitalRead(limitSwitch3) != 1) {
    stepper3.setSpeed(-1100);
    stepper3.runSpeed();
    stepper3.setCurrentPosition(-1580); // When limit switch pressed set position to 0 steps
  }
  delay(20);

  stepper3.moveTo(0);
  while (stepper3.currentPosition() != 0) {
    stepper3.run();
  }

  // Homing Stepper2
  while (digitalRead(limitSwitch2) != 1) {
    stepper2.setSpeed(1300);
    stepper2.runSpeed();
    stepper2.setCurrentPosition(4350); // When limit switch pressed set position to -5440 steps
  }
  delay(20);

  stepper2.moveTo(0);
  while (stepper2.currentPosition() != 0) {
    stepper2.run();
  }

  // Homing Stepper1
  while (digitalRead(limitSwitch1) != 1) {
    stepper1.setSpeed(-1200);
    stepper1.runSpeed();
    stepper1.setCurrentPosition(-5000); // When limit switch pressed set position to 0 steps
  }
  delay(20);
  stepper1.moveTo(0);
  while (stepper1.currentPosition() != 0) {
    stepper1.run();
  }
  // Homing Stepper4
  while (digitalRead(limitSwitch4) != 1) {
    stepper4.setSpeed(-1500);
    stepper4.runSpeed();
    stepper4.setCurrentPosition(-8500); // When limit switch pressed set position to 0 steps
  }
  delay(20);
  // stepper4.moveTo(0);
  while (stepper4.currentPosition() != 0) {
    stepper4.run();
  }
}
```
**Homing** - https://github.com/maduwanthasl/Scara-Robot/blob/main/Videos/Homing%20Function/Homing%20Function.mp4


---

### **6. Pick and Place Application**  
The robot is programmed to pick objects from a defined source and place them in a target location.  

- Move to the pick position using the prismatic and revolute joints.  
- Grip the object using the servo-controlled gripper.  
- Transition to the target location and release the object.  

In the pick-and-place application, I saved 8 waypoints starting from its home position. Using the GUI, I configured these waypoints, which helped to better understand the movement of the joints and the gripper. After saving the waypoints and running the sequence, I achieved the following output:  

**Pick and Place Output** - https://github.com/maduwanthasl/Scara-Robot/blob/main/Videos/Pick%20and%20place/Pick%20and%20place.mp4


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

## **9. 3D Printed Parts**  

| ![pic 6 (2)](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/Full%20arm%20without%20wiring.png) | ![pic 6 (4)](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/Arm%20without%20wiring.png) |
|---|---|
<p align="center">
    <em>Figure 6: ARM without wiring </em>
</p>

The robot's design relies heavily on 3D-printed components, with over 100 hours of printing time invested to produce these parts. Each part was carefully designed to ensure functionality and precision:  

- **Gears**: Over seven different types of gears were printed to enable precise torque transfer and smooth motion across the joints.  
- **Link Components**: Critical parts for Link 1, Link 2, and Link 3 were printed to form the main structure of the robotic arm, allowing for stable and accurate joint movements.  
- **Z Holder**: This component supports the prismatic joint, ensuring reliable vertical motion and alignment.  
- **Limit Switch Contactors**: Custom 3D-printed parts that interact with limit switches to facilitate homing and accurate position detection.  
- **Gripper Mechanism**: Includes the gripping claws and structural supports necessary for securely holding objects during operation.  
- **Support Structures**: Temporary structures were printed alongside the main components to maintain the integrity of complex shapes during the printing process.  

These parts were printed using PLA+ material for durability and dimensional accuracy. All STL files are organized and available in the `/3D-Printed-Parts` folder for easy access and replication.  

---

## **10. Code Explanation**  
The robot is programmed using Arduino Uno, with future plans to transition to AVR register-based programming for enhanced control. The key programming aspects include:  

- **Forward Kinematics**: Calculates the end-effector position based on joint values, ensuring precise movement to desired coordinates.  
- **Inverse Kinematics**: Determines joint angles for a given position, enabling accurate trajectory planning for the robot arm.  
- **DH Table and Jacobian Matrix**: The Denavit-Hartenberg (DH) parameters were derived to construct the transformation matrix, while the manipulator Jacobian was calculated to analyze joint velocities and forces.  
- **Control Algorithms**: Implements control for stepper motors, including speed adjustments and precise motion handling.  
- **Gripper Control**: Manages the servo-controlled gripper to open and close efficiently based on commands.  

To facilitate communication between the computer and the Arduino Uno, serial communication was established at a baud rate of 115200. This allows for easy command input and real-time control without needing to manually alter the code for each operation.  

Future iterations will focus on optimizing the code and exploring advanced microcontroller programming techniques for better performance.  
 

---

## **11. Robot Details and Calculations**

### **11.1 Link Dimensions and Specifications**  
The SCARA robot has **4 Degrees of Freedom (DoF)** with a **PRRR joint configuration**.  

**Link Dimensions**:  
- a1 = 160mm — Link 1 length  
- a2 = 220mm — Link 2 length  
- a3 = 202mm — Link 3 length  
- d4 = 580mm — Prismatic joint length  

### **11.2 Coordinate Frame Assignment**  
The following figure illustrates the coordinate frame assignment for the SCARA PRRR robot, adhering to the Denavit-Hartenberg (DH) convention:  

![Coordinate Frame Assignment](https://github.com/maduwanthasl/Scara-Robot/blob/main/Pictures/Coordinate%20Frames.jpg)  

### **11.3 DH Table**  
The table below summarizes the DH parameters for the SCARA PRRR robot:  

| **Joint (i)**      | **aᵢ (mm)** | **αᵢ (°)** | **dᵢ (mm)**         | **θᵢ (°)**         |
|---------------------|------------|------------|---------------------|--------------------|
| 1 (Prismatic)      | 0          | 0          | d₁ (variable)       | 0                  |
| 2 (Revolute)       | 160        | 0          | 0                   | θ₁ (variable)      |
| 3 (Revolute)       | 160        | 0          | 0                   | θ₂ (variable)      |
| 4 (Revolute)       | 202        | 0          | 0                   | θ₃ (variable)      |
| 5                  | 0          | 0          | 580                  | 0                  |


### **11.4Forward Kinematics**

Forward kinematics calculates the position and orientation of the end-effector based on the joint angles and link lengths. Using Denavit-Hartenberg (DH) parameters, we define the transformation matrix for each joint. The transformation matrix is:

<p align="center">
  <img src="https://github.com/user-attachments/assets/55f509af-13c3-474f-8a48-537ff5206caa" alt="SCARA Robot" width="50%">
</p>
By multiplying the individual transformation matrices from base to end-effector, we get the final transformation matrix T . This matrix provides the position (x, y, z) and the orientation of the end-effector. The angles θ1, θ2, and θ3 are used to determine the robot’s orientation in space.

<p align="center">
  <img src="https://github.com/user-attachments/assets/88b55576-af50-4bdb-9f5c-051f1642d028" alt="SCARA Robot" width="50%">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/ec2ee10e-e7f9-4a29-92f0-bf62982926e4" alt="SCARA Robot" width="50%">
</p>

The Jacobian is derived using the partial derivatives of the forward kinematics equations.  

### **11.5Manipulator Jacobian Matrix**
The Jacobian matrix relates joint velocities to end-effector velocities. It is essential for analyzing the robot’s motion and controlling its speed and acceleration. For a PRRR manipulator, the Jacobianmatrix has two parts:

- Linear Velocity: The part of the Jacobian that maps joint velocities to linear velocities of the end-effector. It involves the cross product between the joint axes and the position vector.
- Angular Velocity: The part that maps joint velocities to angular velocities.

The Jacobian for the SCARA robot is given by:

<p align="center">
  <img src="https://github.com/user-attachments/assets/d17c3fa6-750b-44d6-ae88-0843819cb8f3" alt="SCARA Robot" width="50%">
</p>

---


## 11. References  
- SCARA Robot Design Basics: [Link](https://en.wikipedia.org/wiki/SCARA)  
- Arduino CNC Shield Documentation: [Link](https://www.aranacorp.com/en/using-an-arduino-cnc-shield-v3)  
- Processing Language for GUI: [Link](https://howtomechatronics.com/projects/scara-robot-how-to-build-your-own-arduino-based-robot)
- Scara Robot 3D Printed Parts: [Link](https://github.com/IVProjects/Engineering_Projects/tree/main/ProjectFiles/SCARA%20Robot)
  
---

Feel free to raise issues or contribute improvements to this project!

