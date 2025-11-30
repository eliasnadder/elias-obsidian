## I- Intro
Write a function to implement a dense layer, that is a single layer of a neural network. I'm going to define the `dense` function, which takes as input the activation from the previous layer, as well as the parameters w and b for the neurons in a given layer. 
```python
def dense(a_in, W, b):
```

If layer 1 has three neurons, and if `w_1` and `w_2` and `w_3` are these, 
$$\vec{w_1}^{[1]}=
\begin{bmatrix}
1 \\
2
\end{bmatrix}
$$
$$\vec{w_2}^{[1]}=
\begin{bmatrix}
-3 \\
4
\end{bmatrix}
$$
$$\vec{w_3}^{[1]}=
\begin{bmatrix}
5 \\
-6
\end{bmatrix}
$$
then stack all of these wave vectors into a matrix. This is going to be a 2x3 matrix, where the first column is the parameter `w1_1`, the second column is the parameter `w1_2`, and the third column is the parameter `w1_3`.
```python
w = np.array([
			 [1, -3, 5],
			 [2, 4, -6]
			 ])
```

Then in a similar way, if you have parameters `b`
$b_1^{[1]} = -1$, $b_2^{[1]} = 1$, and $b_3^{[1]} = 2$
then we're going to stack these three numbers into a 1D array
```python
b = np.array([-1, 1, 2])
```
***
## II- Implement `dense()`
What the `dense()`will do is, 
1. Take as inputs the activation from the previous layer, `a_0`, or the activation from a later layer, as well as the `W` parameters, as well as the `b` parameters. 
2. Then output the activations from the current layer. 

### Here's the code
```python
def dense(a_in,W,b):
	units = W. shape[1] # no. units
	a_out = np.zeros(units)
	for j in range(units):
		w = W[:,j]
		z = np.dot(w,a_in) + b[j]
		a_out[j] = g(z)
	return a_out
```

- ```python
  units = W. shape[1]
  ```
	Here is a 2x3 matrix, and so the number of columns is three. 
	That's equal to the number of units in this layer.

- ```python
  a_out = np.zeros(units)
```
	set a to be an array of zeros with as many elements as there are units. In this example, we need to output three activation values, so this just initializes 
	
- ```python
  for j in range(units):
		w = W[:,j]
		z = np.dot(w,a_in) + b[j]
		a_out[j] = g(z)
  ```
	- go through a for loop to compute the first, second, and third elements of a. 
	- `w = W[:,j]` 
		this is how you pull out the $j^{th}$ column of a matrix in Python. 
	- `z = np.dot(w,a_in) + b[j]`: 
		Then compute z using the usual formula, 
	- `a_out[j] = g(z)` 
		compute the activation $a_j$ 

- ```python
  	return a_out
  ```
	Then finally return a 

What the dense function does is it inputs the activations from the previous layer, and given the parameters for the current layer, it returns the activations for the next layer. 
***
## III- `sequential()` function in code 
in order to implement forward prop in the neural network
```python
def sequential(x):
	a1 = dense(x,W1,b1)
	a2 = dense(a1,W2,b2)
	a3 = dense(a2,W3,b3)
	a4 = dense(a3,W4,b4)
	f_x= a4
	return f_x
```
> [!NOTE] Note
> If this is a neural network with four layers, then define the output `f_x = a_4`

> [!WARNING] Notice 
 >Use `W` because under the notational conventions from linear algebra is to use uppercase or a capital alphabet is when it's referring to a matrix and lowercase refer to vectors and scalars
 
***
## The lab
![[C2_W1_Lab03_CoffeeRoasting_Numpy.pdf]]