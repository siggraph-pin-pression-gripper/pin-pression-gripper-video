# Project of Designing Pin-pression Gripper and Learning its Dexterous Grasping with Online In-hand Adjustment
## Introduction
In this project, we introduce a novel pin-pression gripper that features adjusting its finger shape to conform to the target object.
We carefully devise a reinforcement learning algorithm to handle the online grasping skills.


## Real-world demos
We develop a physical prototype of the pin-pression gripper. 

![](assets/Real-world/Sim2real.png)
![](assets/Real-world/real-world-1.gif)

### Hardware configuration: 
We utilize pneumatic cylinders as the actuators of our pin-pression gripper. Each cylinder is controlled via solenoid valves and relays, allowing for precise extension and retraction. To explore the minimum number of pin actuators in practice, the physical gripper is designed with a 3x3 resolution, weighing 2.3kg. Both gripper size and pin sizes align with the simulated gripper. Our gripper is mounted on a FANUC Robot for vertical movement.

### Observation signal and control policy: 
To enable real-world deployment, we distill the control policy learned in the simulator into a student policy that only receives RGB-D images, the extension values of each pin actuator, and the position of the gripper as observation signals. These signals are embedded and concatenated as the state feature and then fed to the student policy for grasping actions. In our real-world experiments, we confirmed that our gripper can achieve satisfactory grasping of multiple complex objects, such as Stanford Bunny, even only with a 3×3 pin resolution.


## Data Preparation
The challenge datasets: Chal-H dataset with 50 flat shapes and a Chal-T dataset consisting of 58 objects with inclined surfaces or tetrahedron-like shapes.
You can download the prepared dataset from [here](https://drive.google.com/drive/folders/1nx7LngqmtAvSGkX44yYfAoMbGQITP_i1?usp=drive_link).


## RL policy VS Extending all pins
|**Group**  | **RL policy** | **Extending all pins** |
|-----------|--------------|--------------|
| **#G1** | ![Image 1.1](assets/compare_with_all-extended/group-1/rl-1.gif) | ![Image 1.2](assets/compare_with_all-extended/group-1/all-1.gif) |
| **#G2** | ![Image 2.1](assets/compare_with_all-extended/group-2/rl-2.gif) | ![Image 2.2](assets/compare_with_all-extended/group-2/all-2.gif) |
| **#G3** | ![Image 3.1](assets/compare_with_all-extended/group-3/rl-3.gif) | ![Image 3.2](assets/compare_with_all-extended/group-3/all-3.gif) |
| **#G4** | ![Image 4.1](assets/compare_with_all-extended/group-4/rl-4.gif) | ![Image 4.2](assets/compare_with_all-extended/group-4/all-4.gif) |
| **#G5** | ![Image 5.1](assets/compare_with_all-extended/group-5/rl-5.gif) | ![Image 5.2](assets/compare_with_all-extended/group-5/all-5.gif) |
| **#G6** | ![Image 6.1](assets/compare_with_all-extended/group-6/rl-6.gif) | ![Image 6.2](assets/compare_with_all-extended/group-6/all-6.gif) |
| **#G7** | ![Image 7.1](assets/compare_with_all-extended/group-7/rl-7.gif) | ![Image 7.2](assets/compare_with_all-extended/group-7/all-7.gif) |
| **#G8** | ![Image 8.1](assets/compare_with_all-extended/group-8/rl-policy-8.gif) | ![Image 8.2](assets/compare_with_all-extended/group-8/all-8.gif) |
<!-- Table -->
Our pin-pression gripper offers object adaption and in-hand re-orientation through dynamically adjusting the extension and retraction of pins.

<!-- ## Demonstration of Grasp-then-Lift (GtL) motion
<div style="display: flex; justify-content: space-between;">
  <img src="GtL-mode-1.gif" alt="Image 1" width="48%">
  <img src="GtL-mode-2.gif" alt="Image 2" width="48%">
</div>

## Demonstration of Grasp-while-Lift (GwL) motion
<div style="display: flex; justify-content: space-between;">
  <img src="GwL-mode-1.gif" alt="Image 1" width="48%">
  <img src="GwL-mode-3.gif" alt="Image 2" width="48%">
</div> -->

#### Tips: If you find the gifs don't work, please try to refresh the page and wait for a while.
Code/data will be released soon.
