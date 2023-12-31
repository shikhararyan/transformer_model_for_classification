# Transformer Model for Classification

## (A) Data Loading and Preprocessing:

1. **Loading the Dataset:**
   - The code starts by importing necessary libraries and loading the IMDB dataset using Pandas.

2. **Data Cleaning and Preprocessing:**
   - The 'review' column is cleaned by removing non-alphabetic characters and converting the text to lowercase.
   - Stop words are removed using the NLTK library.

3. **Data Splitting:**
   - The dataset is split into training and testing sets using the `train_test_split` function from scikit-learn.

4. **Label Encoding:**
   - Sentiment labels are encoded using `LabelEncoder` for both the training and testing sets.

5. **Tokenization and Padding:**
   - Tokenization is performed using Keras's `Tokenizer`, and the sequences are padded to ensure uniform length using `pad_sequences`.

## (B) Transformer Model Building:

1. **Embedding Layer:**
   - The input sequences are passed through an Embedding layer to convert them into dense vectors of fixed size.

2. **Transformer Block:**
   - The core of the model is a Transformer block, which consists of self-attention mechanisms. It's applied multiple times (`num_heads`)
     to capture different aspects of the input sequence.

3. **Convolution and Global Average Pooling:**
   - After the attention mechanism, a 1D convolutional layer is applied to capture local patterns. Global Average Pooling is used to obtain a 
     fixed-size output from the convolutional layer.

4. **Dense Layers:**
   - Dropout is applied for regularization, and a Dense layer with ReLU activation is used to capture complex patterns. The final layer uses a 
     sigmoid activation for binary sentiment classification.

## (C) Model Training:

1. **Compilation and Training:**
   - The model is compiled using the Adam optimizer and binary cross-entropy loss. It is then trained on the training data for a specified number 
     of epochs.

## (D) Model Saving and Evaluation:

1. **Saving the Model:**
   - The trained model is saved in the HDF5 format for future use.

2. **Model Evaluation:**
   - The model is evaluated on the test set, and metrics like accuracy and a classification report are printed.

## (E) User Input Prediction:

1. **User Input Prediction Function:**
   - A function `predict_sentiment_transformer` is defined to predict the sentiment of user input. The function processes the input similarly to 
     the training data.

2. **Interactive User Input:**
   - The user is prompted to enter a review, and the model predicts the sentiment (Negative, Neutral, or Positive).

This code showcases the implementation of a Transformer model for sentiment analysis, providing a comprehensive example for understanding and applying this architecture.
