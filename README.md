# Reddit Political Text Classification

This project focuses on classifying text from Reddit to determine its political leaning (Conservative or Liberal) and identifying the subreddit it belongs to. The goal is to leverage machine learning techniques to analyze and categorize Reddit posts based on their content.

## Features

- **Political Leaning Classification**: Predict whether a Reddit post leans Conservative or Liberal.
- **Subreddit Identification**: Identify the subreddit where the post originated.
- **Machine Learning Models**: Utilize state-of-the-art natural language processing (NLP) models for text classification.
- **Dataset**: A curated dataset of Reddit posts labeled with political leaning and subreddit information.

## Dataset

The dataset consists of Reddit posts labeled with:
- Political leaning: `Conservative` or `Liberal`

## Model

The project uses NLP techniques such as:
- Tokenization
- Word embeddings

### LSTMs for Text Classification

Long Short-Term Memory (LSTM) networks are utilized in this project to capture sequential dependencies in text data. LSTMs are a type of recurrent neural network (RNN) that excel in handling long-term dependencies, making them well-suited for natural language processing tasks.

The LSTM-based model in this project includes:
- **Embedding Layer**: Converts words into dense vector representations.
- **LSTM Layer**: Processes the sequence of embeddings to capture contextual information.
- **Fully Connected Layer**: Maps the LSTM outputs to the target classes (Conservative, Liberal, or subreddit categories).

This architecture helps improve the accuracy of text classification by leveraging the sequential nature of language.

### Two-Stage Training Architecture

The model employs a two-stage training process to enhance its performance on both tasks: political leaning classification and subreddit prediction.

1. **Stage 1: Political Leaning Prediction**  
    In the first stage, the output of the LSTM layer is used to predict the political leaning of a Reddit post. During this phase, the layers responsible for subreddit prediction are frozen, ensuring that the model focuses solely on learning features relevant to political leaning classification.

2. **Stage 2: Subreddit Prediction**  
    In the second stage, the output from the political leaning prediction is concatenated with the LSTM output. This combined representation is then passed to a dense layer responsible for predicting the subreddit. During this phase, the lower layers that were trained for political leaning prediction are frozen, ensuring that the learned features remain intact while the model adapts to the subreddit classification task.

This two-stage approach allows the model to leverage shared features while maintaining task-specific representations, improving overall performance on both classification tasks.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.


## Acknowledgments

- Reddit for providing the data
- Open-source libraries like PyTorch, Pandas, Scikit-Learn, Matplotlib,  NumPy,
