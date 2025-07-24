
# Sign Language Detector

This is a real-time American Sign Language (ASL) alphabet detection system. It uses a webcam to recognize hand gestures and display the corresponding alphabet. The system uses MediaPipe for hand tracking and PyTorch for model training and inference made by SOHAM ROY

## Features

- Detects all 26 ASL alphabet hand gestures (A–Z)
- Real-time video feed with letter prediction overlay
- Uses MediaPipe for landmark extraction
- Custom neural network built with PyTorch
- Full pipeline from data collection to model training and real-time testing

## Technologies Used

- Python
- OpenCV
- MediaPipe
- PyTorch
- Pandas, NumPy
- Scikit-learn, Matplotlib

## Project Structure

```
Sign-Language-Detector/
│
├── collect_data.py        # Collects hand landmark data for each alphabet
├── train_model.py         # Trains a neural network on the collected data
├── model.pth              # Trained model file
├── inference.py           # Runs real-time prediction using webcam
├── utils/                 # Utility functions and custom dataset class
│   └── dataset.py
├── requirements.txt       # Required Python packages
└── README.md              # Project overview
```

## How It Works

1. **Data Collection**:  
   The script `collect_data.py` captures webcam input and stores MediaPipe hand landmark coordinates for each letter in CSV format.

2. **Model Training**:  
   The script `train_model.py` reads the collected data, trains a classification model using PyTorch, and saves the trained model as `model.pth`.

3. **Real-Time Inference**:  
   The script `inference.py` opens the webcam, detects hand landmarks using MediaPipe, and predicts the hand sign using the trained model.

## How to Run

### Step 1: Clone the Repository

```bash
git clone https://github.com/soham-tries/Sign-Language-Detector.git
cd Sign-Language-Detector
```

### Step 2: Install Requirements

```bash
pip install -r requirements.txt
```

### Step 3: Collect Training Data

```bash
python collect_data.py
```

Follow the on-screen instructions to record hand gestures for each letter.

### Step 4: Train the Model

```bash
python train_model.py
```

### Step 5: Run the Real-Time Detector

```bash
python inference.py
```

A window will open showing the webcam feed with the predicted alphabet displayed on the screen.

## Learning Outcomes

- Understanding of computer vision and hand gesture recognition
- Practical use of MediaPipe for extracting hand landmarks
- Training classification models using PyTorch
- Working with real-time webcam input using OpenCV
- Building a full machine learning pipeline from data to deployment

## Notes

- Ensure your hand is visible and centered in the webcam frame for accurate detection.
- Good lighting improves performance.
- You may need to adjust camera index (e.g., `cv2.VideoCapture(0)`) if you're using an external webcam.


