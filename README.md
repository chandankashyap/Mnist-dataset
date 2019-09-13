# Mnist-dataset
An introduction to Neural Networks with Mnist dataset

The MNIST database of handwritten digits, available from this page, has a training set of 60,000 examples, and a test set of 10,000 examples. The digits have been size-normalized and centered in a fixed-size image.

The following steps were taken to arrive to a model with 98% val_acc:

1.	Load data
2.	Check for null and missing values
3.	Normalization
4.	Reshape
5.	Label encoding
6.	Split training and valdiation set

7.	The Approach:

Model 1: Based on SGD optimizer
•	Layers – Input layer, 4 hidden layers, Output layer

•	Activation function (Inner layers) – Relu

•	Activation function (Output layer) – Softmax

•	learning_rate - 0.1

•	training_epochs - 20

•	batch_size - 100

•	Optimizers – SGD

•	Loss - categorical_crossentropy

Model 1 delivered val_acc = 0.9651



Model 2: Based on ADAM optimizer, while retaining the rest of the parameters as Model 1

•	Layers – Input layer, 4 hidden layers, Output layer

•	Activation function (Inner layers) – Relu

•	Activation function (Output layer) – Softmax

•	learning_rate - 0.1

•	training_epochs - 20

•	batch_size - 100

•	Optimizers – ADAM

•	Loss - categorical_crossentropy

Model 2 delivered val_acc = 0.9781

Since ADAM optimizer delivered a better accuracy, we retain ADAM in the next model and evaluate with different “learning_rate” i.e. 0.01 and 0.5



Model 2a: Based on ADAM optimizer, and “learning_rate” = 0.01

•	Layers – Input layer, 4 hidden layers, Output layer

•	Activation function (Inner layers) – Relu

•	Activation function (Output layer) – Softmax

•	learning_rate - 0.01

•	training_epochs - 20

•	batch_size - 100

•	Optimizers – ADAM

•	Loss - categorical_crossentropy

Model 2a delivered val_acc = 0.9800



Model 2b: Based on ADAM optimizer, and “learning_rate” = 0.5

•	Layers – Input layer, 4 hidden layers, Output layer

•	Activation function (Inner layers) – Relu

•	Activation function (Output layer) – Softmax

•	learning_rate - 0.5

•	training_epochs - 20

•	batch_size - 100

•	Optimizers – ADAM

•	Loss - categorical_crossentropy

Model 2b delivered val_acc = 0.9778

The accuracy, as measured by the 3 different learning rates 0.01, 0.1 and 0.5 are around 98%. 
As there are no considerable gains by changing the learning rates, we stick with the default learning rate of 0.1.

We proceed to fit a neural network with 5 hidden layers with the features in the hidden layer set as (300, 100, 100, 100, 200) respectively. 
To ensure that the two models are comparable, we will set the training epochs as 20, and the training batch size as 100.



Model 3: Based on ADAM optimizer, and “learning_rate” = 0.1,  5 hidden layers

•	Layers – Input layer, 5 hidden layers, Output layer

•	Activation function (Inner layers) – Relu

•	Activation function (Output layer) – Softmax

•	learning_rate - 0.1

•	training_epochs - 20

•	batch_size - 100

•	Optimizers – ADAM

•	Loss - categorical_crossentropy

Model 3 delivered val_acc = 0.9797

Compared to our first model, adding an additional layer did not significantly improve the accuracy from our previous model. 
However, there are computational costs (in terms of complexity) in implementing an additional layer in our neural network. 
Given that the benefits of an additional layer are low while the costs are high, we will stick with the 4 layer neural network.

We now proceed to include dropout (dropout rate of 0.3) in our second model to prevent overfitting.



Model 4: Based on ADAM optimizer, and “learning_rate” = 0.1,  4 hidden layers, 3 Dropout (0.3) layers

•	Layers – Input layer, 4 hidden layers, 3 Dropout layers, Output layer

•	Activation function (Inner layers) – Relu

•	Activation function (Output layer) – Softmax

•	learning_rate - 0.1

•	training_epochs - 20

•	batch_size - 100

•	Optimizers – ADAM

•	Loss - categorical_crossentropy

Model 4 delivered val_acc = 0.9817

With a validation score of close > 98%, we proceed to use this model to predict for the test set.


8.	Result -  9805 instances out of 10000 were correctly identified.





