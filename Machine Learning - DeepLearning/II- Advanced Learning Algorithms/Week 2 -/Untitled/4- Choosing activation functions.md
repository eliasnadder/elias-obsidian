Choose different activation functions for different neurons in your neural network, it turns out that there'll often be one fairly natural choice, **depending on what is the target or the ground truth label y.** 

### In a classification problem,
- where y is either zero or one, so a binary classification problem, **then the sigmoid activation function will almost always be the most natural choice**, 
- Because then the neural network learns to predict the probability that y is equal to one, just like we had for logistic regression. 

### In a regression problem,  
For example, try to predict how tomorrow's stock price will change compared to today's stock price. Well, it can go up or down, and so in this case y would be a number that can be either positive or negative, and in that case recommend use the linear activation function. 

Finally, on non-negative values, such as predict the price of a house, that can never be negative, then the most natural choice will be **the ReLU activation function** because as you see here, this activation function only takes on non-negative values, either zero or positive values. 

### How about the hidden layers of a neural network? 
It turns out that the ReLU activation function is by far the most common choice in how neural networks. Even though we had initially described neural networks using the sigmoid activation function. 

> [!INFO]
> Well, the one exception that you do use a sigmoid activation function in the output layer if you have a binary classification problem. So why is that? Well, there are a few reasons. 

1. First, compare the ReLU and the sigmoid activation functions, the ReLU is a bit faster to compute because it just requires computing max of 0, z, whereas the sigmoid requires taking an exponentiation and then a inverse and so on, and so it's a little bit less efficient. 

2. The second reason is that the ReLU function goes flat only in one part of the graph; here on the left is completely flat, whereas the sigmoid activation function, it goes flat in two places. It goes flat to the left of the graph and it goes flat to the right of the graph. If you're using gradient descent to train a neural network, then when you have a function that is fat in a lot of places, gradient descents would be really slow. 

I know that gradient descent optimizes the cost function J of W, B rather than optimizes the activation function, but the activation function is a piece of what goes into computing, and that results in more places in the cost function J of W, B that are flats as well and with a small gradient and it slows down learning.
