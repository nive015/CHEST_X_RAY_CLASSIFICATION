# CHEST_X_RAY_CLASSIFICATION USING DenseNet121
**Overview**
This project aims to classify chest X-ray images into two categories: chest (likely representing relevant X-ray scans) and non-chest (irrelevant or other types of images). The workflow involves:

Preprocessing raw image data

Data augmentation

Building and training a CNN model using DenseNet121

Evaluating the trained model


**Data Preprocessing**
Grayscale Conversion: Images are read in grayscale.

Normalization: Pixel values are scaled between 0–255.

Resizing: Images are resized to 224x224 pixels to fit DenseNet121 input requirements.

RGB Conversion: Grayscale images are converted to 3-channel RGB for compatibility with pre-trained models.

Saving: The processed images are saved to new directories.

**Data Augmentation**
To increase the robustness of the model, the following augmentation techniques are applied:

Rotation

Zoom

Shear

Flipping

Width and height shift

The ImageDataGenerator from TensorFlow is used for real-time augmentation.

**Model Architecture**
Base Model: DenseNet121 pre-trained on ImageNet (excluding top layer).

Top Layers:

Global Average Pooling

Dense (fully connected) layer

Dropout for regularization

Output layer with sigmoid activation (binary classification)

Optimizer: Adam

Loss Function: Binary Crossentropy

Metrics: Accuracy

**Training**
Training/Validation Split: Automatically handled by ImageDataGenerator.flow_from_directory().

Epochs: Defined in the notebook

Batch Size: Typically set to 32


**Evaluation**
Confusion Matrix: Used to visualize performance.

The user has to upload the test images and an excel file will be generated with


**Dependencies**
TensorFlow and Keras

OpenCV (cv2)

PIL

NumPy, Pandas

Matplotlib

Tkinter (for GUI)

pydicom (not actively used in the displayed code but imported)

tqdm (for progress bars)
