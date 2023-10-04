# Detection-JKT48-member-face

This repository contain my personal project documentation about JKT48 members face recognition with YOLOv8 Object Detection. The general purpose of this project is to introduce JKT48 members to the public who can be known through facial recognition. For now, the accuracy with three members are 94,5%. The members that will be detected are limited. Any request member or discussion is open, just contact me through my email on the profile (^^)

### List of member:
1. Fiony
2. Ashel
3. Shani

### How to use the model?

1. Install requirements on `Google Colab`
   ```bash
   !pip install -q ultralytics "ray[tune]"
   !pip uninstall -q -y albumentations
   ```
2. Import `library`
   ```bash
   from roboflow import Roboflow
   from ultralytics import YOLO
   from ray import tune
   import cv2
   import numpy as np
   from statistics import mean
   import matplotlib.pyplot as plt
   from PIL import Image
   from google.colab.patches import cv2_imshow
   ```
3. Download model on `Model` folder with name `detectmemberbest.pt`
4. Open `Google Colab`, connect runtime and upload the model
5. Copy this code to predict
   ```bash
   PATH="path/to/directoryimagetest"
   !yolo predict task=detect model=/path/to/model/detectmemberbest.pt imgsz=640 conf=0.5 max_det=1 source={PATH}
   ```
