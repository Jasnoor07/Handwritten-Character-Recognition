# Handwritten Character Recognition

## Project Overview

This project uses a Convolutional Neural Network (CNN) to recognize handwritten English characters from grayscale images.

The model is trained on the EMNIST Letters dataset, which contains handwritten examples of the 26 English alphabet characters (A–Z).

The project covers the complete machine learning workflow, including data preprocessing, CNN model development, training, evaluation, error analysis, and an interactive prediction demo.

## Dataset

**Dataset:** EMNIST Letters

- 26 classes: A–Z
- 124,800 training images
- 20,800 test images
- Image size: 28 × 28 pixels
- Grayscale images

The original EMNIST labels range from 1–26, so they were converted to 0–25 during preprocessing for compatibility with the CNN output classes.

## Workflow

1. Load the EMNIST Letters dataset
2. Inspect and visualize handwritten characters
3. Normalize pixel values
4. Convert labels to 0–25
5. Reshape images for CNN input
6. Split the training data into training and validation sets
7. Build a Convolutional Neural Network
8. Train the model using Early Stopping and learning-rate reduction
9. Evaluate the model on unseen test data
10. Analyze predictions using a confusion matrix and classification report
11. Examine incorrectly classified characters
12. Build an interactive Gradio prediction demo

## CNN Architecture

The model consists of:

- 3 convolutional layers
- Max-pooling layers
- A fully connected dense layer
- Dropout for regularization
- A 26-class softmax output layer

The model uses:

- Optimizer: Adam
- Loss function: Sparse Categorical Crossentropy
- Evaluation metric: Accuracy

## Model Performance

The best validation accuracy was:

**94.73%**

The final test-set performance was:

**Test Accuracy: 94.47%**

**Test Loss: 0.1761**

The classification report showed strong performance across most character classes.

Some of the more challenging characters for the model were:

- I — F1-score: 0.762
- L — F1-score: 0.763
- G — F1-score: 0.855
- Q — F1-score: 0.867

This analysis shows that visually similar or more ambiguous handwritten characters can be more difficult for the model to classify.

## Error Analysis

A confusion matrix and incorrectly classified test images were analyzed to understand where the model makes mistakes.

Instead of relying only on overall accuracy, the project examines performance for individual character classes using:

- Precision
- Recall
- F1-score
- Confusion matrix
- Incorrect prediction examples

## Interactive Demo

A Gradio-based interface allows users to upload a handwritten character and receive:

- Predicted letter
- Prediction confidence
- Top 3 predicted letters

The demo also includes preprocessing designed to handle uploaded images by:

- Converting them to grayscale
- Automatically adjusting image intensity
- Cropping the character
- Resizing it
- Centering it on a 28 × 28 canvas
- Normalizing pixel values

## Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- PIL
- Gradio
- Google Colab

## Project Files

```text
Handwritten-Character-Recognition/
│
├── Handwritten_Character_Recognition.ipynb
├── handwritten_character_cnn.keras
├── class_labels.json
├── README.md
└── requirements.txt