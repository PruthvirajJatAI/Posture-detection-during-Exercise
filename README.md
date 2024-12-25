# Posture-detection-during-Exercise
This project focuses on detecting and providing feedback for correct and incorrect postures during gym exercises, specifically for movements like bicep curls. The system uses a pre-trained deep learning model to classify postures based on joint angles and alignment, providing real-time feedback through a webcam interface.

# Features
- Posture Detection: Identifies whether the posture during exercises (e.g., bicep curl) is correct or incorrect based on joint angles and alignment.
- Real-Time Feedback: Provides visual and textual feedback through webcam output, indicating whether the posture is correct or needs improvement.
- Repetition Tracking: Counts and displays the number of repetitions performed and the average speed of repetitions per minute.
- Session Logging: Saves session data (reps, duration, start time) to a text file for future reference.
- Model Training: A neural network is trained using labeled datasets for correct and incorrect postures.

# Files Overview

- Cell 1
 -- Imports libraries: cv2, mediapipe, numpy, tensorflow, and others.
 -- Pose Calculation: Functions to calculate angles between body joints and extract features (e.g., arm angles, shoulder alignment) from annotated images.
 -- Data Extraction: Extracts features and labels from correct and incorrect posture images for training a neural network model.

- Cell 2
 -- Model Evaluation: Evaluates the trained model's performance using the test set. Outputs the classification report, confusion matrix, and accuracy metrics.

- Cell 3
 -- Posture Detection in Real-Time: Captures video using a webcam, processes each frame for posture detection, and provides real-time feedback on the subject’s posture.
 -- Repetition Counting: Tracks repetitions and calculates the average speed of reps per minute.
 -- Session Logging: Saves the session data (reps, duration) to a text file when the session ends.

# Prerequisites
 -Python: Version 3.6 or later
 -Libraries: Install the required Python libraries  :opencv-python mediapipe numpy tensorflow scikit-learn

# Data Preparation

The project assumes the existence of two datasets:

 - Correct Postures: Images where the subject is performing exercises correctly.
 - Incorrect Postures: Images where the subject is performing exercises incorrectly.
These datasets should be organized in directories as follows:

markdown
correct_dataset/
    image1.jpg
    image2.jpg
    ...
incorrect_dataset/
    image1.jpg
    image2.jpg
    ...
Make sure the paths to the datasets are updated in the code:

correct_dataset_path = 'path/to/correct_dataset'
incorrect_dataset_path = 'path/to/incorrect_dataset'

# Model Training
1. The model uses a neural network architecture with:
 -- An input layer accepting features such as joint angles.
 -- Two hidden layers with ReLU activation.
 -- An output layer using sigmoid activation for binary classification (correct/incorrect posture).

2 .The model is trained using TensorFlow/Keras and is saved to a .h5 file after training. The trained model is then used for real-time posture feedback.

# Running Real-Time Posture Detection
1 .Run the script that loads the trained model and starts webcam capture.
2 .The system will process each frame, detecting body landmarks and evaluating the posture.
3 .Real-time feedback (e.g., "Good posture!" or "Incorrect posture!") will be shown on the webcam feed.
4 .The number of repetitions and session duration will be displayed on the screen.
5 .Press 'q' to exit the program.

# Saving Session Data
 - Session data, including the number of repetitions and the session duration, is saved to a text file (session_data.txt) when the session ends.

Example format of the session data:
Repetitions: 15
Duration: 00:15:30
Start Time: 14:30
