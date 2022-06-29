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

Configurations for running the simulator are set in the Unity Editor. A good working knowledge of Unity is helpful for getting the simulator up and running. For those who are entirely new to Unity I recommend completing the [introductory course by Brackeys](https://www.youtube.com/watch?v=IlKaB1etrik)

For those who are more familiar with Unity or willing to dive in head first,  I provide a high-level overview of setting up and using the simulator/Unity. See the video below.

### Data Generation

#### 1. Load the "SegImage" Scene

To load the "SegImage" Scene, click on the project tab by default found in the lower left-hand corner. Under the assets folder, click Scenes. Clicking scenes should display all of the scenes for the project. Double click on the one that says seg image to open it. 

![image](https://user-images.githubusercontent.com/24756984/176236106-f784864a-8771-45ae-b1fa-ae5a97105fb6.png)

#### 2. Set the view to see the main and segmentation cameras

To view the main camera, click the game tab at the top left. Under the game tab, click the dropdown next to the aspect ratio ie "free aspect", "16:9", etc. Select if available select 480x480 or add it by choosing the plus at the very bottom and then select 480x480.

![image](https://user-images.githubusercontent.com/24756984/176240789-82930d4c-451a-4d48-b49e-c14ed8c62d0a.png)

To view the segmentation camera, right-click on the "game tab" and select "add tab", and under "add tab", select "game". Note that if you can not find a tab, you can typically add it by right-clicking any existing tab and selecting "add tab" from the dropdown menu.

![image](https://user-images.githubusercontent.com/24756984/176242006-762fe9a1-ebc3-4473-ab0a-4f25dde6c262.png)

To view both cameras simultaneously, first drag and drop the newly created (currently selected) game tab to the right. The editor should show a split-screen. Next, repeat the above step to change the camera resolution to 480x480.  Under the game tab, click the dropdown next to the aspect ratio ie "free aspect", "16:9", etc. Select if available select 480x480 or add it by choosing the plus at the very bottom and then select 480x480.

![image](https://user-images.githubusercontent.com/24756984/176242882-1f25a296-d0fb-4c07-ae9f-fd432bb1efe6.png)

Finally in the rightmost game tab click the dropdown next to display 1 and select display 2. This should beging rendering both displays.

![image](https://user-images.githubusercontent.com/24756984/176243261-29f6931f-0939-432a-88c4-49334c58bd5f.png)

#### 4. Set paths and run config

To run the data generator, first navigate to the autoCap object under the hierarchy menu.

![image](https://user-images.githubusercontent.com/24756984/176243847-ba58672f-5c29-4927-b2e9-96993be30164.png)

Under the inspector for this object found on the far right, select "Is train mode" and deselect all others. Under "data folder," provide a path to a folder to hold the data. The data folder MUST contain two sub folders, x and y.

![image](https://user-images.githubusercontent.com/24756984/176244940-0e7029aa-dd16-4a0a-a839-57b6b3632285.png)

At the top of the editor, click the play button. This should start running the data collection process. Data pairs will be saved at the specified location under the folders x and y.

![image](https://user-images.githubusercontent.com/24756984/176246209-4408c514-dc8e-4d62-942d-1d321840f6e5.png)


Note the simulator is flexible and with some tweaks to the code and other parameters, things like the distance between pictures, flood locations, water color, altitude, etc can be changed [See the video] or the [AutoCapture script](https://github.com/memeQueenPaulaDeen/UnityFloodSimulator/blob/master/Assets/AutoCapture.cs)  

### Navigation simulation

#### Creating the navigation environment
