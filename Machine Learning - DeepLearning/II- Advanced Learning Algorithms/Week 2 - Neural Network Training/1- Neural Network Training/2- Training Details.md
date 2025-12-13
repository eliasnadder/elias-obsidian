[[1- Simplified Cost function for Logistic regression]]
Before looking at the details of training in neural network, let's recall how you had trained a logistic regression model:

1. Specify how to compute the output given the input feature x and the parameters w and b. 
The logistic regression function predicts `f(x)` is equal to `G` (The sigmoid function). If `z = np.dot(w, x) + b`, then `f_x = 1/(1 + np.exp(-z))`

2. Train the literacy regression model was to specify the loss function and also the cost function
 If religious regression is $L(f_{\vec{w},b}(\vec{x}),y)$, then the loss on that single training example was 
 ```python
loss = -y * np.log (f_x)-(1-y) * np.log(1-f_x)
```
This was a measure of how well is logistic regression doing on a single training example x comma y. 

3. Define the cost function, has parameters $\vec{w}$ and b, and that was just the average that is taking an average overall M training examples of the loss function computed on the M training examples
$$J(\vec{w},b)=\frac{1}{m} \sum_{i=0}^{m}L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)})$$
Using the loss function is a function of the output of the learning algorithm and the ground truth label as computed over a single training example whereas the cost function J is an average of the loss function computed over your entire training set. 

4. Train a logistic regression model was to use an algorithm specifically gradient descent to minimize that cost function J.
Minimize the cost J as a function of the parameters using gradient descent where w is updated as `w = w - alpha * dj_dw`. And b similarly is updated `b = w - alpha * dj_db`. 
***
## ?- How we can train a neural network in TensorFlow?
The same steps:
1. Specify how to compute the output given the input x and parameters W and B.
```python
import tensorflow as tf
from tensorflow.keras import Sequential
from tensorflow.keras.layers import Dense

model = Sequential([
	Dense(units=25, activation='sigmoid'),
	Dense(units=15, activation='sigmoid'),
	Dense(units=1, activation='sigmoid')
])
```
It defines the parameters w, b for all layers.
It specifies the entire architecture of the neural network and therefore tells TensorFlow everything it needs in In order to compute the output $\vec{a}^{[3]} = f(x)$

2. Compile the model and to tell it what loss you want to use
```python
from tensorflow.keras.losses import BinaryCrossentropy

model.compile(loss=BinaryCrossentropy() )
```
For the handwritten digit classification problem where images are either of a zero or a one, loss function to use is this one is actually the same loss function as what we had for logistic regression $$L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) = -\mathbf{y}^{(i)}log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})) - (1-\mathbf{y}^{(i)})log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))$$
To minimize is the average, taking the average over all m training examples of the loss on all of the training examples
> [!NOTE]
> In case you want to solve a regression problem rather than a classification problem. You can also tell TensorFlow to compile your model using a different loss function. 
> For example, if you have a regression problem and if you want to minimize the squared error loss. 

Once you specify this loss taking an average over the entire training set also gives you the cost function for the neural network

3. Call function to try to minimize the cost as a function of the parameters of the neural network. 
```python
model.fit(X, Y, epochs=100)
```
Use gradient descent to train the parameters of a neural network, then you are repeatedly, for every layer $l$ and for every unit $j$, 
$w^{[l]}_j=w^{[l]}_j-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}$
$b^{[l]}_j=b^{[l]}_j-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}$
After doing, say, 100 iterations of gradient descent, hopefully, you get to a good value of the parameters. In order to use gradient descent, the key thing need to compute is these partial derivative terms. What TensorFlow does, is to use an algorithm called backpropagation in order to compute these partial derivative terms. 