### ?- Why neural networks need activation functions and why they just don't work if we were to use the linear activation function in every neuron in the neural network. 
In demand prediction example. What would happen if we were to use a linear activation function for all of the nodes in this neural network? It turns out that this big neural network will become no different than just linear regression. 
So this would defeat the entire purpose of using a neural network because it would then just not be able to fit anything more complex than the linear regression model. 

Look at the example of a neural network where the input x is just a number and we have one hidden unit with parameters w1 and b1 that outputs a1, which is here, just a number, and then the second layer is the output layer and it has also just one output unit with parameters w2 and b2 and then output a2, which is also just a number, which is the output of the neural network. 

#### ?- What if we were to use the linear activation function $g(z)=z$ everywhere. 
So to compute a1 as a function of x, the neural network will use a1 equals 
$$a^{[1]}=w_1^{[1]}.x+b_1^{[1]}$$
Then a2 is equal to 
$$a^{[2]}=w_1^{[2]}.a^{[1]}+b_1^{[2]}$$
If we simplify,
$$a^{[2]}=w_1^{[2]}.a^{[1]}+b_1^{[2]}$$
$$a^{[2]}=w_1^{[2]}.(w_1^{[1]}.x+b_1^{[1]})+b_1^{[2]}$$
$$a^{[2]}=(w_1^{[2]}w_1^{[1]}).x+w_1^{[2]}b_1^{[1]})+b_1^{[2]}$$
$$a^{[2]}=w.x+b$$
So a2 is just a linear function of the input x. Rather than using a neural network with one hidden layer and one output layer, we might as well have just used a linear regression model.
This is why having multiple layers in a neural network doesn't let the neural network compute any more complex features or learn anything more complex than just a linear function. 

So in the general case, if you had a neural network with multiple layers and use a linear activation function for all of the hidden layers and also use a linear activation function for the output layer, then it turns out this model will compute an output that is completely equivalent to linear regression. 

Or alternatively, use a linear activation function for all the hidden layers, or use a logistic activation function for the output layer, then it turns out this model becomes equivalent to logistic regression
So this big neural network doesn't do anything that you can't also do with logistic regression. 
> [!ERROR]
> That's why a common rule of thumb is don't use the linear activation function in the hidden layers of the neural network. 

In fact, recommend typically using the ReLU activation function.