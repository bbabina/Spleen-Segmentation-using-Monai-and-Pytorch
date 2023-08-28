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

To train the U-Net model for semantic segmentation, follow these steps:

1. **Model Architecture Definition**: Define the U-Net model architecture according to your requirements. Specify parameters such as the number of input channels, output channels, and the number of residual units for the encoder and decoder.

2. **Loss Function and Metrics**: Set up the loss function for training the model. For semantic segmentation, the Dice Loss is commonly used as it measures the overlap between predicted and ground truth segmentations. Additionally, select an evaluation metric such as the Dice Metric to assess the performance of the model during training and validation.

3. **Optimizer Configuration**: Choose an optimizer for updating the model's parameters. The Adam optimizer is a popular choice due to its adaptive learning rate. Configure the optimizer with an appropriate learning rate.

4. **DataLoader Setup**: Prepare training and validation datasets using DataLoader objects. Ensure that the data is properly formatted and transformed for input to the model. The DataLoader provides efficient batching and shuffling of data during training.

5. **Training Loop**: Implement the training loop, iterating over batches of data. Within each iteration, perform the following steps:
   - Zero the gradients of the model's parameters using `optimizer.zero_grad()`.
   - Forward pass the input through the model to obtain predictions.
   - Compute the loss between the predictions and the ground truth using the defined loss function.
   - Backpropagate the gradients and update the model's parameters using `loss.backward()` and `optimizer.step()`.
   - Track the running average of the loss for the current epoch.

6. **Validation and Progress Tracking**: At regular intervals, evaluate the model on the validation dataset using the configured evaluation metric. Monitor the model's performance, both in terms of loss and the chosen metric, throughout training.


![Learning curve](https://github.com/bbabina/Spleen-Segmentation-using-Monai-and-Pytorch/assets/74191100/91176326-9d05-45cb-9cc1-35b52b50d7fa)


### Visualization

- Load the trained U-Net model from a saved checkpoint.
- Perform sliding window inference on validation data to obtain segmentation outputs.
- Visualize input images, ground truth labels, and model predictions for selected slices.
- Observe how well the model is performing on the segmentation task.

## Results

The results of the model training and evaluation, including loss curves, Dice metric values, and visualization of segmentation outputs, are saved in the specified directory.

![output](https://github.com/bbabina/Spleen-Segmentation-using-Monai-and-Pytorch/assets/74191100/6f39ea1b-a740-48bc-96e9-f4e4644e8931)





