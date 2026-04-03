# Overview
The goal of this CNN model is to assist in medical image analysis by automatically identifying patterns in X-ray scans that indicate if a person has pneumonia or not.

#Dataset
The dataset consists of 5,863 chest X-ray images collected from pediatric patients (ages 1–5 years).

#Structure
Archive/
    train/
        NORMAL/
        PNEUMONIA/
    val/
        NORMAL/
        PNEUMONIA/
    test/
        NORMAL/
        PNEUMONIA/

Training Set: Used to train the model
Validation Set: Used to tune hyperparameters
Test Set: Used for final evaluation

#Methodology
Step 1: Data Acquisition

The dataset consisting of 5,863 chest X-ray images was obtained and organized into three subsets:

Training set
Validation set
Test set

Each subset contains two classes: NORMAL and PNEUMONIA.

Step 2: Data Preprocessing
All images were resized to 150 × 150 pixels to maintain consistency
Pixel values were normalized to the range [0, 1]

Data augmentation techniques were applied to the training set:
Random rotation
Zooming
Horizontal flipping

This step helps improve model generalization and reduces overfitting.

Step 3: Data Loading

The dataset was loaded using image data generators, which:

Read images directly from directories
Automatically assign labels based on folder names
Feed images to the model in batches

Step 4: Model Selection (Transfer Learning)

A pretrained MobileNetV2 model was selected as the base model:

Pretrained on the ImageNet dataset
Convolutional layers were initially frozen to retain learned features

Step 5: Model Customization

Custom layers were added on top of the base model:

Global Average Pooling layer
Fully connected Dense layer (ReLU activation)
Dropout layer (0.5) to reduce overfitting
Output layer with Sigmoid activation for binary classification

Step 6: Model Compilation

The model was compiled with:

Optimizer: Adam
Loss Function: Binary Crossentropy
Evaluation Metric: Accuracy

Step 7: Model Training
The model was trained using the training dataset
Validation data was used to monitor performance
Early stopping was applied to prevent overfitting
The best-performing model was saved using checkpointing

Step 8: Fine-Tuning

After initial training:

Some layers of the pretrained model were unfrozen
The model was retrained with a lower learning rate

This step improves feature learning and boosts accuracy.

Step 9: Model Evaluation

The trained model was evaluated on the test dataset using:

Accuracy
Loss
Confusion Matrix
Precision, Recall, and F1-score

Step 10: Model Interpretation

Grad-CAM was applied to:

Visualize important regions in X-ray images.
Understand how the model makes predictions.

#Findings
Test Accuracy: 80.77%
Training Performance: During the 15th epoch, the model reached a training accuracy of ~95.65%, though validation accuracy fluctuated, suggesting a need for further hyperparameter tuning to stabilize the learning process.

#Observations
The model performs well in distinguishing between Pneumonia and Normal cases.
Slight overfitting may occur due to dataset imbalance.
Transfer learning significantly improved performance compared to a basic CNN.

#Model Interpretability (Grad-CAM)

Grad-CAM was used to visualize which regions of the X-ray influenced the model's predictions.

Key Insight:
The model focuses on lung regions where abnormalities are present.
This improves transparency and trust in predictions.

#Limitations
Dataset is imbalanced.
Model may misclassify borderline cases.
Not suitable for real clinical diagnosis without validation.
