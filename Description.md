Introduction:
Hand gesture recognition is an essential technology in Human-Computer Interaction (HCI), enabling users to control and interact with computers using hand movements. This project focuses on implementing a Convolutional Neural Network (CNN) to recognize static hand gestures from images. It also supports real-time gesture prediction through a webcam.

About Dataset:
The LeapGestRecog dataset is used, containing thousands of grayscale images of various hand gestures. Each class of gesture is stored in a separate folder.

Key preprocessing steps:
All images are resized to 64×64 pixels for consistency and faster processing.

The dataset is split into:
* Training Set (80%) – for learning model parameters.
* Validation Set (20%) – for evaluating model performance during training.

Image Processing:
Before training, each image goes through the following preprocessing steps:
* Resizing to 64×64 resolution.
* Normalization – pixel values are scaled between 0 and 1.
* Label extraction is automated using the directory structure via image_dataset_from_directory.

CNN Model Architecture:
The model is built using TensorFlow and Keras, with the following layers:
* Convolutional Layers – extract features from input images.
* Max Pooling Layers – reduce feature map size while retaining key information.
* Flatten Layer – converts 2D feature maps to 1D.
* Dense Layer – learns higher-level representations.
* Dropout Layer – prevents overfitting by randomly dropping neurons.
* Output Layer – a softmax layer that outputs class probabilities.
The model is compiled with the Adam optimizer and trained using sparse categorical crossentropy, which is ideal for multi-class problems with integer labels.

Model Evaluation:
After training, the model is evaluated using:
* Classification Report – provides precision, recall, and F1-score for each class.
* Confusion Matrix – visualizes true vs. predicted labels to identify strengths and weaknesses.
These tools help in analyzing the model’s performance and identifying areas for improvement.

Real-Time Gesture Prediction:
Using OpenCV, the system supports real-time recognition:
* Captures video from the webcam.
* Preprocesses each frame in real-time.
* Predicts gesture class using the trained CNN.
* Displays the predicted gesture name and confidence score on the video feed.
* Optionally overlays a reference gesture image.
* The system can be exited by pressing the ‘q’ key.

Applications:
This gesture recognition system can be applied in many areas:
* Touchless control systems
* Sign language interpretation
* AR/VR interfaces
* Gaming and entertainment
* Robotics and industrial automation
