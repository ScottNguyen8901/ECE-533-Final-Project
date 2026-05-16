# README.md

# ECE 533 Final Project

# Deep Learning-Based Lunar Crater Detection Using Modern Object Detection Architectures

## Scott Nguyen

University of New Mexico
ECE 533
Spring 2026

---

# Project Overview

This project investigates the use of modern deep learning object detection architectures for automated lunar crater detection using annotated planetary surface imagery.

Three object detection architectures were implemented and evaluated:

* YOLOv8 Nano
* Faster R-CNN
* RetinaNet

The project explores the tradeoffs between:

* crater localization accuracy
* computational efficiency
* training duration
* inference speed
* model complexity

for potential aerospace and planetary exploration applications.

---

# Objectives

The primary goals of this project were:

* develop a complete crater detection pipeline
* train multiple deep learning detection architectures
* compare localization quality and runtime performance
* generate quantitative evaluation plots
* visualize crater predictions
* analyze computational efficiency

---

# Dataset

Dataset source:

https://www.kaggle.com/datasets/lincolnzh/martianlunar-crater-detection-dataset

Dataset contents include:

* lunar imagery
* Martian imagery
* crater bounding box annotations
* training/validation/testing splits

---

# Repository Structure

```text
ECE-533-Final-Project/
├── data/
├── dataset_outputs/
├── comparison_outputs/
├── github/
├── images/
│   ├── ground_truth_examples/
│   ├── prediction_examples/
│   ├── accuracy_metrics_comparison.png
│   ├── avg_inference_time_per_image.png
│   ├── dataset_annotation_distribution.png
│   ├── dataset_image_distribution.png
│   ├── inference_time_comparison.png
│   └── training_time_comparison.png
├── logs/
├── weights/
├── main.ipynb
├── README.ipynb
├── report.ipynb
├── report.md
├── data.yaml
├── yolo26n.pt
└── yolov8n.pt
```

---

# Experimental Workflow

The overall crater detection workflow included:

1. dataset preparation
2. dataset inspection
3. annotation verification
4. ground truth visualization
5. model initialization
6. model training
7. prediction generation
8. quantitative evaluation
9. timing analysis
10. comparative analysis

---

# Models Evaluated

## YOLOv8 Nano

* single-stage detector
* lightweight architecture
* fast inference performance
* efficient GPU utilization

## Faster R-CNN

* two-stage region proposal detector
* strong localization quality
* higher computational overhead

## RetinaNet

* focal-loss-based single-stage detector
* balanced computational complexity
* stable training performance

---

# Results Summary

## YOLOv8

* strongest runtime-performance balance
* efficient inference speed
* strong crater localization capability

## Faster R-CNN

* strongest localization quality
* slower inference speed
* higher computational cost

## RetinaNet

* intermediate performance
* balanced runtime and localization quality

---

# Quantitative Evaluation

The project evaluated:

* mAP@0.50
* mAP@0.50:0.95
* recall
* training duration
* inference runtime
* computational timing metrics

Generated plots include:

* accuracy comparison
* training time comparison
* inference time comparison
* average inference time per image
* dataset distribution plots

---

# Google Colab Implementation

Google Drive Folder:

https://drive.google.com/drive/folders/18OnwDg1re-HRRi3NxY0z8zSU-ZSPvP3b

Includes:

* training pipelines
* dataset setup
* evaluation scripts
* prediction visualization generation
* saved outputs and logs
* comparison workflows

---

# Main Technologies

* Python
* PyTorch
* TorchVision
* Ultralytics YOLOv8
* Google Colab
* OpenCV
* Matplotlib

---

# References

1. Ultralytics YOLOv8
   https://github.com/ultralytics/ultralytics

2. TorchVision Object Detection Models
   https://pytorch.org/vision/stable/models.html

3. Lunar and Martian Crater Dataset
   https://www.kaggle.com/datasets/lincolnzh/martianlunar-crater-detection-dataset

4. PyTorch Documentation
   https://pytorch.org/

5. KaggleHub Documentation
   https://github.com/Kaggle/kagglehub
