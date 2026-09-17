````markdown
# CNN-Based EMG Gesture Recognition and Real-Time Control System

A machine-learning-based gesture recognition system that uses surface Electromyography (sEMG) signals to recognize hand gestures and provide the foundation for real-time gesture-based control of industrial Human-Machine Interface (HMI) systems.

## Overview

This project explores the use of EMG signals for recognizing hand gestures without relying on conventional physical input devices.

The system processes EMG signals through a preprocessing pipeline and uses a **1D Convolutional Neural Network (CNN)** to classify gestures.

The initial prototype was developed using the **Ninapro dataset** and supports classification across **10 gesture classes**.

The project is being developed as part of an academic collaboration with **Schneider Electric**, with the goal of building a gesture-based control interface for industrial HMI systems.

## Key Features

- EMG-based gesture recognition
- 1D CNN-based classification
- 10 gesture classes
- Ninapro dataset
- EMG signal preprocessing
- Sliding-window segmentation
- RMS smoothing
- Real-time inference pipeline
- LOSO cross-validation
- Foundation for industrial HMI gesture control

## System Pipeline

```text
             EMG Signal
                  |
                  v
        Signal Preprocessing
                  |
        +---------+---------+
        |         |         |
        v         v         v
   Rectification  RMS    Filtering/
                 Smoothing  Processing
        |         |         |
        +---------+---------+
                  |
                  v
        Sliding-Window
          Segmentation
                  |
                  v
             1D CNN
                  |
                  v
        Gesture Classification
                  |
                  v
       Real-Time Inference
                  |
                  v
       HMI Control Interface
````

## Dataset

The initial model was developed using the **Ninapro EMG dataset**.

The prototype performs classification across:

* 10 gesture classes
* Surface EMG signals
* Multiple subjects

The dataset is used for model training, validation, and evaluation.

## Preprocessing

Raw EMG signals require preprocessing before being passed to the neural network.

The current preprocessing pipeline includes:

### 1. Rectification

The EMG signal is rectified to work with the magnitude of muscle activation.

### 2. RMS Smoothing

Root Mean Square (RMS) smoothing is applied to obtain a smoother representation of muscle activity.

### 3. Sliding-Window Segmentation

The continuous EMG signal is divided into smaller windows.

These windows are then used as individual model inputs for gesture classification.

```text
Raw EMG
   |
   v
Rectification
   |
   v
RMS Smoothing
   |
   v
Sliding Window
   |
   v
CNN Input
```

## Model

### 1D Convolutional Neural Network

The project uses a **1D CNN** for classifying EMG signals.

1D convolution is suitable for the sequential structure of EMG data because the model can learn local patterns from the signal over time.

The general workflow is:

```text
EMG Window
    |
    v
1D Convolution
    |
    v
Feature Extraction
    |
    v
Pooling / Feature Reduction
    |
    v
Flattening
    |
    v
Dense Layers
    |
    v
10-Class Output
```

## Model Performance

The initial working prototype achieved:

**87% within-subject accuracy**

using **Leave-One-Session-Out (LOSO) cross-validation**.

### Evaluation

| Metric     | Result                     |
| ---------- | -------------------------- |
| Model      | 1D CNN                     |
| Dataset    | Ninapro                    |
| Classes    | 10                         |
| Evaluation | LOSO Cross-Validation      |
| Accuracy   | 87%                        |
| Task       | EMG Gesture Classification |

## Real-Time Inference

A real-time inference pipeline has been developed to process incoming EMG data and classify gestures continuously.

The inference pipeline follows:

```text
Live EMG Input
      |
      v
Preprocessing
      |
      v
Window Generation
      |
      v
1D CNN
      |
      v
Predicted Gesture
      |
      v
Control Action
```

The predicted gesture can then be mapped to a corresponding control action for an HMI system.

## Industrial HMI Application

The intended application is gesture-based interaction with industrial Human-Machine Interface systems.

Instead of requiring a conventional physical input method, recognized EMG gestures can be mapped to predefined HMI actions.

For example:

```text
EMG Gesture
     |
     v
CNN Classification
     |
     v
Recognized Gesture
     |
     v
HMI Command
```

The current implementation forms the foundation for the industrial HMI control system under development.

## Technology Stack

| Category          | Technology                     |
| ----------------- | ------------------------------ |
| Programming       | Python                         |
| Deep Learning     | TensorFlow / Keras             |
| Model             | 1D CNN                         |
| Signal Type       | Surface EMG                    |
| Dataset           | Ninapro                        |
| Signal Processing | Rectification, RMS Smoothing   |
| Segmentation      | Sliding Window                 |
| Evaluation        | LOSO Cross-Validation          |
| Application       | Industrial HMI Gesture Control |

## Project Structure

```text
EMG-Based-Gesture-Recognition-and-Real-Time-Control-System/
│
├── data/
│
├── preprocessing/
│
├── models/
│
├── notebooks/
│
├── inference/
│
├── results/
│
├── requirements.txt
│
└── README.md
```

> Update this structure to match the actual repository folders if they differ.

## Installation

Clone the repository:

```bash
git clone https://github.com/JATIN17082005/EMG-Based-Gesture-Recognition-and-Real-Time-Control-System.git
```

Move into the project directory:

```bash
cd EMG-Based-Gesture-Recognition-and-Real-Time-Control-System
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the environment on Windows:

```bash
venv\Scripts\activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Running the Project

The project consists of separate stages for preprocessing, model training, evaluation, and inference.

A typical workflow is:

```text
1. Prepare Ninapro Dataset
        ↓
2. Preprocess EMG Signals
        ↓
3. Segment Signals
        ↓
4. Train 1D CNN
        ↓
5. Evaluate Using LOSO
        ↓
6. Run Real-Time Inference
```

Refer to the notebooks/scripts in the repository for the corresponding implementation.

## Results

The initial prototype demonstrates that a 1D CNN can classify the selected EMG gesture classes with **87% within-subject accuracy** under LOSO cross-validation.

The preprocessing and inference pipeline provides the foundation for converting continuous EMG activity into real-time gesture predictions.

## Current Development

The project is being developed toward integration with an industrial HMI environment.

Current work focuses on:

* Improving the real-time inference pipeline
* Gesture-to-command mapping
* Hardware integration
* HMI control
* Further model evaluation

## Contributors

**Jatin Poripireddi**

Vellore Institute of Technology

GitHub:
https://github.com/JATIN17082005

LinkedIn:
https://www.linkedin.com/in/jatin-poripireddi-5ba70128a

## Acknowledgements

This project uses the **Ninapro** dataset for EMG-based gesture recognition research and development.

The project is being developed through an academic collaboration with **Schneider Electric**.

## License

This project is intended for academic and research purposes.

```

For GitHub, I'd recommend keeping the README **this technical rather than making it overly long**. Your resume already establishes the Schneider Electric connection and the 87% result; the README should mainly let someone understand **what the model does, how the EMG data flows through it, and how to reproduce it**.
```
