# UnityFloodSimulator

## Overview

The Unity Flood simulator is a tool to simulate realistic floods anywhere on earth! The simulator has two primary functions. The first is to support training neural networks for image segmentation by generating an unlimited number of image mask pairs. The second is providing a sandbox environment where a UGV and UAV can solve a navigation problem cooperatively.

The flood simulator is one piece of a larger project targeted at solving navigation problems in the wake of natural disasters. The code repository for the navigation solution can be found [here](https://github.com/memeQueenPaulaDeen/DeepLearnFinalProject). A dataset consisting of 40,000 image mask pairs using the simulator can be found [here](https://www.kaggle.com/datasets/samiwood/synthetic-flood-imagery-for-image-segmentation). An example of the navigation solution is shown below.

![image](https://user-images.githubusercontent.com/24756984/175994893-31e3c78b-fc1b-4519-bbd4-c84b60b06d71.png)(https://www.youtube.com/watch?v=Id2LECr51fw)

## Installation

#### 1. Install Unity hub. 

Unity hub can be downloaded folloing this [link](https://unity3d.com/get-unity/download). Note Unity Hub version 2.4.3 was used for this project, the version of Unity Hub probably does not matter, however the version of Unity used is important.

#### 2. Install Unity version 2020.3.4f1. 

Unity version version 2020.3.4f1 can be downloaded by clicking the installs tab in Unity Hub. 

![image](https://user-images.githubusercontent.com/24756984/175999554-0661fb0b-f68d-4734-bcc4-0b1b2b052388.png)

Then click the add button and find version 2020.3.4f1 in the popup window. Alternativly the locate button can be used to install unity versions found on the web, try googling "Unity version 2020.3.4f1" or check the [download archive](https://unity3d.com/get-unity/download/archive) if you can't find it.

![image](https://user-images.githubusercontent.com/24756984/175999827-a757e3a3-c483-442c-81e9-76d0e493ea2b.png)

#### 3. Clone this repository.

#### 4. Add this repository as a project in Unity Hub. 

In the projects tab click the add button.

![image](https://user-images.githubusercontent.com/24756984/176002388-134f0eb9-8b55-4d89-834e-be631ceedb91.png)

Navigate to the cloned UnityFloodSimulator folder and click the select folder button.

![image](https://user-images.githubusercontent.com/24756984/176003723-6cdbd9bf-0b74-4a7e-b81a-4117568f27c2.png)

##### 5. Launch the Unity Flood Simulator

At this point, the simulator should be added to the Unity Hub projects. Double click to launch it. Ensure the proper unity version is selected before launching the editor. The version can be changed by clicking on the version number. When first launched the simulator should look similar to the screenshot below. 

![image](https://user-images.githubusercontent.com/24756984/176007077-08448e70-a673-4faa-9cfb-d0676bcef2fd.png)



### system requirements

Note that the simulator and navigation solutions have only been tested on a Windows 10 desktop. 16 GB ram, 3080 Nvidia GPU, intel Core i7 10700k. A computer running windows with similar or better specs is likely required.

## Using the simulator

### Data Generation


### Navigation simulation

#### Creating the navigation environment
