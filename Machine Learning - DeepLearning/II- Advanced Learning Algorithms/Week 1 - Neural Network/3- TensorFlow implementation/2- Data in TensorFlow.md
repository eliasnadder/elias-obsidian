When implement a new neural networks, you can have a consistent framework to think about how to represent your data. 
> One of the unfortunate things about the way things are done in code today is that many, many years ago `NumPy` was first created and became a standard library for linear algebra and Python. 
> And then much later the Google brain team, the team created `TensorFlow`. And so unfortunately there are some inconsistencies between how data is represented in `NumPy` and in `TensorFlow`. 

You have a data set from [[1- Inference in code|the coffee example]]. The input features `x` would write as follows. 
```python
x = np.array([[200.0, 17.0]])
```

^7113eb
So why do you have this double square bracket here? 
### ?- How NumPy stores vectors and matrices? 
Here is a matrix with 2 rows and 3 columns. 
$$
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}
$$
We call this a 2 x 3 matrix. So in code to store this matrix, this 2 x 3 matrix, 
```python
x = np.array([[1, 2, 3],
			  [4, 5, 6]])
```

So what we did previously when setting `x` to be input feature vectors, 
$$
x=\begin{bmatrix}
200 & 17
\end{bmatrix}
$$
```python
x = np.array([[200.0, 17.0]])
```
It creates a 1 x 2 matrix, that is just one row and two columns. And it called a row vector.

Let's look at a different example, if you were to define x,
$$x=\begin{bmatrix}
200 \\
17
\end{bmatrix}$$
```python
x = np.array([[200.0], 
			  [17.0]])
```
This creates a 2x1 matrix that has two rows and one column. And this example is also called a column vector. 

And the difference between using double square brackets like this versus a single square bracket, is that whereas the two examples of 2D arrays where one of the dimensions happens to be 1.
```python
x = np.array([200.0, 17.0])
```
And this technically is not 1 x 2 or 2 x 1, is just a linear array with no rows or no columns, but it's just a list of numbers. With TensorFlow the convention is to use matrices to represent the data. 

### And why is there this switching conventions? 
> Well it turns out that TensorFlow was designed to handle very large datasets and by representing the data in matrices instead of 1D arrays, it lets TensorFlow be a bit more computationally efficient internally. 

Example in this dataset with features 200°C in 17 minutes, we're represented [[#^7113eb|like this]]. And so this is actually a 1 x 2 matrix that happens to have one row and two columns. Going back to the code for carrying out for propagation or influence in the neural network. When you compute a1 equals layer 1 applied to x, what is a1? 

Well, a1 is actually going to be because the three numbers, is actually going to be a 
- 1 x 3 matrix. 
- floating point numbers meaning, `float32` 
- **`tensor`:** A tensor here is a data type that the TensorFlow team had created in order to store and carry out computations on matrices efficiently. So whenever you see tensor just think of that matrix. 
### Note
> Technically a tensor is a little bit more general than the matrix but for the purposes of this course, think of tensor as just a way of representing matrices. 