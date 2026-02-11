📌 Model / Approach Used
I implemented a Convolutional Neural Network (CNN) trained from scratch using TensorFlow/Keras to classify weather images into five categories:
Cloudy
Foggy
Rainy
Shine
Sunrise
The model architecture consisted of multiple convolutional blocks followed by fully connected layers:
Conv2D → BatchNormalization → MaxPooling
Repeated with increasing filters (32, 64, 128)
Flatten → Dense (256) → Dropout
Final Dense layer with Softmax activation (5 classes)
The model was trained using:
Categorical Cross-Entropy Loss
Adam Optimizer
EarlyStopping and ReduceLROnPlateau callbacks
🎯 Why I Chose This Model
The competition restricted the use of pretrained models, so I designed a custom CNN trained entirely on the provided dataset.
CNNs are well-suited for image classification tasks because they effectively capture:
Spatial patterns
Textures
Edges
High-level visual features
A from-scratch CNN ensures:
Full compliance with competition rules
No external data leakage
Transparent learning from only the given dataset
Batch Normalization and Dropout were added to:
Improve training stability
Reduce overfitting
Improve generalization performance
🛠️ Preprocessing \& Improvements
Several preprocessing and optimization steps were applied:
1️⃣ Data Preprocessing
Images resized to 224×224
Pixel values normalized to \[0,1]
Labels encoded into categorical format (one-hot encoding)
Proper train–validation split using stratification
2️⃣ Data Augmentation
To improve generalization and reduce overfitting:
Random horizontal flips
Random rotations
Random zoom
Random contrast adjustments
This helped the model perform better on unseen test data.
3️⃣ Training Optimizations
Used EarlyStopping to retain best validation weights
Applied ReduceLROnPlateau to lower learning rate when validation loss plateaued
Debugged test prediction alignment using test.csv to ensure correct ID–label mapping
📊 Final Performance
Validation Accuracy: ~82%
Kaggle Public Score: 0.523
The final model generalizes well without relying on pretrained networks.

