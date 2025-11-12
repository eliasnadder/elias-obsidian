The fundamental building block of most modern neural networks is a layer of neurons. 

## Hidden layer in depth
Here's the example we had from the [[2- Demand Prediction|demand  prediction example]] where we had four input features that were set to this layer of three neurons in the hidden layer that then sends its output to this output layer with just one neuron. 

Let's zoom in to the hidden layer to look at its computations. This hidden layer inputs four numbers and these four numbers are inputs to each of three neurons. Each of these three neurons is just implementing a little logistic regression unit or a little bit logistic regression function. 

![[Screenshot 2025-11-12 232730.png]]
Take this first neuron. It has two parameters, $w$ and $b$. In fact, to denote that
- I'm going to subscript this as $w_1$, $b_1$. What it does is I'll output some activation value $a$. 
$$a_1=g(\vec{w_1}.\vec{x}+b_1)$$
where, 
$$z=\vec{w_1}.\vec{x}+b$$
$$g(z)=\frac{1}{1+e^{-(z)}}$$
- Maybe this ends up being a number $a_1=0.3$ and that's the activation value a of the first neuron. There's a 0.3 chance of this being highly affordable based on the input features. 

Look at the second neuron. The second neuron has parameters $w_2$ and $b_2$. It computes $a_2$
$$a_2=g(\vec{w_2}.\vec{x}+b_2)$$

- Maybe this ends up being a number $a_2=0.7$. There's a 0.7 chance that we think the potential buyers will be aware of this t-shirt. 

Similarly, the third neuron has a third set of parameters $w_3$, $b_3$. To compute the activation value $a_3$ equals
$$a_3=g(\vec{w_3}.\vec{x}+b_3)$$
- Maybe this ends up being a number $a_3=0.2$.

### II- Label the hidden layers
In this example, these three neurons output 0.3, 0.7, and 0.2, and this vector of three numbers becomes the vector of activation values a, that is then passed to the final output layer of this neural network. 
$$\vec{a}=[0.3,0.7,0.2]$$
Now, when you build neural networks with multiple layers, it'll be useful to give the layers different numbers. 
By convention, 
- this hidden layer is called layer 1 of the neural network 
- and this output layer is called layer 2 of the neural network. 
- The input layer is also sometimes called layer 0

### III- Distinguish between hidden layers
Today, there are neural networks that can have dozens or even hundreds of layers. 
But in order to introduce notation to help us distinguish between the different layers, use superscript square bracket i $^{[i]}$ to index into different layers. 
- In particular, a superscript in square brackets 1 $^{[1]}$, use that's a notation to denote the output of layer 1 of this hidden layer
- Similarly, $w_1$ and $b_1$ are the parameters of the first unit in layer 1 of the neural network, so add a superscript in square brackets 1
$$a_1^{[1]}=g(\vec{w_1}^{[1]}.\vec{x}+b_1^{[1]})$$
and so on,
$$a_2^{[1]}=g(\vec{w_2}^{[1]}.\vec{x}+b_2^{[1]})$$$$a_3^{[1]}=g(\vec{w_3}^{[1]}.\vec{x}+b_3^{[1]})$$
> This notation is getting a little bit cluttered. But the thing to remember is whenever you see this superscript square bracket 1, that just refers to a quantity that is associated with layer 1 of the neural network. If you see superscript square bracket 2, that refers to a quantity associated with layer 2 of the neural network and similarly for other layers as well, including layer 3, layer 4 and so on for neural networks with more layers. 

### IV- Zoom on the output layer

![[Screenshot 2025-11-12 232618.png]]
this activation vector $\vec{a}^{[1]}$ is the input to layer 2. Now let's zoom into the computation of layer 2 of this neural network, which is also the output layer. 
The input to layer 2 is the output of layer 1, $$\vec{a}^{[1]}=[0.3,0.7,0.2]$$Because the output layer has just a single neuron, all it does is it computes $a_1$ that is the output of this first and only neuron
$$a_1^{[2]}=g(\vec{w_1}^{[2]}.\vec{a_1}^{[1]}+b_1^{[2]})$$
$$z=\vec{w_1}^{[2]}.\vec{a_1}^{[1]}+b_1^{[2]}$$
$$g(z)=\frac{1}{1+e^{-(z)}}$$
- If this results in a number, say 0.84, then that becomes the output layer of the neural network. 
- In this example, because the output layer has just a single neuron, this output is just a scalar, is a single number rather than a vector of numbers. 
- It's the output of this layer and the final output of the neural network. 

### V- Predict the y
![[Screenshot 2025-11-12 232523.png]]
Once the neural network has computed $a_2$, there's one final optional step that you can choose to implement or not, which is if you want a binary prediction, 1 or 0, is this a top seller? 

Take the number $a^{[2]}=0.84$ , and threshold this at 0.5. If it's greater than 0.5, you can predict y equals 1 and if it is less than 0.5, then predict your y hat equals 0. 