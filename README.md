# Week 5 – Deep Learning Application in Data Science

## Handwritten Digit Classification Using CNN

## Project Overview
This project implements a **Convolutional Neural Network (CNN)** to classify handwritten digit images using Python, TensorFlow, and Keras. It was developed as part of Week 5 of a Data Science internship, focusing on the practical application of deep learning.

The model classifies grayscale images into ten classes, representing digits from **0 to 9**. The project is implemented in a Jupyter Notebook and covers data exploration, preprocessing, CNN architecture design, model training, evaluation, and error analysis.

## Objectives
- Understand the fundamentals of deep learning and CNNs.
- Load and explore a publicly available image dataset.
- Normalize image data and prepare it for neural network training.
- Design and train a CNN using TensorFlow/Keras.
- Evaluate performance using multiple classification metrics.
- Analyze misclassified images, training behavior, and model limitations.

## Dataset
**Dataset:** MNIST Handwritten Digits  
**Source:** TensorFlow/Keras built-in dataset loader

MNIST contains:
- 60,000 training images
- 10,000 test images
- Image dimensions: 28 × 28 pixels
- Image type: grayscale
- Classes: digits 0–9

The dataset is loaded directly in the notebook using `tf.keras.datasets.mnist.load_data()`. The first run may require an internet connection to download the dataset.

## Technologies Used
- Python
- Jupyter Notebook
- TensorFlow and Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

## CNN Architecture
The model uses the following layers:

1. Input layer: 28 × 28 × 1
2. Conv2D: 32 filters, 3 × 3 kernel, ReLU activation
3. MaxPooling2D: 2 × 2
4. Conv2D: 64 filters, 3 × 3 kernel, ReLU activation
5. MaxPooling2D: 2 × 2
6. Flatten layer
7. Dense layer: 128 units, ReLU activation
8. Dropout layer: 30%
9. Output layer: 10 units, Softmax activation

The convolutional layers learn image features, pooling reduces spatial dimensions, and the final layers classify the image into one of the ten digit classes.

## Data Preprocessing
- Convert image pixels to the `float32` data type.
- Normalize pixel values from 0–255 to 0–1 by dividing by 255.
- Add a channel dimension required by the convolutional layers.
- Use 10% of the training pool for validation.
- Keep the separate test set for final evaluation.

## Model Training
The notebook uses:
- **Optimizer:** Adam
- **Learning rate:** 0.001
- **Loss function:** Sparse categorical cross-entropy
- **Batch size:** 128
- **Maximum epochs:** 15
- **Validation split:** 10%
- **Callbacks:** Early stopping and model checkpointing
- **Random seed:** 42

Early stopping monitors validation loss and restores the best weights. A checkpoint saves the model with the best validation loss.

## Evaluation Metrics
The trained model is evaluated using:
- Test loss
- Accuracy
- Macro precision
- Macro recall
- Macro F1-score
- Classification report
- Confusion matrix
- Analysis of misclassified images

Training and validation loss/accuracy curves are also plotted to help assess learning behavior and possible overfitting.

**Note:** Actual evaluation values should be obtained by running the notebook. No performance figures are claimed in this README because they depend on the executed model.

### 4. Execute the notebook
Run all cells in order. The notebook downloads MNIST if needed, trains the CNN, evaluates the model, displays visualizations, and saves the generated outputs.

## Project Structure

```text
Week-5-Deep-Learning/
├── Week_5_Deep_Learning_MNIST_CNN.ipynb
├── Week_5_Deep_Learning_Report_Based_on_Notebook.docx
├── README.md
├── requirements.txt
├── outputs/
│   ├── evaluation_metrics.csv
│   ├── evaluation_metrics.json
│   ├── classification_report.txt
│   ├── test_predictions.csv
│   ├── best_mnist_cnn.keras
│   └── mnist_cnn_final.keras
└── visualizations/
    ├── training_history.png
    ├── confusion_matrix.png
    └── misclassified_examples.png
```

The `outputs/` and `visualizations/` files are generated when the notebook is executed. They may not exist in the repository before the first run.

## Challenges and Limitations
Potential challenges include package installation, dataset download issues, training time, overfitting, and confusion between visually similar digits.

The notebook uses normalization, dropout, validation monitoring, early stopping, and checkpointing to help address training-related issues.

MNIST contains small, centered, grayscale images. Its performance may not represent real-world handwriting with noise, rotation, varied backgrounds, or multiple characters.

## Future Improvements
- Compare the CNN with a fully connected neural-network baseline.
- Experiment with data augmentation.
- Tune the learning rate, dropout rate, and batch size.
- Analyze errors for individual digit classes.
- Test the model on a separate real-world handwriting dataset.

## Learning Outcomes
- Applied deep learning to a multi-class image-classification problem.
- Implemented a CNN using TensorFlow/Keras.
- Performed image preprocessing and normalization.
- Used validation monitoring and callbacks.
- Evaluated classification performance using multiple metrics.
- Conducted error analysis and documented model limitations.
