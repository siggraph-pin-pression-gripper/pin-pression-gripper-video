# pin-pression-gripper-video
Project of Pin-pression Grippers for Dexterous Grasping with Dynamic In-hand Adjustment

## Demonstration of real-world experiments
We develope a physical prototype of the pin-pression gripper. 

![](assets/Real-world/Sim2real.png)
![](assets/Real-world/real-world-1.gif)


Physical configuration: We use pneumatic cylinders as the pin actuators and an RGB-D image as the observation signal. The pneumatic pressure is controlled via solenoid valves and relays, enabling the extension and retraction of the pins. The gripper, with 3×3 pins and one RGB-D camera, weighs 2.3 kg and is mounted on a FANUC robot for vertical movement. 

Visual perception processing: We retrained the network using PyBullet with the RGB-D image as observation. RGB and depth images are processed separately by two pre-trained Inception-v3 networks, and their features are concatenated into a 4096-dimensional vector as the state representation. Both the actor and critic network are implemented as Multi-Layer Perceptron structures. The entire network is trained end-to-end, allowing the pre-trained networks to be fine-tuned to better fit our task. 

Further work: We aim for our gripper to achieve good performance on as many shapes as possible while minimizing the number of pin actuators used. In our real-world experiments, we confirmed that a 3×3 resolution can achieve satisfactory grasping of multiple given objects, such as the Stanford bunny. As we elaborated in the future work, we will further implement a practical 4*4 version and consider applying the imitation learning and domain randomization to achieve the sim-to-real transfer like the gap between the designed state representation and RGB-D image.


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

## Demonstration of Grasp-then-Lift (GtL) motion
<div style="display: flex; justify-content: space-between;">
  <img src="GtL-mode-1.gif" alt="Image 1" width="48%">
  <img src="GtL-mode-2.gif" alt="Image 2" width="48%">
</div>

## Demonstration of Grasp-while-Lift (GwL) motion
<div style="display: flex; justify-content: space-between;">
  <img src="GwL-mode-1.gif" alt="Image 1" width="48%">
  <img src="GwL-mode-3.gif" alt="Image 2" width="48%">
</div>




#### Tips: If you find the gifs don't work, please try to refresh the page and wait for a while.
Code/data will be released soon.
