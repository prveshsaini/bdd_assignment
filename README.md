# BDD100K Interview Assignment

## Overview
This repo contains my work on the BDD100K dataset for Siemens interview assignment.

Tasks covered:
- Dataset exploration & visualization
- Baseline YOLOv8 object detection
- Model comparison
- Analysis-driven improvements
- Fine-tuning pipeline

## Dataset
Download the dataset from the google link shared and put it in the dataset/ directory
Directory Structure Should look like this:
dataset/
├── bdd100k_images_100k/
└── bdd100k_labels_release/
notebooks/
├── 01_data_analysis.ipynb
├── 02_baseline_model.ipynb
├── 03_comparision.ipynb
└── 04_fine_tuning.ipynb
requirements.txt

## Environment Setup
pip install -r requirements.txt

## Guides for the notebooks
01_data_analysis.ipynb
- Load annotations for train and val
- Visualize the structure of annotations
- Converted annotations to data frame with each object as new entry
- Print infomation based on this data frame like instances per class, per scene type, area distribution of the boxes etc.
- Converts the annotation type to yolo, which can be used later on for evaluation and training yolo models
- While creating yaml file relative weight are also mentioned based on the class representation in the dataset

02_baseline_model.ipynb
- baseline YOLO 8n model is used
- Module to compare yolo prediction to the ground truth 
- YOLO 8n model is evaluated on the val set and metrics are printed
- YOLO 8m model is also evaluated on the val set and metrics were printed
- Observations based on  the results is listed

03_comparision.ipynb
- Tested Faster R-CNN and SSD model for object detection task
- Results for all 3 (YOLO, Faster R-CNN, SSD) mdoels are visualized and compared to Ground Truth for a random image side by side.
- Faster R-CNN, SSD model were then evaluated on Val set to get class wise as well as all metrics

04_fine_tuning.ipynb
- Discussed different ways of improving the model performance
- Code for fine tuing the yolo model on train dataset
- Printing the metrics for fine tuned model
