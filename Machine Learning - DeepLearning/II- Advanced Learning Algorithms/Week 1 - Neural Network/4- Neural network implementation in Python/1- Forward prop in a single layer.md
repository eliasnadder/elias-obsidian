?- How you implement forward prop in a single layer?
we're going to continue using the coffee roasting model shown here. I'm going to use 1D arrays to represent all of these vectors and parameters.
```python
x = np.array([200, 17])
```
So the first value you need to compute is $a_1^{[1]}$
$$a_1^{[1]}=g(\vec{w_1}^{[1]}.\vec{x}+b_1^{[1]})$$
> [!NOTE] Note 
> Use the convention at a term like `w2_1`, It represents as a variable $w_1^{[2]}$. 

To compute `a1_1`, we have parameters `w1_1` and `b1_1`, then compute `z1_1`
```python
a1_1 = np.array([1, 2])
b1_1 = np.array([-1])
z1_1 = np.dot(w1_1, x) + b1_1
a1_1 = sigmoid(z1_1)
```

Next let's go on to compute `a1_2`
$$a_2^{[1]}=g(\vec{w_2}^{[1]}.\vec{x}+b_2^{[1]})$$
And same as before
```python
a1_2 = np.array([-3, 4])
b1_2 = np.array([1])
z1_2 = np.dot(w1_2, x) + b1_2
a1_2 = sigmoid(z1_2)
```

Finally you do the same thing to compute `a1_3`. 
$$a_3^{[1]}=g(\vec{w_3}^{[1]}.\vec{x}+b_3^{[1]})$$
And same as before
```python
a1_3 = np.array([5, -6])
b1_3 = np.array([2])
z1_3 = np.dot(w1_3, x) + b1_3
a1_3 = sigmoid(z1_3)
```

Now, you've computed these three values `a1_1`, `a1_2`, and `a1_3` and group them together into an array to give you `a1`.
```python
a1 = np.array([a1_1, a1_2, a1_3])
```

So you compute, the output a2, 
$$a_1^{[2]}=g(\vec{w_1}^{[2]}.\vec{a}^{[1]}+b_1^{[2]})$$
```python
a2_1 = np.array([-7, 8, 9])
b2_1 = np.array([3])
z1_3 = np.dot(w2_1, a1) + b2_1
a2_1 = sigmoid(z2_1)
```