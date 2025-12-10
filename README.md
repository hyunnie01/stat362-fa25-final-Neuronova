# stat362-fa25-final-Neuronova

Project title: Neuronvoa (STAT 362 Fall 2025)

Author: Yi Hyun Kwon

Problem description and dataset

The goal of this project is to develop a high-performing model capable of accurately classifying brain tumor MRI images. More specifically, the task involves a two-step classification problem: first, determining whether an MRI scan indicates the presence of a tumor; and second, if a tumor is present, identifying its specific type. For this study, I use a publicly available MRI brain tumor dataset from Kaggle, which contains 7,023 images distributed across four classes: glioma, meningioma, pituitary, and no tumor. The dataset is already partitioned into a training set of 5,712 images and a test set of 1,311 images.

High-level description of your model

The baseline model is a convolutional neural network (CNN) with four convolutional blocks followed by a fully connected layer to classify brain MRI images. The structure consists of 4 blocks with progressively increasing filters (32 → 64 → 128 → 128), each followed by max-pooling. Finally, there is a fully connected dense layer of 512 units and a final output layer (softmax and sigmoid activation for two models accordingly). Due to restricted GPU memory and long run time, most of the designs were kept as default. Adam was used as the optimizer with a batch size of 32 and a 15 epochs. The learning rate was kept as default. Images were normalized by scaling the pixel values from [0, 255] → [0, 1]. Data agumentation involved 1) Random rotations (up to 40°), 2) Width shifts (±20%), 3) Height shifts (±20%), 4) Shear transformations, 5) Zoom adjustments, 6) Horizontal flips.

Summary of key results

The tumor type classification model achieved an accuracy of 86.4% and the tumor identification model acheived a recall of 99.5%. Improvements of the model accuracy was limited due to limited GPU memory and long training time, but training and validation accuracy graph indicates ample potential for improvements.

How to run the code
1. Install dependencies with Poetry ----- command: poetry install
2. Visit https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset to download the image data. * Make sure to change the folder path accordingly to match your path when importing
3. Run the code
