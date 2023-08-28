# Spleen Segmentation using Monai and Pytorch


## Introduction

Semantic segmentation is a critical task in medical image analysis, allowing for the accurate delineation of anatomical structures in images. The U-Net architecture has proven effective for such tasks due to its ability to capture spatial information and produce accurate segmentations.

This project involves preparing the data, training the U-Net model, and visualizing the results with the Monai framework for spleen segmentation task.


## Monai Framework

Monai is a set of open-source, freely available collaborative frameworks built for accelerating research and clinical collaboration in Medical Imaging. 

https://monai.io/

## Usage

### Data Preparation

#### Creating DICOM Groups

- The first step is to create DICOM groups from DICOM files.
- Organize DICOM files into groups based on common attributes.
- Ensure each group contains DICOM files related to the same patient or study.

#### Conversion to NIFTI

- Using the DICOM groups, convert each group of DICOM files into NIFTI format.
- Perform this conversion using tools or libraries that support DICOM to NIFTI conversion.
- Obtain NIFTI images and labels from the converted DICOM groups.

 Apply data augmentation and preprocessing transforms using `train_transforms` and `val_transforms`.

  
### Model Training

- Define the U-Net model architecture with the desired parameters (e.g., input channels, output channels, number of residual units).
- Set up the loss function (Dice Loss), optimizer (Adam), and evaluation metric (Dice Metric).
- Train the model using a DataLoader for both training and validation data.
- Monitor training progress, track loss, and metric values.
- Save checkpoints of the model's state, optimizer state, and training progress.

### Visualization

- Load the trained U-Net model from a saved checkpoint.
- Perform sliding window inference on validation data to obtain segmentation outputs.
- Visualize input images, ground truth labels, and model predictions for selected slices.
- Observe how well the model is performing on the segmentation task.

## Results

The results of the model training and evaluation, including loss curves, Dice metric values, and visualization of segmentation outputs, are saved in the specified directory.


![Learning curve](https://github.com/bbabina/Spleen-Segmentation-using-Monai-and-Pytorch/assets/74191100/91176326-9d05-45cb-9cc1-35b52b50d7fa)


