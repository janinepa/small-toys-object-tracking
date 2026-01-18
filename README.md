# Object Tracking with YOLOv8 and DeepSORT

This project implements a multiple object tracking (MOT) system designed to track small randomly moving toys. It combines the state-of-the-art object detection model **YOLOv8** with the **DeepSORT** tracking algorithm.

## Project Overview

The system pipeline performs detection and tracking on video footage. It was developed with a focus on comparing different tracking approaches and analyzing performance metrics.



https://github.com/user-attachments/assets/d265ddbc-763f-42e5-9d95-06a14407661e



## Methodology

### 1. Object Detection
- **Model**: [YOLOv8](https://github.com/ultralytics/ultralytics) (You Only Look Once v8)
- **Training**: The model was fine-tuned on a custom dataset of the toys using Google Colab.
- **Performance Metrics**:
  - **mAP@50**: 0.967
  - **mAP@50-95**: 0.483

### 2. Object Tracking
Two tracking methods were explored and compared:
**YOLOv8 + DeepSORT**: Integrates appearance information (using a Siamese network fine-tuned on a custom dataset of the toys) and motion information (Kalman filtering) for robust tracking.

<img width="321" height="196" alt="yolo_deepsort_example" src="https://github.com/user-attachments/assets/5491af74-b768-4df7-a775-4db9794282b3" />

## Experimental Results

### Framerate Analysis
We analyzed the impact of frame rate on tracking performance, testing ranges from **60 fps** down to **10 fps** (matching the training data characteristics).

### Performance Evaluation
TODO plot with framerate and number of id switches

## Project Structure
- `src/YOLO/`: Scripts for training the YOLOv8 model and converting data formats.
- `src/DeepSORT/`: Scripts for training the Siamese network for ReID and DeepSORT integration.
- `data/`: Contains training data, labels, and processed frames.

## Acknowledgements
This project is based on the [Multiple-Object-Tracking](https://github.com/ls-da3m0ns/Multiple-Object-Tracking.git) repository.
