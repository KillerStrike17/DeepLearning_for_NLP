# Sentimental Analysis of Movie Prediction

The code is taken from the book: [Deep learning with Python - Francois Chollet](http://faculty.neu.edu.cn/yury/AAI/Textbook/Deep%20Learning%20with%20Python.pdf): Chapter 6

## [Word Embedding](https://towardsdatascience.com/what-the-heck-is-word-embedding-b30f67f01c81)

Word Embedding is used for model that have learned to map set of words or phrases in dictionary to a numerical representation. Embedding came in to solve the [scalability and sparsity problem of One Hot Encoder](https://www.quora.com/What-are-the-main-issues-with-using-one-hot-encoding). 

One such popular word embedding model is GloVe by Stanford

### [GloVe](https://nlp.stanford.edu/projects/glove/)

* It is an unsupervised learning algorithm 

* It is used to obtain vector representation of words

* In transfer learning it is used as Word Embedding Layer

## Best Results

| Sr No. | Dimensions | BatchSize | Optimizer | Embedding Constraint | Train Accuracy | Validation Accuracy | Accuracy & Loss Graph | Remarks |
| --- | --- | --- | ---| --- | --- | --- | --- | --- | 



**Note:** The rest of the grid search results can be viewed in the colab file and *embedding_constraint* parameter is working only in keras and not in tensorflow binding of keras.
