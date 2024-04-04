# MNIST-based Four-Digit Number Recognition Using CNN

## Introduction

This project focuses on developing a deep learning model capable of accurately recognizing and classifying sequences of four digits from images derived from the MNIST dataset. By concatenating individual MNIST digits into sequences, we've created a complex classification task designed to mimic real-world applications such as reading zip codes or account numbers. A Convolutional Neural Network (CNN), known for its proficiency in image recognition tasks, was employed. The performance of our model was evaluated using standard metrics.

## Dataset Description

The MNIST dataset comprises 70,000 images of handwritten digits, widely utilized in machine learning for training and testing. For our task, individual digit images were concatenated to form sequences representing four-digit numbers. This generated a custom dataset containing sequences that provide a unique challenge, extending the MNIST dataset's utility. Our custom dataset maintained the original single-channel grayscale format of MNIST images, and with 10,000 classes (each representing a number from 0 to 9999) and 10 training examples per class, it totals 100,000 training samples. The data was split into 80% training and 20% testing. Each label consisted of 40 units, with sets of 10 from these 40 units one-hot encoded to indicate the presence of a particular digit at a specific location.

## Model Architecture

The CNN model architecture includes two convolutional layers, capturing spatial hierarchies by learning the arrangement and patterns of the digits. Following these, two fully connected layers interpret the features, outputting 40 units that represent the probability distribution over the ten classes for each of the four digit positions.

## Training Process

A custom loss function was utilized, calculating the loss for each of the ten classes in all four digit positions independently before averaging them. Training was performed using the Adam optimizer with a learning rate of 0.001, over seven epochs. Separate subsets of the dataset were used for training and testing to evaluate the model's generalization capabilities.

## Evaluation Results

After training, the model achieved a test accuracy of 94.675%. This high accuracy level demonstrates the model's effectiveness in classifying sequences of four digits accurately, indicating a robust understanding of digit features and their sequences. The precision, recall, and F1-score across all classes were near 0.98. A plot of the loss vs. epoch for both training and testing is included below:

- Precision: 0.9865692785914962
- Recall: 0.9863949914411935
- F1 Score: 0.986416185893081
- Test Accuracy: 94.675%
- Hamming Loss: 0.0027175

## Possible Improvements

Enhancements could include using more varied examples, expanding beyond four digits, limited due to memory constraints. The current model, trained and evaluated on synthesized sequences from the MNIST dataset, would benefit from adaptation and testing on a dataset of real-world images, which would present digits under various conditions.

## Conclusion

The CNN model developed through this project shows exceptional performance in recognizing sequences of MNIST digits. The high precision, recall, and F1-score underline the model's effectiveness, with potential applications across various domains requiring automated number recognition. Future efforts may explore the model's robustness against noisy and distorted images and its scalability to sequences of variable lengths.
