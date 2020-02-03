This Folder contains Codes to understand and implement Simple RNN. A simple model is developed to understand the concept of RNN and its structure. 

The Dataset worked on is IMDB Movie Reviews, Reuters, MNIST and Random Generated data (for Time series prediction).

## Time Series Prediction

[Code](https://github.com/KillerStrike17/DeepLearning_for_NLP/blob/master/Recurrent_Neural_Networks_101/Time_Series_Prediction.ipynb)

Here I Generated some random set of numbers and tried to predict the future number. As they are random numbers, hence I did not expect much accuracy. This exercise was to get started with Recurrent Neural Networks.

There are 1000 random points generated and then they are combined to form a group of 4 consecutive points and the 5th point as target variable. 
For example:

numbers generated : 1,2,3,4,5,6
  
Dataset = 1,2,3,4 -> 5

2,3,4,5 -> 6

### Observation from experiments

| SR No. |Experiment | N | Steps(Dimensionality) | Summary |
| --- | --- | --- | --- | --- |
|1| Optimizer as RMS Prop | 1000 | 4 | Train loss of 32.94 and test loss of 38.12- Which is good as we used random dataset and a very basic model |
|2| Optimizer as Adagrad | 1000 | 4 | Train loss of 35.85 and test loss of 37.69- Which is good as we used random dataset and a very basic model but bad on comparing with rmsprop |
|3| Optimizer as Adam | 1000 | 4 | Train loss of 33.61 and test loss of 39.11- Which is good as we used random dataset and a very basic model but bad on comparing with rmsprop  |
|4| Optimizer as Adadelta | 1000 | 4 | Train loss of 33.78 and test loss of 37.75- Which is good as we used random dataset and a very basic model |
|5| Increasing the dataset | 2000 | 4 | Increasing the dataset should increase the accuracy, but as the dataset is randomly generated, the model now has to learn 1600 random words and predict 400 instead of 800 and 200. Thus making it difficult |
|6| Increasing step size to 40| 1000 | 40 | Increasing the dimension means the network can noe look into 40 numbers rather than 4 to decide the next one which is good and results convey the same |
|7| Replacing relu with TanH | 1000 | 4 | Tan explodes on slight variation as it tries to fit in the number between -1 to 1 where as relu gives a gradual increase, hence that leads to much better and accurate pridictions |
