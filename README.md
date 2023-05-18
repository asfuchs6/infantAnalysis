## Installation

### 

### Requirements

- Python 3.9
- macOS 
- iCatcher+: 0.0.11
- Torch: >=1.11.0
- Torchvision: >=0.12
- dlib: 19.24.1
- face_recognition: 1.3.0
- jupyter notebook

## Table of Contents
#### input
Put any video you are interested in running Infant Analysis on in the input folder.
Sample videos in the input folder:
- 3sec.mp4
- infant.mov
- infant2.mov

#### emotion_detection
This directory contains three subdirectories: emotion_detector_models, output, src.
- /emotion_detector_models: a pre-trained model that is used to determine the emotion classification for a given image.
- /output: contains a folder and a csv file for each video classified. The folder contains every time frame as a .jpg 
and the csv records the emotion predicted at each timeframe.
- /src: 
    - facial_detection_recog_emotion.ipynb: use your input video and classify the emotion at any time frame. 
    The data will be smoothed and out the output will be the folder and csv file found in /output. 
    The name of the folder and csv is the name of the input video without the video format.
    - EmotionDetector_v2.ipynb: used to train the emotion detection model. 
    - requirements.txt: necessary to download all of the libraries to  run this code.

Open Jupyter notebook and navigate to /src/facial_detection_recog_emotion.ipynb. 
Before running all cells, go to the last cell and fill in the variables "video_name, full_video_name".
Then run all cells to populate your output folder. Once you have gathered all of the emotion detection 
files you need, go to the icatcher_plus directory.

#### icatcher
This directory contains a lisence and requirements/setup file (pyproject.toml), a test directory, icatcher_video_dataset, src, and output directory. 
 - /tests: A test directory to make sure the right dependencies are installed.
 - /src/icatcher: 
    - cli.py: the main file to implement looking direction analysis.
    - draw.py: functions for adding text, arrows and bounding boxes.
    - parsers.py and options.py: parse the command line arguments.
    - video.py: process the video.
    - models: identify faces (face recognition) and classify the looking direction.
 - /output: The output videos from Infant Analysis now with a bounding box, arrow, and text added to the original videos.
 A txt file with all of the information (timeframe, looking direction, confidence of looking direction, emotion)
 - /icatcher_video_dataset: a subset of videos from the iCatcher dataset for training (https://osf.io/5u9df/)
 
 Navigate to /icatcher_plus/src/icatcher and run: 
 ```
 python src/icatcher/cli.py ../input/nameOfVideo --output_video_path output --output_annotation output
```
 Once the video is done processing you can check the output folder. 
 If you rerun the same command the previous video and txt will be rewritten unless they are renamed.
 If you choose to not run the emotion detection then just run icatcher_plus without processing the video first in jupyter notebook.  

## More information
iCatcher+: https://github.com/erelyotam/icatcher_plus
face_and_emotion_detection: https://github.com/priya-dwivedi/face_and_emotion_detection

