# Pos tagging with RNNs
Assignment 1 of 2022 NLP course at Unibo for Master Degree in AI. 

## Abstract 
The present work aims to study the Part-of-speech (POS) tagging task as Sequence Labbelling using Recurrent Neural Architectures. The approach adopted follows some fundamental steps: inspection of data, use of an embedding model, pre-processing of sentences and development of recurrent architectures. Concerning this last step, an increasing development in complexity was performed, starting from a basic architecture.

## System Description
Our baseline architecture coposed by:
- a frozen Embedding layer, initialized with GloVe word embedding matrix
- a Bidirectional LSTM
- -a Dropout and a Time-Distributed FC layer with Softmax.

We use a word tokenization to encode input string. During the creation of the embedding matrix following strategies was applied. Initially, if we don't find words as it, we search it lowercase version. If still not found, we try to search if it's an hypened terms, in this case the resultin embedding is the average of each word embedding. Finally, if no one of the previous methos works, we assign to it a default vector computed as the average of all the GloVe vectors. The vector embedding dimension is 100. 

Other model are subsequently created trying to improve the result and these are:
- 2 x Bidirectional LSTM + TD-Dense
- Bidirectional GRU + TD-Dense
- Bidirectional LSTM + 2 x TD-Dense

