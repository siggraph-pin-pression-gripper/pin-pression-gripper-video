# Project of Designing Pin-pression Gripper and Learning its Dexterous Grasping with Online In-hand Adjustment

#### Tips: If you find the GIFs don't work, please try to refresh the page and wait for a while.

## Introduction
In this project, we introduce a novel pin-pression gripper that features adjusting its finger shape to conform to the target object.
We carefully devise a reinforcement learning algorithm to handle the online grasping skills.


## Real-world demo
We have developed a real-world implementation of our pin-pression gripper with electrically controlled pins.

![](assets/Real-world/sim2real.png)
We fabricate a real pin-pression gripper with electrically controlled pins (a), equipped with an in-hand RGB-D camera for capturing observations. The gripper approaches the target object from the top, forms a basic closure against the object with pin movements, and achieves the final grasp (b).

### Physical experiment video (Loading the GIF here may take a few minutes and thanks for your patience)
<table>
  <tr>
    <th style="text-align: center;">Ours</th>
    <th style="text-align: center;">Passive Grasping</th>
  </tr>
  <tr>
    <td style="text-align: center;"><img src="assets/Real-world/gif_result/object1/01-ours.gif" alt="Image 1.1" width="99%"></td>
    <td style="text-align: center;"><img src="assets/Real-world/gif_result/object1/01-passive.gif" alt="Image 1.2" width="99%"></td>
  </tr>
  <tr>
    <td style="text-align: center;"><img src="assets/Real-world/gif_result/object2/02-ours.gif" alt="Image 2.1" width="99%"></td>
    <td style="text-align: center;"><img src="assets/Real-world/gif_result/object2/02-passive.gif" alt="Image 2.2" width="99%"></td>
  </tr>
  <tr>
    <td style="text-align: center;"><img src="assets/Real-world/gif_result/object3/03-ours.gif" alt="Image 3.1" width="99%"></td>
    <td style="text-align: center;"><img src="assets/Real-world/gif_result/object3/03-passive.gif" alt="Image 3.2" width="99%"></td>
  </tr>
  <tr>
    <th colspan="2" style="text-align: center;">Ours</th>
  </tr>
  <tr>
    <td style="text-align: center;"><img src="assets/Real-world/gif_result/object4/04-ours.gif" alt="Image 4" width="99%"></td>
    <td style="text-align: center;"><img src="assets/Real-world/gif_result/object5/05-ours.gif" alt="Image 5" width="99%"></td>
  </tr>
</table>

The corresponding MP4 format demos have also been uploaded in the path: 'assets/Real-world/video_result'.

#### Hardware configuration
We utilize  electrical actuators as pins of our pin-pression gripper. Each pin is connected to a separate relay for independent control, allowing for precise extension and retraction. The physical gripper is designed with a 4x4 resolution, weighing 2.3kg. Both gripper size and pin sizes align with the simulated gripper. Our gripper is mounted on a FANUC Robot for vertical movement.  

#### Observation signal and control policy
To enable real-world deployment, we use a two-stage teacher-student training paradigm. We distill the control policy learned in the simulator into a student policy that only receives RGB-D images and the extension values of each pin actuator as observation signals. These signals are embedded and concatenated as the state feature and then fed to the student policy for grasping actions. In our real-world experiments, we confirmed that our gripper can achieve satisfactory grasping of multiple objects.

## Data preparation
We collect several challenging objects to further demonstrate the necessity of our on-line grasping approach. 
The challenge datasets: Chal-H dataset with 50 flat shapes and Chal-T dataset consisting of 58 objects with inclined surfaces or tetrahedron-like shapes. You can download the prepared dataset from [here](https://drive.google.com/drive/folders/1nx7LngqmtAvSGkX44yYfAoMbGQITP_i1?usp=drive_link). The training and testing data used in our experiments can be found [here](https://drive.google.com/drive/folders/1gUtK2BN2nmtp3zWg8up30pIlELLl_lgJ?usp=drive_link).

## Supplementary Material

For more experimental details and additional results, please refer to the supplementary material:

👉 [Download Supplementary Material (PDF)](./assets/supplementary/supp.pdf)

## Animation result 
Using our pin-pression gripper, we found that passive grasping method which heuristically extends all pins struggles, particularly with objects with inclined surfaces. It is necessary to adopt reinforcement learning (RL) policies for the pin-pression gripper to enable adaptive in-hand object adjustments, thereby achieving better force closure and efficient grasping. 
#### RL policy vs. Passive grasping (Loading the GIF may take a while and thanks for your patience)
|**Object**  | **RL policy** | **Passive grasping** |
|-----------|--------------|--------------|
| **#O1** | ![Image 1.1](assets/compare_with_all-extended/group-1/rl-1.gif) | ![Image 1.2](assets/compare_with_all-extended/group-1/all-1.gif) |
| **#O2** | ![Image 2.1](assets/compare_with_all-extended/group-2/rl-2.gif) | ![Image 2.2](assets/compare_with_all-extended/group-2/all-2.gif) |
| **#O3** | ![Image 3.1](assets/compare_with_all-extended/group-3/rl-3.gif) | ![Image 3.2](assets/compare_with_all-extended/group-3/all-3.gif) |
| **#O4** | ![Image 4.1](assets/compare_with_all-extended/group-4/rl-4.gif) | ![Image 4.2](assets/compare_with_all-extended/group-4/all-4.gif) |
| **#O5** | ![Image 5.1](assets/compare_with_all-extended/group-5/rl-5.gif) | ![Image 5.2](assets/compare_with_all-extended/group-5/all-5.gif) |
| **#O6** | ![Image 6.1](assets/compare_with_all-extended/group-6/rl-6.gif) | ![Image 6.2](assets/compare_with_all-extended/group-6/all-6.gif) |
<!-- | **#O7** | ![Image 7.1](assets/compare_with_all-extended/group-7/rl-7.gif) | ![Image 7.2](assets/compare_with_all-extended/group-7/all-7.gif) | -->
<!-- | **#O8** | ![Image 8.1](assets/compare_with_all-extended/group-8/rl-policy-8.gif) | ![Image 8.2](assets/compare_with_all-extended/group-8/all-8.gif) | -->
<!-- Table -->

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

#### Code/data will be released soon.
