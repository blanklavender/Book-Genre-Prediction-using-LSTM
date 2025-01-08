# Book-Genre-Prediction-using-LSTM

## Architecture:

The architecture is a multi-layered LSTM (Long Short-Term Memory) model designed for book genre
classification. It starts with an embedding layer that maps input words to dense vector representations
using pretrained word embeddings. The input is a sequence of fixed length (max seq length = 20),
and each word is represented by an embedding of size embedding dim. This sequence of embeddings
is processed by a 2-layer LSTM with a hidden size of 256, which captures temporal dependencies in
the text.

The final hidden state of the LSTM is passed to a fully connected (FC) layer that maps it to a vector of
size output dim, where output dim is the number of genres in the dataset. The raw outputs (logits)
from the FC layer are converted into probabilities using a softmax function, enabling multi-class
classification. The model is trained using cross-entropy loss, and predictions are made by selecting
the class with the highest probability. The architecture is tailored to handle sequential text data
efficiently while leveraging the temporal modeling capability of LSTMs.

## Improvements introduced from the old model:

Max sequence length was changed 10 -¿ 20 to better capture the semantics of longer sentences.
The tensorflow framework was switched to Pytorch’s NN.Module to define the architecture properly.
Modified vocabulary and pre-trained word embeddings size for the dataset. Split training into training
and validation set and added early stopping to prevent overfitting. The learning rate changed to 0.0005
from 0.001. Modified dropout rate to 0.5 Trained for 50 epochs.

## Results:

Test Accuracy: 54.08%
Train Accuracy: 55.12%
