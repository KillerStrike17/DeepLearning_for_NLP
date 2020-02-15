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

## IRNN

[Code](https://github.com/KillerStrike17/DeepLearning_for_NLP/blob/master/Recurrent_Neural_Networks_101/IRNN.ipynb)

Here, I tried to replicate [IRNN](http://arxiv.org/pdf/1504.00941v2.pdf), but did some modifications on it to check the output. The dataset i worked on in it is [MNIST](http://yann.lecun.com/exdb/mnist/)

### Observation from experiments

RMS Prop is used instead of SGD because it is more stable.

| SR No. |Experiment | Result | Summary |
| --- | --- | --- | --- |
| 1 | Initialized model with all random paramters with 1024 batch size | Train Accuracy = 11.24% & Test Accuracy = 11.37% | The model trains very slow, after 10 epochs the accuracy is 11% |
| 2 | Initialized model kernel Initializer and Recurrent Initilizers with 32 batch size | Train Accuracy = 22.64% & Test Accuracy = 23.62% | The model trains much better than before |
| 3 | Initialized model kernel Initializer and Recurrent Initilizers with 32 batch size | Train Accuracy = 59.96% & Test Accuracy = 61.00% | The model trains very slow but train much better than before |
| 4 | Added a new layer with random params to experiment3| Train Accuracy = 41.03% & Test Accuracy = 40.83% | The model trains very slow, and even the accuracy is poor as compared to experiment 3 |


## Simple RNN Over IMDB Dataset

[Code](https://github.com/KillerStrike17/DeepLearning_for_NLP/blob/master/Recurrent_Neural_Networks_101/SimpleRNN_for_IMDB_Dataset.ipynb)

In this, I worked on text Classification over [IMDB Dataset](https://www.kaggle.com/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews). The problem was to classify the sentiment as negative or positive. The experiment over the basic model are:

| SR No. |Experiment | Result | Summary |
| --- | --- | --- | --- |
| 1 | Added a new Layer to the initial Model | Train Accuracy : Test Accuracy | The accuracy is pretty good over this basic model|
| 2 | Added a new Layer to the initial Model | Train Accuracy : Test Accuracy | The Accuracy of the model increases indicating that the model has generalised well |
| 3 | Activation of final layer is changed to Relu | Train Accuracy : Test Accuracy | The Model doesnot Train well |

## Simple RNN Over Reuters Dataset

[Code](https://github.com/KillerStrike17/DeepLearning_for_NLP/blob/master/Recurrent_Neural_Networks_101/SimpleRNN_Over_Reuters_Dataset.ipynb)

In this I worked on text classification again but with more categories i.e.46 classes. I worked on [Reuters Dataset](https://www.kaggle.com/nltkdata/reuters)

The experiments I conducted in it are:


| SR No. |Experiment | Result | Summary |
| --- | --- | --- | --- |
| 1 |  Testing the affect of batchsize on model, Batchsize of 512 | Train Accuracy: 90% Test Accracy: 34% |there wont be any change in the model summary, the results may very based on the dataset and model overfits |
| 2 |  Testing the affect of batchsize on model, Batchsize of 64 | Train Accuracy: 93% Test Accracy: 41%% |there wont be any change in the model summary, the results may very based on the dataset|

All the experiments I conducted was to understand RNNs, and how do they work. 
