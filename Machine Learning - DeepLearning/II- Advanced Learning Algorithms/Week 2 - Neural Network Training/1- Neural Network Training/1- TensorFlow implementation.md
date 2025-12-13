Continue with example of [[3- Inference; making predictions (forward propagation)|handwritten digit recognition]], recognizing a image as zero or a one.
If you're given a training set of examples comprising images x, as was the ground truth label y.
## ?- How would you train the parameters of this neural network? 
### 1$^{st}$ step
Create the model with hidden layers
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
---
### 2$^{nd}$ step 
Ask TensorFlow to compile the model. The key is to specify what is the loss function you want to use. 
```python
from tensorflow.keras.losses import BinaryCrossentropy

model.compile(loss=BinaryCrossentropy() )
```
> In this case, we'll use something that goes by the `BinaryCrossentropy` loss function. Then having specified the loss function.

### 3$^{rd}$ step
Call the fit function, which tells TensorFlow to fit the model that you specified in step 1 using the loss of the cost function that you specified in step 2 to the dataset X, Y. 
```python
model.fit(X, Y, epochs=100)
```

> [!NOTE]
> Previously, when we talked about gradient descent, we had to decide how many steps to run gradient descent or how long to run gradient descent, so `epochs` is a technical term for how many steps of a learning algorithm like gradient descent you may want to run. 
