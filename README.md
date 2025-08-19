# Handwritten-Digit-Recognition-Deep-Learning-
I worked on the Kaggle Digit Recognizer dataset (MNIST in CSV format) to build a robust classifier using ResNet152 with transfer learning.

Data Overview:
-Training set: 42,000 images (28x28 pixels flattened into 784 features)
-Test set: 28,000 images
-10 classes (digits 0–9)
-Class distribution (balanced but slightly uneven):
      - Digit 1: 4684 samples
      - Digit 7: 4401 samples
      - Digit 3: 4351 samples
      - Digit 5: 3795 samples (lowest)

Approach:
- Preprocessing: reshaped to 28x28, converted grayscale to RGB, resized to 224x224, normalized
- Base model: ResNet152 pretrained on ImageNet
- Two training stages:
       - Feature extraction with frozen layers
       - Fine-tuning last 30 layers for task-specific learning
- Regularization: dropout layers, early stopping, learning rate scheduling
- Class imbalance addressed with computed class weights

Results:
- Training accuracy: 98.7%
- Validation accuracy: 98.2%
- Predictions generated for the 28,000 test images
- Submission file submission.csv prepared with final labels

Key Takeaways:
- Transfer learning delivers high performance even on grayscale digit datasets
- Fine-tuning improves adaptation to dataset-specific features
- Class weights help mitigate bias toward more frequent digits

This project shows how modern architectures like ResNet can outperform traditional CNNs on classic problems.
