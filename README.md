# Pedestrican-Tracker
Pedestrian Tracking scenario: it reads frames from an input video sequence, detects pedestrians in the frames, and builds trajectories of movement of the pedestrians in a frame-by-frame manner, using Intel OpenVino

## Pre Requisites
1. Intel OpenVino
2. Python
3. Cmake
4. Visual Studio

### Installation Instructions

Kindly refer to https://docs.openvinotoolkit.org/latest/openvino_docs_install_guides_installing_openvino_windows.html

### Getting Started

1. Navigate to <Installation Directory>\Intel\openvino_2021.4.582\bin using command prompt (CMD) and initialise the environment variables.
2. Enter the following in the CMD
  
   cd C:\Program Files (x86)\Intel\openvino_2021.4.582\inference_engine\demos
  
   and run build_demos_msvc.bat file.

3. cd <Installation Directory>\Intel\openvino_2021.4.582\deployment_tools\tools\model_downloader
4. Download the two models using the following commands
  
    python downloader.py --name person-detection-retail-0013 -o (specify the output path.)
  
    python downloader.py --name person-reidentification-retail-0288 -o (specify the output path.)
    
  
5. cd C:\Users\<username>\Documents\Intel\OpenVINO\omz_demos_build\intel64\Release
  
  Copy the downloaded models from FP 32 into the release folder.
  
  Copy the test video file into the release folder as well
  
  ![image](https://user-images.githubusercontent.com/80956623/133468509-86a83611-af1b-4ff2-87e6-fffb4e08d752.png)
  
  ![image](https://user-images.githubusercontent.com/80956623/133469182-62b000ed-9eba-4cb3-a311-468f74001326.png)


6. Finally enter the following command
  
  pedestrian_tracker_demo.exe -i sample.mp4 -m_det person-detection-retail-0013.xml -m_reid person-reidentification-retail-0288.xml
  
## Output sample

  ![image](https://user-images.githubusercontent.com/80956623/133469070-7883454d-a41a-477b-87c0-33be89713ee0.png)

### Note
1. Text mentioned in angular brackets <> needs to be replaced with relevant path specific to the particular user.
2. Use
  
    pedestrian_tracker_demoo.exe -h
  
    for usage instructions.
  
2. If CMD is closed the varibles are lost and have setupvars.bat is needed to ran again.
3. Preferably run the Command Prompt as admin.
4. Use 
  
    pedestrian_tracker_demo.exe -i 0 -m_det person-detection-retail-0013.xml -m_reid person-reidentification-retail-0288.xml
  
    to use webcam feed as the input for this program.
