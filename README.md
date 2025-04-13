# Reddit Political Text Classification

This project focuses on classifying text from Reddit to determine its political leaning (Conservative or Liberal) and identifying the subreddit it belongs to. The goal is to explore machine learning techniques that analyze and categorize Reddit posts based on their content and linguistic patterns.

## Features

- **Political Leaning Classification**: Predict whether a Reddit post leans Conservative or Liberal.
- **Subreddit Identification**: Predict the most likely subreddit a post belongs to, based on content alone.
- **NLP Models**: Apply neural architectures and word embeddings for text classification.
- **Custom Dataset**: A curated dataset of Reddit posts labeled with political leaning and subreddit metadata.

## Dataset

The dataset consists of approximately 9,000 Reddit posts labeled with:
- Political leaning: `Conservative` or `Liberal`
- Subreddit of origin

## Model Architecture

The project uses NLP techniques such as:
- Tokenization
- Pre-trained GloVe word embeddings

### LSTM-Based Classification

An LSTM network was used to capture sequential dependencies in Reddit text. The architecture includes:
- **Embedding Layer**: Maps tokens to GloVe vectors.
- **LSTM Layer**: Learns contextual and temporal relationships in the text.
- **Dense Layers**: Output predictions for political leaning and subreddit classification.

### Two-Stage Training Pipeline

1. **Stage 1: Political Leaning Prediction**  
   The model is first trained to classify political leaning. Subreddit classification layers are frozen during this stage.

2. **Stage 2: Subreddit Prediction**  
   The political leaning output is concatenated with LSTM features and passed to a second head for subreddit classification. The political layers are frozen to retain learned features.

This approach was intended to encourage shared representations while keeping task-specific learning paths.

## Outcome & Reflections

This project ultimately did **not** produce high-performing results, largely due to data limitations and the inherent complexity of the task. Key challenges included:

- **Small dataset size (9,000 posts)**: Too limited to train deep networks effectively, especially for nuanced tasks like ideological detection and subreddit classification.
- **Domain-specific language**: Reddit's informal and context-heavy writing style likely reduced the effectiveness of pre-trained embeddings like GloVe.
- **Ambiguity in labeling**: Inferring political leaning from posts is inherently noisy and subjective.

Despite the outcome, the project provided valuable hands-on experience in multi-task learning, LSTM-based NLP, and the challenges of working with real-world social media data. Future iterations might use transformer-based models (e.g., DistilBERT) and larger, more balanced datasets.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## Acknowledgments

- Reddit for providing access to public data
- Open-source libraries: PyTorch, Pandas, Scikit-Learn, Matplotlib, NumPy
