Previously, If you want to do [[1- Inference in code|forward prop]], you initialize the data `x`, create `layer_!` then compute `a1`, then create `layer_2` and compute `a2`. 
So this was an explicit way of carrying out forward prop one layer of computation at the time. 

It turns out that `TensorFlow` has a different way of implementing forward prop as well as learning. 
### Different way of building a neural network in TensorFlow
which is that same as before.
- you're going to create `layer_1` and create `layer_2`. 
- But now instead of you manually taking the data and passing it to `layer_1` and then taking the activations from `layer_1` and pass it to `layer_2`. We can instead tell tensor flow that we would like it to take `layer_1` and `layer_2` and string them together to form a neural network. 
```python
layer_1 = Dense(units=3, activation='sigmoid')
layer_2 = Dense(units=1, activation='sigmoid')
model = Sequential([layer_1, layer_2])
```

It turns out that with the `sequential` framework `TensorFlow` can do a lot of work for you. 
Let's say you have a training set like this,

|     |     | y   |
| --- | --- | --- |
| 200 | 17  | 1   |
| 120 | 5   | 0   |
| 425 | 20  | 0   |
| 212 | 18  | 1   |
This is for the coffee example. You can then take the training data as inputs `x` and put them into a `numpy` array. 
```python
x = np.array([[200.0, 17.0],
			  [120.0, 5.0],
			  [425.0, 20.0],
			  [212.0, 18.0]])
```
This here is a 4x2 matrix and the target labels `y` can then be written as follows. 
```python
y = np.array([1, 0, 0, 1])
```
And this is just a 1D array of length four. And it turns out that given the data `x` and `y` stored in this matrix `x` and this array `y. 

If you want to train this neural network, all you need to do is 
1. call to functions you need to call `model.compile(...)` with some parameters. 
2. And then you need to call `model.fit(x, y)`, which tells `TensorFlow` to take this neural network that are created by sequentially string together layers one and two, and to train it on the data `x` and `y`. 

>[!Note] Note
> If you have a new example, say `x_new` with two features than to carry out forward prop instead of having to do it one layer at a time yourself, you just have to call `model.predict(x_new)` and this will output the corresponding value of a two for you given this input value of `x`.

---
So model predicts carries out forward propagation and carries an inference for you, using this neural network that you compiled using the `sequential` function.

### Declare NN in right way
By convention we don't explicitly assign the two layers to two variables, layer one and layer two. Instead, we write like this
```python
model = Sequential([
	Dense(units=3, activation='sigmoid'),
	Dense(units=1, activation='sigmoid')
])
```
---
### Example: [[3- Inference; making predictions (forward propagation)|digit classification]]
So previously we had `x` in this input layer one is a layer a one equals. They want to apply to `x` and so on through `layer_2` and `layer_3` in order to try to classify a digit. 
And now, you can instead specify what are `layer_1`, `layer_2`, `layer_3` and tell `TensorFlow` to string the layers together for you into a new network and same as before. 
```python
model = Sequential([
	Dense(units=25, activation='sigmoid'),
	Dense(units=15, activation='sigmoid'),
	Dense(units=1, activation='sigmoid')
])
model.compile(...)
x = np.array([[0..., 245, ..., 17],
			  [0..., 200, ..., 184]
			])
y = np.array([1, 0])
model.fit(x, y)
model.predict(x_new)
```
***
## The lab
![[C2_W1_Lab02_CoffeeRoasting_TF.pdf]]
***
## Explaintion
![[Lab.pdf]]