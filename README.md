# Sign Language Detection

This project is a real-time Sign Language Detection system that uses computer vision and machine learning to recognize hand gestures representing letters of the alphabet. It leverages MediaPipe for hand landmark detection and a Random Forest Classifier for gesture recognition.

## Features

- **Real-time Detection:** Detects and classifies sign language gestures via webcam.
- **Custom Dataset Support:** Includes tools to process image datasets (like the ASL dataset) for training.
- **Fine-tuning:** Allows users to record their own hand gestures to fine-tune the model for better accuracy in specific environments.
- **Model Training:** Automated scripts to train and retrain the machine learning model.

## Project Structure

- **`model_training.py`**: Main script to process the initial dataset and train the base model.
- **`predicting_letters.py`**: Runs the real-time inference using the webcam to predict letters.
- **`fine_turning_debuging.py`**: A utility to collect personal data and retrain the model to improve accuracy for specific users or lighting conditions.
- **`servies/`**: Contains the core logic modules:
  - `image_process_1.py`: Processes raw images into landmarks for training.
  - `train_model_2.py`: Trains the Random Forest model on the processed data.
  - `inference_3.py`: Handles the webcam feed and real-time prediction.
  - `collect_finetune_data.py`: Captures new training samples from the webcam.
  - `retrain_mixed.py`: Merges original and personal data to retrain the model.
- **`model/`**: Stores the trained model (`model.p`) and processed data (`data.pickle`, `my_real_data.pickle`).
- **`asl_dataset/`**: Directory to place your ASL image dataset (e.g., from Kaggle).

## Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd Sign_language_detection
    ```

2.  **Install dependencies:**
    It is recommended to use a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```

## Usage

### 1. Initial Setup & Training

If you are starting from scratch with an image dataset (e.g., Kaggle ASL dataset):

1.  Place your dataset in the `asl_dataset` folder. The structure should be `asl_dataset/A/image1.jpg`, `asl_dataset/B/image2.jpg`, etc.
2.  Run the training script:
    ```bash
    python model_training.py
    ```
    This will process the images and train the initial model.

### 2. Real-time Prediction

To start detecting sign language using your webcam:

```bash
python predicting_letters.py
```
Press `Q` to quit the application.

### 3. Fine-tuning (Optional)

If the model struggles with certain letters or your specific environment:

1.  Run the fine-tuning script:
    ```bash
    python fine_turning_debuging.py
    ```
2.  Follow the on-screen prompts to record samples for the problematic letter.
3.  The script will automatically retrain the model with the new data mixed in.

## Requirements

- Python 3.x
- OpenCV
- MediaPipe
- Scikit-learn
- Numpy
- Matplotlib

(See `requirements.txt` for full list and versions)
