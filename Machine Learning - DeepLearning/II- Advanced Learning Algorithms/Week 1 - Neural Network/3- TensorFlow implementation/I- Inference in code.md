## A- Intro
TensorFlow is one of the leading frameworks to implementing deep learning algorithms. 
One of the remarkable things about neural networks is the same algorithm can be applied to so many different applications. 
****
## B- Real example
I'm going to use another example to illustrate inference. Sometimes I do like to roast coffee beans myself at home. My favorite is actually Colombian coffee beans. 
**?- Can the learning algorithm help optimize the quality of the beans you get from a roasting process like this?** 
When you're roasting coffee, two parameters you get to control are:
- the temperature at which you're heating up the raw coffee beans to turn them into nicely roasted coffee beans, 
- as well as the duration or how long are you going to roast the beans. 

![[Screenshot 2025-11-15 145719.png]]
In this slightly simplified example, 
- we've created the datasets of different temperatures and different durations, 
- as well as labels showing whether the coffee you roasted is good-tasting coffee. Where cross here, the positive cross y equals 1 corresponds to good coffee, and all the negative cross corresponds to bad coffee. 

It looks like a reasonable way to think of this dataset is 
1. if you cook it at too lower temperature, it doesn't get roasted and it ends up undercooked. 
2. If you cook it, not for long enough, the duration is too short, it's also not a nicely roasted set of beans. 
3. Finally, if you were to cook it either for too long or for too higher temperature, then you end up with overcooked beans. They're a little bit burnt beans. There's not good coffee either. 
4. It's only points within this little triangle here that corresponds to good coffee. This example is simplified a bit from actual coffee roasting.

![[Screenshot 2025-11-15 145942.png]]
***
## C- Implement Neural Network 
Even though this example is a simplified one for the purpose of illustration, there have actually been serious projects using machine learning to optimize coffee roasting as well. 

The task is given a feature vector $\vec{x}$ with both temperature and duration, say 
$$
\vec{x}=
\begin{bmatrix}
temp=200 \\
duration=17^o 
\end{bmatrix}
$$
**?- How can we do inference in a neural network to get it to tell us whether or not this temperature and duration setting will result in good coffee or not?** 

### 1- Use `tensorflow` library
It looks like this. We're going to set x to be an array of two numbers. The input features 200 degrees and 17 minutes. 
#### 1- Init inputs vector
```python
x = np.array([200.0,17.0])
```
#### 2- Create hidden layers & Compute activation values
##### A- Create the first hidden layers
create `layer_1` as this first hidden layer in the neural network, as `Dense` 
```python
layer_1 = Dense(units=3, activations='sigmoid')
```
- `units 3`, that means three units or three hidden units in this layer 
- using as the activation function, the sigmoid function. 
### Note
> Dense is another name for the layers of a neural network that we've learned about so far. 

##### B- Compute $\vec{a}^{[1]}$
Compute `a1` by taking `layer_1`, 
```python
a1 = layer_1(x)
```
- which is actually a function, and applying this function `layer_1` to the values of `x`. 
That's how you get $\vec{a}^{[1]}$, which is going to be a list of three numbers because layer 1 had three units. 
So $\vec{a}^{[1]}$ here may, just for the sake of illustration, be 
$$
\vec{a}^{[1]} =
\begin{bmatrix}
0.2 \\
0.7 \\
0.3
\end{bmatrix}
$$
##### C- Create the second layer (output layer)
For the second layer, layer 2, would be`dense`. 
- It has one unit and again to sigmoid activation function
- and compute `a2` by applying this `layer_2` function to the activation values from `layer_1` to `a1`.
```python
layer_2 = Dense(units=1, activations='sigmoid')
a2 = layer_2(a1)
```
That will give you the value of `a2`, which for the sake of illustration is maybe $\vec{a}^{[2]}=0.8$. 

#### 3- Compare with threshold
Finally, if you wish to threshold it at 0.5, then you can just test if `a2` is greater and equal to 0.5 and set y-hat equals to one or zero positive or negative cross accordingly. 
```python
if a2>= 0.5:
	yhat = 1
else:
	yhat = 0
```

That's how you do inference in the neural network using TensorFlow. But these are the key steps for forward propagation in how you compute a1 and a2 and optionally threshold a2. 
***
## D- Another Example: [[3- Inference; making predictions (forward propagation)|Handwritten digit classification problem]] 
In this example, x is a list of the pixel intensity values. 
1. Init `x` array of inputs
```python
x = np.array([[0.0,...245,...240...0]])
```

2. Then to initialize and carry out one step of [[3- Inference; making predictions (forward propagation)|forward propagation]], `layer_1` is a dense layer with 25 units and the sigmoid activation function. then compute `a1` equals the `layer_1` function applied to `x`.
```python
layer_1 = Dense(units=25, activations='sigmoid')
a1 = layer_1(x)
```

3. For the second layer, similarly, you set up `layer_2` as follows, and then computes `a2` as `layer_2` applied to `a1`. 
```python
layer_2 = Dense(units=15, activations='sigmoid')
a2 = layer_2(a1)
```
3. Then finally, Layer 3 is the third and final dense layer. 
```python
layer_3 = Dense(units=1, activations='sigmoid')
a3 = layer_3(a2)
```

4. Then finally, you can optionally threshold a`3` to come up with a binary prediction for y-hat. 
```python
if a3>= 0.5:
	yhat = 1
else:
	yhat = 0
```

## The full code
![[C2_W1_Lab01_… (5) - JupyterLab.pdf|Full Code]]
