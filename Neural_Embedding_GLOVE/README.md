# Sentimental Analysis of Movie Prediction

The code is taken from the book: [Deep learning with Python - Francois Chollet](http://faculty.neu.edu.cn/yury/AAI/Textbook/Deep%20Learning%20with%20Python.pdf): Chapter 6

## [Word Embedding](https://towardsdatascience.com/what-the-heck-is-word-embedding-b30f67f01c81)

Word Embedding is used for model that have learned to map set of words or phrases in dictionary to a numerical representation. Embedding came in to solve the [scalability and sparsity problem of One Hot Encoder](https://www.quora.com/What-are-the-main-issues-with-using-one-hot-encoding). 

One such popular word embedding model is GloVe by Stanford

### [GloVe](https://nlp.stanford.edu/projects/glove/)

* It is an unsupervised learning algorithm 

* It is used to obtain vector representation of words

* In transfer learning it is used as Word Embedding Layer

## Best Results(used UnitNorm Embedding Constraint)

All the plots and results are in the notebook

| Sr No. | Train Sample Size | Dimensions | Train Accuracy | Validation Accuracy | Remarks |
| --- | --- | --- | ---| --- | --- |
| 1 | 2000 | 50 | 99.95% | 50.37% | The validation accuracy remains constant whereas the loss increases |
| 2 | 2000 | 100 | 99.95% | 50.71% | The validation accuracy remains constant whereas the loss increases |
| 3 | 2000 | 200 | 99.95% | 50.55% | The validation accuracy remains constant whereas the loss increases |
| 4 | 2000 | 300 | 99.95% | 50.42% | The validation accuracy remains constant whereas the loss increases |
| 5 | 8000 | 50 | 99.90% | 83.93% | The validation accuracy is better as compared to previous tests, the loss is very constant and the model is badly overfitting|
| 6 | 8000 | 100 | 100.00% | 84.36% | The validation accuracy is better as compared to previous tests, the loss is very constant and the model is badly overfitting |
| 7 | 8000 | 200 | 99.99% | 83.38% | The validation accuracy is better as compared to previous tests, the loss is very increasing on more epochs and the model is badly overfitting |
| 8 | 8000 | 300 | 100.00% | 81.64% | The validation accuracy is better as compared to previous tests, the loss is very increasing on more epochs and the model is badly overfitting |
| 9 | 20000 | 50 | 98.62% | 51.50% | The validation accuracy remains constant whereas the loss increases |
| 10 | 20000 | 100 | 88.74% | 51.16% | The validation accuracy remains constant whereas the loss increases |
| 11 | 20000 | 200 | 91.08% | 50.60% | The validation accuracy remains constant whereas the loss increases |
| 12 | 20000 | 300 | 91.44% | 50.84% | The validation accuracy remains constant whereas the loss increases |

## Conclusions:

* Based on the performed experiments we conclude that when the training samples is very less as compared to validation and embedding layer, the model is learning very few words and is tested against a lot of new words which will definately affect the accuracy.

* When the sample size is 8000 words, it is gives a decent accuracy of 83-84% in all the cases which is pretty good based on the training conditions. It overfits but, some tweaks can be made.

* When there is too many sample size which is 20000 words where as embedding layer just have 10000, it is forced to learn only half of the data, hence the accurayc is stuck at 50%. 

**Note:** The rest of the grid search results can be viewed in the colab file and *embedding_constraint* parameter is working only in keras and not in tensorflow binding of keras.
