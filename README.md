# Bone Segmentation in Low-Field Knee MRI Using a 3D Convolutional Neural Network 
## Introduction

Bone segmentation in magnetic resonance imaging (MRI) is crucial for clinical and research applications, including diagnosis, surgical planning, and treatment monitoring. However, it remains challenging due to anatomical variability and complex bone morphology. Manual segmentation is time-consuming and operator-dependent, fostering interest in automated methods. This study presents a deep learning approach utilizing a 3D convolutional neural network (CNN) to segment the femur, tibia, and patella from low-field MRI scans. Low-field MRI offers advantages in cost, patient comfort, and accessibility but presents challenges related to lower signal quality. Our method achieved a Dice Similarity Coefficient (DSC) of 0.9838, Intersection over Union (IoU) of 0.9682, and Average Hausdorff Distance (AHD) of 0.0223, with an inference time of approximately 3.96 seconds per volume on GPU. Although post-processing had minimal impact on metrics, it significantly enhanced the visual smoothness of bone surfaces, crucial for clinical use. Final segmentations enabled the creation of clean, 3D-printable bone models, beneficial for preoperative planning. These results demonstrate that the model achieves accurate segmentation with a high degree of overlap compared to manually segmented reference data. This accuracy is a result of meticulous fine-tuning of the network, along with the application of advanced data augmentation and post-processing techniques.

## How to use
The project consists of two Jupyter Notebooks:

- `3d-unet.ipynb`: Loads the dataset, applies pre-processing, defines and builds the 3D U-Net model, trains the model on the training set, and performs inference on the test set.
- `post-processing.ipynb`: Loads the predictions from the test set, applies post-processing techniques, and evaluates the segmentation results using voxel-level metrics.


## Setup
These notebooks are intended to be run on [Kaggle](https://www.kaggle.com/code), where most common libraries (e.g. NumPy, Pandas, PyTorch, scikit-learn, etc.) are already available.

However, you need to manually install the `patchify` library.  
At the beginning of the notebook, make sure to include:

```python
!pip install patchify
```

## Dataset
The dataset is available at https://zenodo.org/records/10534328
