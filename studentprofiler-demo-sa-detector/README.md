# Student Profiler Demo - Sentiment Analysis Detector

This component of the Student Profiler system is responsible for analyzing textual feedback and responses to determine the underlying sentiment using natural language processing (NLP) and machine learning techniques.

## Features

- **Sentiment Classification**: Categorizes text input into sentiment classes (e.g., based on the training data labels).
- **Custom Model Training**: Provides a script to train a Multinomial Naive Bayes classifier on custom datasets (e.g., student feedback forms).
- **Text Vectorization**: Converts raw text into meaningful numerical representations using Bag-of-Words techniques.
- **Model Persistence**: Saves and loads trained models and vectorizers using Joblib for efficient reuse.

## Tech Stack

- **Language**: Python
- **Machine Learning**:
  - Scikit-learn
- **Serialization**:
  - Joblib
- **Data Handling**:
  - NumPy
  - Pandas
  - CSV (Python built-in)

## Algorithms & Approaches

### 1. Text Preprocessing & Vectorization

- **Method**: Bag-of-Words (BoW)
- **Tool**: `CountVectorizer` from Scikit-learn.
- **Process**: Converts a collection of text documents to a matrix of token counts, enabling digital processing of the text data.

### 2. Classification

- **Algorithm**: Multinomial Naive Bayes (`MultinomialNB`)
- **Process**:
  - Takes the vectorized text as input.
  - Predicts the probability of the text belonging to a specific sentiment category based on prior probabilities calculated during training.
  - Suitable for classification with discrete features (like word counts).

## Project Structure

```markdown
studentprofiler-demo-sa-detector/
├── model_trainer.py        # Script to train and save the sentiment model
├── model_tester.py         # Script to load the model and test predictions
├── requirements.txt        # Python dependencies
├── Form/                   # Directory containing input data (e.g., CSV)
│   └── form_responses.csv  # Dataset for training
└── Model/                  # Directory for saved model files
    ├── sentiment_analysis_model.joblib
    └── vectorizer.joblib
```

## Setup Instructions

### Prerequisites

- Python 3.8+ (Python 3.10 recommended)

### Installation

1. **Navigate to the directory:**

    ```bash
    cd studentprofiler-demo/studentprofiler-demo-sa-detector
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

## Usage

### 1. Train the Model

To train the sentiment analysis model using your dataset:

1. Place your training data in `Form/form_responses.csv`. Ensure it follows the expected format (columns for questions/responses).
2. Run the training script:

    ```bash
    python model_trainer.py
    ```

    *This will split the data, train the classifier, report accuracy, and save the model to the `Model/` directory.*

### 2. Test Predictions

To visualize the model's predictions on new data:

1. Open `model_tester.py` and modify the `new_texts` list with the text you want to analyze.
2. Run the tester:

    ```bash
    python model_tester.py
    ```

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

- Scikit-learn community for robust ML tools.
