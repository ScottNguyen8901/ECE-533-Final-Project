# ECE 533 Final Project

# Deep Learning-Based Lunar Crater Detection Using Modern Object Detection Architectures

## Scott Nguyen

University of New Mexico
ECE 533
Spring 2026

---

# Abstract

This project investigates the use of modern deep learning object detection architectures for automated lunar crater detection using annotated planetary surface imagery. Automated crater detection is an important problem within planetary science, aerospace imaging, autonomous navigation, terrain analysis, and planetary surface mapping. Manual crater annotation is time-consuming and difficult to scale across large planetary datasets, motivating the need for efficient computer vision-based crater detection systems.

Three modern object detection architectures were implemented and evaluated:

* YOLOv8 Nano
* Faster R-CNN
* RetinaNet

The experimental workflow included:

* dataset preparation
* dataset inspection
* annotation verification
* ground truth visualization
* model training
* prediction visualization
* quantitative evaluation
* computational timing analysis

All experiments were implemented using Google Colab with NVIDIA Tesla T4 GPU acceleration. Comparative evaluation demonstrated that YOLOv8 achieved the strongest balance between crater localization quality, inference speed, and computational efficiency.

---

# Introduction

Planetary crater detection is an important problem in planetary science and aerospace imaging applications. Accurate crater localization supports planetary mapping, terrain hazard assessment, robotic navigation, and autonomous aerospace exploration systems.

Traditional crater detection methods often rely on manual inspection or classical image processing algorithms. These approaches become increasingly difficult when applied to large-scale planetary datasets due to computational complexity and annotation workload.

Recent advances in deep learning and computer vision have enabled modern object detection architectures to achieve strong performance across a wide variety of image recognition and localization tasks. This project investigates whether modern object detection architectures can effectively generalize to planetary crater detection using annotated lunar and Martian surface imagery.

This project additionally explores the tradeoffs between:

* crater localization accuracy
* computational efficiency
* training duration
* inference speed
* model complexity

for future aerospace and planetary analysis applications.

The major contributions of this project include:

* development of a complete crater detection pipeline
* implementation of multiple modern object detection architectures
* quantitative and qualitative model comparison
* computational performance analysis
* prediction visualization generation

---

# Background

Modern object detection architectures can generally be categorized into:

* single-stage detectors
* two-stage detectors

YOLOv8 is a lightweight single-stage object detector designed for fast inference and efficient runtime performance. YOLO architectures directly predict bounding boxes and object classifications from the input image in a single forward pass.

Faster R-CNN is a two-stage detector that first generates region proposals before performing object classification and localization refinement. Two-stage detectors often achieve strong localization capability but introduce higher computational overhead.

RetinaNet is a single-stage detector that introduces focal loss to improve learning stability under class imbalance conditions. Focal loss reduces the influence of easy negative examples during training and improves detection robustness for sparse object distributions.

These architectures were selected because they provide meaningful comparisons between:

* lightweight detectors
* region-based detectors
* focal-loss-based detectors

under consistent crater detection conditions.

---

# Dataset

Dataset source:

https://www.kaggle.com/datasets/lincolnzh/martianlunar-crater-detection-dataset

The dataset contains annotated lunar and Martian surface imagery formatted for YOLO-based object detection workflows.

The dataset includes:

* training images
* validation images
* testing images
* crater bounding box annotations

Each annotation file contains crater bounding box coordinates used for supervised object detection training.

The dataset was organized into standard supervised learning splits and used consistently across all evaluated architectures to ensure fair experimental comparison.

---

# Dataset Summary and Inspection

Prior to training, the dataset was inspected to verify:

* dataset split integrity
* image counts
* annotation counts
* crater bounding box formatting
* empty annotation files
* compatibility with object detection pipelines

Ground truth crater annotations were visualized to verify correct crater alignment across the dataset.

## Dataset Split Summary

| Dataset Split | Purpose                                             |
| ------------- | --------------------------------------------------- |
| Training      | Model parameter optimization                        |
| Validation    | Performance monitoring during training              |
| Testing       | Prediction visualization and qualitative evaluation |

---

## Image Distribution by Dataset Split

![Dataset Image Distribution](images/dataset_image_distribution.png)

Figure: Distribution of images across training, validation, and testing splits.

---

## Crater Annotation Distribution

![Dataset Annotation Distribution](images/dataset_annotation_distribution.png)

Figure: Distribution of crater annotations across dataset splits.

---

# Ground Truth Bounding Box Visualization

Ground truth crater annotations were visualized before training to verify annotation quality and crater alignment consistency.

These examples demonstrate the crater structures used during supervised object detection training.

## Ground Truth Example 1

![Ground Truth Example 1](images/ground_truth_examples/ground_truth_example_1.jpg)

---

## Ground Truth Example 2

![Ground Truth Example 2](images/ground_truth_examples/ground_truth_example_2.jpg)

---

## Ground Truth Example 3

![Ground Truth Example 3](images/ground_truth_examples/ground_truth_example_3.jpg)

---

# Methodology

Three object detection architectures were implemented and evaluated:

* YOLOv8 Nano
* Faster R-CNN
* RetinaNet

Each model was trained using:

* identical dataset splits
* GPU acceleration
* comparable training configurations
* identical crater annotations

The experimental workflow included:

1. dataset preparation
2. dataset inspection
3. annotation verification
4. ground truth visualization
5. model training
6. prediction generation
7. prediction visualization
8. quantitative evaluation
9. timing analysis
10. comparative analysis

All experiments were implemented using Google Colab with NVIDIA Tesla T4 GPU acceleration.

The project additionally logged:

* training duration
* inference timing
* model comparison metrics
* detection statistics
* prediction visualizations

throughout the experimental pipeline.

---

# High-Level Training Workflow

```text
Load crater dataset
Verify image and annotation integrity
Generate ground truth visualizations

For each detection model:
    Initialize pretrained detector
    Train model
    Save weights and logs
    Generate crater predictions
    Measure training and inference timing

Compare localization quality
Generate plots and evaluation summaries
```

---

# Model Configuration

| Model        | Type         | Main Purpose                   |
| ------------ | ------------ | ------------------------------ |
| YOLOv8 Nano  | Single-stage | Fast crater detection          |
| Faster R-CNN | Two-stage    | Strong localization quality    |
| RetinaNet    | Single-stage | Balanced detection performance |

---

# YOLOv8

YOLOv8 is a lightweight single-stage object detector optimized for:

* fast training
* fast inference
* efficient GPU utilization
* lightweight deployment

YOLOv8 Nano was selected because it provides a strong balance between crater detection capability and computational efficiency.

Training configuration:

* image size: 640 × 640
* batch size: 8
* epochs: 50
* pretrained weights initialization

---

# Faster R-CNN

Faster R-CNN is a two-stage object detection architecture that first generates region proposals before performing object classification and localization refinement.

Advantages:

* strong localization quality
* accurate region proposals
* high-quality detections

Limitations:

* slower inference
* higher computational overhead
* increased training complexity

Faster R-CNN served as a high-capacity localization baseline for crater detection comparison.

---

# RetinaNet

RetinaNet is a single-stage detector that introduces focal loss to improve learning under sparse object distributions and class imbalance conditions.

Advantages:

* stable training
* improved handling of sparse crater distributions
* balanced computational complexity

RetinaNet provided an intermediate comparison point between lightweight YOLO detectors and heavier region-based detectors.

---

# Results

The trained crater detection architectures were evaluated using:

* prediction visualization
* mAP-based accuracy metrics
* recall
* training duration
* inference speed
* computational efficiency

YOLOv8 demonstrated the strongest balance between:

* crater localization quality
* computational efficiency
* training speed
* inference speed

Faster R-CNN produced strong localization results but required significantly greater computational overhead.

RetinaNet demonstrated intermediate performance between YOLOv8 and Faster R-CNN.

---

# Prediction Bounding Box Comparison

The following examples compare crater predictions generated by each trained architecture.

## Ground Truth

![Ground Truth Example](images/ground_truth_examples/ground_truth_example_1.jpg)

---

## YOLOv8 Prediction

![YOLO Prediction](images/prediction_examples/yolo_010_png.rf.fcf5e274562ee69a325f9d7a0b30767f.jpg)

Observation:

* strong crater localization
* efficient runtime performance

---

## Faster R-CNN Prediction

![Faster R-CNN Prediction](images/prediction_examples/faster_rcnn_010_png.rf.fcf5e274562ee69a325f9d7a0b30767f.jpg)

Observation:

* strong localization quality
* slower inference performance

---

## RetinaNet Prediction

![RetinaNet Prediction](images/prediction_examples/retinanet_010_png.rf.fcf5e274562ee69a325f9d7a0b30767f.jpg)

Observation:

* balanced performance
* moderate computational complexity

---

# Quantitative Evaluation

The crater detection architectures were quantitatively evaluated using:

* mAP@0.50
* mAP@0.50:0.95
* recall
* training duration
* inference speed
* computational timing metrics

---

# Overall Model Comparison

| Model        | Speed  | Efficiency | Localization |
| ------------ | ------ | ---------- | ------------ |
| YOLOv8       | High   | High       | Strong       |
| Faster R-CNN | Low    | Low        | Very Strong  |
| RetinaNet    | Medium | Medium     | Strong       |

---

# Accuracy Comparison

![Accuracy Comparison](images/accuracy_metrics_comparison.png)

Figure: Accuracy metric comparison across evaluated crater detection architectures.

---

# Training Time Comparison

![Training Time Comparison](images/training_time_comparison.png)

Figure: Training duration comparison across evaluated models.

---

# Inference Time Comparison

![Inference Time Comparison](images/inference_time_comparison.png)

Figure: Inference runtime comparison across evaluated models.

---

# Average Inference Time Per Image

![Average Inference Time](images/avg_inference_time_per_image.png)

Figure: Average inference runtime per image across evaluated architectures.

---

# Subjective Results

| Model        | Subjective Observation                            |
| ------------ | ------------------------------------------------- |
| YOLOv8       | Best runtime-performance balance                  |
| Faster R-CNN | Strong localization but computationally expensive |
| RetinaNet    | Balanced performance across evaluation categories |

---

# Discussion

The experimental results demonstrated that modern deep learning object detection architectures can successfully perform automated lunar crater detection using annotated planetary surface imagery.

YOLOv8 provided the strongest overall balance between:

* crater localization quality
* computational efficiency
* training speed
* inference speed

The lightweight single-stage architecture achieved strong crater localization while maintaining efficient runtime performance.

Faster R-CNN demonstrated strong localization quality due to the region proposal stage; however, the additional complexity introduced significantly greater computational overhead.

RetinaNet demonstrated intermediate performance between YOLOv8 and Faster R-CNN. The focal loss mechanism improved stability under sparse crater distributions while maintaining moderate computational requirements.

The project additionally demonstrated the effectiveness of deep learning-based crater detection for:

* planetary surface analysis
* aerospace imaging
* autonomous terrain understanding
* crater localization tasks

Main limitations included:

* limited dataset size
* overlapping crater boundaries
* varying terrain illumination
* small crater localization difficulty

---

# Conclusion

This project successfully developed and evaluated multiple deep learning object detection pipelines for automated lunar crater detection.

The full workflow included:

* dataset preparation
* dataset verification
* ground truth visualization
* model training
* prediction visualization
* quantitative evaluation
* computational performance analysis

Among the evaluated architectures, YOLOv8 demonstrated the strongest balance between crater detection accuracy, computational efficiency, and inference speed.

The results demonstrate that modern deep learning object detection architectures provide an effective and scalable solution for automated planetary crater analysis and future aerospace imaging applications.

Future work may include:

* larger crater datasets
* higher-resolution imagery
* advanced augmentation methods
* segmentation-based crater detection
* embedded aerospace deployment optimization

---

# Google Colab Implementation

The complete Google Colab implementation includes:

* dataset preparation scripts
* environment setup instructions
* model training pipelines
* evaluation scripts
* prediction visualization generation
* computational timing analysis
* comparison workflows
* saved outputs and logs

Google Drive Folder:

https://drive.google.com/drive/folders/18OnwDg1re-HRRi3NxY0z8zSU-ZSPvP3b

---

# Repository Structure

```text
ECE-533-Final-Project/
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
│   ├── accuracy_evaluation_results.csv
│   ├── dataset_summary.csv
│   ├── inference_comparison_log.csv
│   ├── model_comparison_summary.csv
│   └── training_logs/
└── report.md
```

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
