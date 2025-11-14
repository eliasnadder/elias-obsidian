![[Screenshot 2025-11-14 202416.png]]
This network has four layers, 
- not counting the input layer, which is also called Layer 0 
- layers 1, 2, and 3 are hidden layers
- layer 4 is the output layer

#### Note
> By convention, when we say that a neural network has four layers, that includes all the hidden layers in the output layer, but we don't count the input layer. This is a neural network with four layers in the conventional way of counting layers in the network. 

Let's zoom in to layer 3, which is the third and final hidden layer to look at the computations of that layer. Layer 3 inputs a vector $\vec{a}^{[2]}$ that was computed by the previous layer, and it outputs $\vec{a}^{[3]}$, which is another vector. It has three neurons or we call it three hidden units, then it has parameters $\vec{w_1}$, $b_1$, $\vec{w_2}$, $b_2$, and $\vec{w_3}$, $b_3$ and it computes 
$$a_1^{[3]}=g(\vec{w_1}^{[3]}.\vec{a}^{[2]}+b_1^{[3]})$$
$$a_2^{[3]}=g(\vec{w_2}^{[3]}.\vec{a}^{[2]}+b_2^{[3]})$$$$a_3^{[3]}=g(\vec{w_3}^{[3]}.\vec{a}^{[2]}+b_3^{[3]})$$Then the output of this layer is a vector 
$$
\vec{a}^{[3]} =
\begin{bmatrix}
a_1^{[3]} \\
a_2^{[3]} \\
a_3^{[3]}
\end{bmatrix}
$$Just the more general form of this equation for an arbitrary layer 0 and for an arbitrary unit $j$, which is that a activation output of layer $l$
$$a_j^{[l]}=g(\vec{w_j}^{[l]}.\vec{a}^{[l-1]}+b_j^{[l]})$$

- When building neural networks, unit j refers to the $j_th$ neuron, so we use those terms a little bit interchangeably where each unit is a single neuron in the layer. 
- G here is the sigmoid function. In the context of a neural network, g has another name, which is also called the activation function, because g outputs this activation value. 

Just one last piece of notation. In order to make all this notation consistent, I'm also going to give the input vector X and another name which is $\vec{a}^{[0]}$