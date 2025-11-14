## Example: handwritten digit recognition 
for simplicity we are just going to distinguish between the handwritten digits zero and one. 
- it's just a binary classification problem where we're going to input an image and classify, is this the digit zero or the digit one
![[Screenshot 2025-11-14 221946.png]]
- use an eight by eight image. And so this image of a one is this grid or matrix of eight by eight or 64 pixel intensity values where 255 denotes a bright white pixel and zero would denote a black pixel. And different numbers are different shades of gray in between the shades of black and white. 

Given these 64 input features, we're going to use the neural network with two hidden layers. Where the first hidden layer has 25 neurons or 25 units. Second hidden layer has 15 neurons or 15 units. And then finally the output layer or outputs unit, what's the chance of this being 1 versus 0?. 

## I- The sequence of computations
So let's step through the sequence of computations that in your neural network will need to make to go from the input $\vec{x}$, this eight by eight or 64 numbers to the predicted probability $\vec{a}^{[3]}$. 
### A- Compute $\vec{a}^{[1]}$
The first computation is to go from $\vec{x}$ to $\vec{a}^{[1]}$, and that's what the first layer of the first hidden layer does. It carries out a computation of $\vec{a}^{[1]}$ 
$$
\vec{a}^{[1]} =
\begin{bmatrix}
g(\vec{w_1}^{[1]}.\vec{x}+b_1^{[1]}) \\
. \\
. \\
. \\
g(\vec{w_{25}}^{[1]}.\vec{x}+b_{25}^{[1]})
\end{bmatrix}
$$
### B- Compute $\vec{a}^{[2]}$

$$
\vec{a}^{[2]} =
\begin{bmatrix}
g(\vec{w_1}^{[2]}.\vec{a}^{[1]}+b_1^{[2]}) \\
. \\
. \\
. \\
g(\vec{w_{15}}^{[2]}.\vec{a}^{[1]}+b_{15}^{[2]})
\end{bmatrix}
$$
### C- Compute $\vec{a}^{[3]}$
The Final step is then to compute $\vec{a}^{[3]}$ and we do so using a very similar computation. Only now, the output layer has just one unit

$$ \vec{a}^{[3]} = g(\vec{w_1}^{[3]}.\vec{a}^{[2]}+b_1^{[3]}) $$
And finally you can optionally take $\vec{a}^{[3]}$ and threshold it at 4.5 to come up with a binary classification label. Is this the digit 1? Yes or no? 
So the sequence of computations first takes x and then computes a1, and then computes a2, and then computes a3, which is also the output of the neural networks. You can also write that as f(x). $$\vec{a}^{[3]}=f(x)$$Because this computation goes from left to right, you start from x and compute a1, then a2, then a3. This album is also called **forward propagation** 
- because you're propagating the activations of the neurons. 
- So you're making these computations in the forward direction from left to right. 
And this is in contrast to a different algorithm called backward propagation or back propagation, which is used for learning. 
And by the way, this type of neural network architecture where you have more hidden units initially and then the number of hidden units decreases as you get closer to the output layer. There's also a pretty typical choice when choosing neural network architectures.