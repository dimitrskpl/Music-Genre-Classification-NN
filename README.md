# Music-Genre-Classification-NN
This project aims to classify 1-second music signals into four genres: Classical, Pop, Rock, and Blues. It utilizes two types of audio signal representations: Mel-Frequency Cepstral Coefficients (MFCCs) and Mel-Spectrograms.

## Dataset
The dataset consists of 1-second audio segments, each represented by 13 MFCC coefficients calculated over 50 ms, resulting in 20 feature vectors of dimension 13 for each music piece. For a static representation, the mean and standard deviation of each of the 13 coefficients across the 20 time moments were computed, leading to a 26-feature vector per music piece. Additionally, Mel-Spectrograms were used as a two-dimensional representation showing the time evolution of the spectrum of frequencies.

The dataset is divided into training (3200 samples), validation (800 samples), and test (1376 samples) sets for model training, hyperparameter tuning, and generalization ability assessment, respectively.

## Framework and Implementation
Implemented in PyTorch and executed on Google Colab, this project comprises several steps, focusing first on creating and training a Feedforward Neural Network and then developing a Convolutional Neural Network (CNN) using Mel-Spectrograms as inputs.

## Feedforward Neural Network
* **Data Loading**: MFCC data for train, validation, and test sets were loaded and preprocessed. Labels were converted from strings to integers with a corresponding mapping retained.
* **Neural Network Design**: A fully connected neural network was designed with four layers, following the dimensions 26 (input features), 128, 32, and 4 (output classes).
* **Training and Evaluation**: Training involved using stochastic gradient descent, a learning rate of 0.002, cross-entropy loss, and 30 epochs. Performance was evaluated using the test set.

## Convolutional Neural Network (CNN)
* **Data Loading for Mel-Spectrograms**: Similar data loading steps were followed for Mel-Spectrogram data.
* **CNN Architecture**: The network consists of four convolutional layers with increasing channels (1, 16, 32, 64, 128) and a sequence of five fully connected layers, integrating max pooling and padding for improved feature extraction.
* **Optimization and Performance Enhancement**: Different optimizers were tested for their impact on accuracy and F1 scores. Techniques such as batch normalization and regularization (weight decay, dropout) were employed to enhance model performance and manage overfitting.

To further improve model performance, reproducibility was ensured by setting seeds for all necessary libraries and algorithms. Various activation functions were experimented with, and learning rate schedulers were introduced to dynamically adjust the learning rate based on performance history. Additionally, the effects of different batch sizes and early stopping on training efficiency and model performance were explored.

## Results
In this project we successfully implemented and compared the performance of Feedforward and Convolutional Neural Networks for music genre classification. Through experimentation with network architecture, optimization algorithms, and performance enhancement techniques, insights into the complexity and challenges of audio signal classification were gained. 
