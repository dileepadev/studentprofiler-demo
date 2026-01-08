# Student Profiler Demo Web App

This is a demo web application for the Student Profiler system, designed to analyze student behavior and learning styles using machine learning models to generate personalized education plans.

## Features

- **Teacher & Student Profiling**: Select and view profiles for teachers and students via a web interface.
- **Facial Emotion Recognition (FER)**: Analyzes video input to detect various emotional states (Angry, Disgusted, Fearful, Happy, Neutral, Sad, Surprised) using a deep learning model.
- **Sentiment Analysis**: Analyzes textual data to determine sentiment polarity.
- **Personalized Plan Generation**: Generates activity plans based on VARK (Visual, Aural, Read/Write, Kinesthetic) learning styles and student performance levels.

## Tech Stack

- **Backend**: Python, Flask
- **Database**: Firebase Firestore
- **Machine Learning**:
  - TensorFlow / Keras (Emotion Recognition)
  - OpenCV (Image Processing)
  - Scikit-learn / Joblib (Sentiment Analysis)
  - NumPy, Pandas
- **Frontend**: HTML5, CSS3 (Bootstrap), JavaScript

## Algorithms & Models

### 1. Facial Emotion Recognition (FER)

- **Model Architecture**: A **Convolutional Neural Network (CNN)** built with Keras/TensorFlow.
  - **Structure**: Sequential model with multiple `Conv2D` layers (filters: 32, 64, 128), `MaxPooling2D` layers (2x2), and `Dropout` layers (0.25, 0.5) to prevent overfitting.
  - **Dense Layers**: A fully connected hidden layer with 1024 units (ReLU) and an output layer with 7 units (Softmax).
- **Face Detection**: Utilizes **OpenCV's Haar Cascade Classifier** (`haarcascade_frontalface_default.xml`) to detect and extract faces from video frames before passing them to the CNN.
- **Input**: 48x48 grayscale face images.
- **Output**: Probability distribution across 7 emotions: *Angry, Disgusted, Fearful, Happy, Neutral, Sad, Surprised*.

### 2. Sentiment Analysis

- **Model Type**: Classical Machine Learning Classifier (Scikit-learn).
- **Process**:
  - **Vectorization**: Uses a pre-trained **Vectorizer** (loaded via Joblib) to transform raw text into numerical features.
  - **Prediction**: A trained classifier predicts the sentiment polarity of the vectorized text.

### 3. Plan Generation Algorithm

- **Logic**: Rule-based mapping interaction system.
- **Functionality**: Takes the identified VARK learning style (Visual, Aural, Read/Write, Kinesthetic) and the student's performance level to recommend specific educational activities and strategies defined in `plan_generator.py`.

## Project Structure

```markdown
studentprofiler-demo-web-app/
├── app.py                  # Main Flask application entry point
├── model.py                # Facial Emotion Recognition logic
├── model_sad.py            # Sentiment Analysis logic
├── plan_generator.py       # Logic for generating learning plans based on VARK
├── requirements.txt        # Python dependencies
├── firebase/               # Firebase configuration and keys
├── models/                 # Pre-trained ML models
│   ├── ferd/               # Facial Emotion Recognition models & data
│   └── sad/                # Sentiment Analysis models
├── static/                 # Static assets (CSS, JS, images)
├── templates/              # HTML templates
└── uploads/                # Directory for uploaded files (videos etc.)
```

## Setup Instructions

### Prerequisites

- Python 3.8+ (Python 3.10 recommended)
- A Google Firebase project with Firestore enabled.

### Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/dileepadev/studentprofiler-demo.git
    cd studentprofiler-demo/studentprofiler-demo-web-app
    ```

2. **Create a virtual environment (Optional but recommended):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Firebase Configuration:**

    - Download your Firebase Admin SDK service account key JSON file from the Firebase Console.
    - Rename it to `serviceAccountKey.json`.
    - Place it in the `firebase/` directory.

### Running the Application

1. Start the Flask server:

    ```bash
    python app.py
    ```

2. Open your browser and navigate to:
    `http://127.0.0.1:5000`

## Usage

1. **Select Profile**: Choose a teacher, student, and subject from the dropdowns.
2. **Analyze**: Upload video or text data to be analyzed by the respective models.
3. **View Results**: See the emotional breakdown and generated learning plans.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

[MIT](../LICENSE)

## Developers

- **Dileepa Bandara** - *Initial work* - [dileepadev](https://github.com/dileepadev)

## Contact

For any inquiries, please contact:

- **Email**: [contact@dileepa.dev](mailto:contact@dileepa.dev)
- **GitHub**: [@dileepadev](https://github.com/dileepadev)

## Acknowledgements

- Special thanks to the open-source community for the invaluable libraries and tools that made this project possible.
