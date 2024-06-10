# Tarzan: The wonder Driver
## Object-Lane_Detection

### Introduction
The purpose of this project is to make a model which can detect objects while a person is driving and make a box around them with the label of the object. These objects include vehicles, persons, traffic signals etc.

### Methodology
#### Catering to YOLO Input Requirements
- Yolov5 takes an image and a text file as label for that image as input for training. A specific directory structure must also be maintained for error free training.
root:> [images:>train,val],[labels:>train,val]. For this task os and shutil modules have been extensively used for files writing and copying.
- The Detect Function
  - This function does all the work on the test video file.
  - First we run the detect.py file of yolo. It takes img size(img), pre learned weights yolov5s.pt, conf , and path to test file.
  - The detect.py file breaks the video into it’s constituent frames which are then analysed individually by the model.
  - Bounding boxes are drawn objects and the video is again merged to generate the output video.
  - The output of this  code is then passed to our lane detection algorithm 

#### Lane Detection 
- A pretrained FCNN model trained on a large dataset was used. The model has been trained on around 21000 images obtained from 12 videos.
- The input to the lane detection code is the output of the object detection model. Hence after the objects have been detected in the input video, it’s forwarded to the lane detection code.

