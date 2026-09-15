# Handwritten Character Recognition

## Project Overview

This project uses image processing and deep learning techniques to recognize handwritten English characters.

A Convolutional Neural Network (CNN) is trained on the EMNIST Letters dataset to classify handwritten characters into 26 classes (A–Z).

The project includes data preprocessing, CNN model training, performance evaluation, confusion matrix analysis, error analysis, and an interactive Gradio demonstration.

## Dataset

The project uses the **EMNIST Letters** dataset.

- 26 handwritten character classes (A–Z)
- 124,800 training images
- 20,800 test images
- Image size: 28 × 28 pixels
- Grayscale images

The dataset was downloaded directly from the EMNIST dataset repository hosted on Hugging Face.

## Workflow

1. Download the EMNIST Letters dataset
2. Load and preprocess the images
3. Normalize pixel values
4. Convert labels into zero-based class indices
5. Split the training data into training and validation sets
6. Visualize sample images and class distribution
7. Build a Convolutional Neural Network
8. Train the model using validation data
9. Evaluate the model on the held-out test set
10. Generate a confusion matrix and classification report
11. Perform error analysis
12. Save the trained model
13. Test the model using an interactive Gradio interface

## CNN Architecture

The model consists of:

- Conv2D layer with 32 filters
- MaxPooling2D
- Conv2D layer with 64 filters
- MaxPooling2D
- Conv2D layer with 128 filters
- Flatten layer
- Dense layer with 128 neurons
- Dropout layer (0.4)
- Output layer with 26 neurons and Softmax activation

The model was compiled using the Adam optimizer and sparse categorical cross-entropy loss.

## Model Performance

The CNN achieved the following performance on the held-out EMNIST test set:

- **Test Accuracy:** 94.47%
- **Test Loss:** 0.1761
- **Macro Average F1-Score:** approximately 0.945
- **Weighted Average F1-Score:** approximately 0.945

The best validation accuracy during training was approximately **94.73%**.

## Error Analysis

The classification report and confusion matrix were used to identify classes that were more difficult for the model to distinguish.

Some of the comparatively harder characters included:

- G
- Q
- I
- L

These errors can occur because some handwritten characters have similar shapes or because writing styles vary between samples.

## Interactive Demo

The trained CNN model is also integrated with a Gradio interface for interactive testing.

Users can upload a handwritten character and receive the model's top predictions along with confidence scores.

The interactive demo provides a practical way to test the trained model on new inputs. However, performance on user-provided handwriting may vary because real-world handwriting can differ in writing style, scale, thickness, background, and image quality from the EMNIST dataset used during training.

Therefore, the reported test accuracy of **94.47%** is based on the held-out EMNIST test set and should not be interpreted as guaranteed accuracy on arbitrary real-world handwriting.

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Pillow
- Gradio
- Google Colab

## Repository Files

- `Handwritten_Character_Recognition.ipynb` — Complete project notebook
- `handwritten_character_cnn.keras` — Trained CNN model
- `class_labels.json` — Character class labels
- `README.md` — Project documentation
- `requirements.txt` — Required Python libraries

## Limitations

- The model was trained specifically on the EMNIST Letters dataset.
- The dataset contains isolated handwritten characters rather than complete words or sentences.
- Real-world handwriting styles may differ from the training data.
- Some visually similar characters may be harder for the model to distinguish.
- The current system is intended for educational and demonstration purposes.

## Future Improvements

- Train with a more diverse handwriting dataset.
- Add data augmentation for different writing styles and image conditions.
- Extend the system to recognize complete words and sentences.
- Improve preprocessing for photographs and scanned documents.
- Deploy the model as a web or mobile application.

## Conclusion

This project demonstrates the use of image preprocessing and Convolutional Neural Networks for handwritten character recognition.

The trained CNN achieved **94.47% accuracy on the held-out EMNIST test set**, demonstrating strong performance on the dataset.

The project also includes error analysis and an interactive Gradio demonstration, providing both quantitative evaluation and practical model interaction.
