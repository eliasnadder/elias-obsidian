The softmax regression algorithm is a generalization of logistic regression, which is a binary classification algorithm to the multiclass classification contexts. 

Recall that logistic regression applies when y can take on two possible output values, either zero or one, and the way it computes this output is, you would first calculate z 
$$z=\vec{w}.\vec{x}+b$$
and then you would compute what I'm going to call here $a$ 
$$a=g(z)=P(y=1|\vec{x})$$
We interpreted this as logistic regressions estimates of the probability of y being equal to 1 given those input features x. 

To embellish logistic regression a little bit in order to set up for the generalization to softmax regression, think of logistic regression as actually computing two numbers:
- $a_1=g(z)=P(y=1|\vec{x})$ 
- $a_2=1-a_1=P(y=0|\vec{x})$

Let's now generalize this to softmax regression, do this with a concrete example of when y can take on four possible outputs, so y can take on the values 1, 2, 3 or 4. 
Here's what softmax regression will do, 
1- It will compute $z_1$, $z_2$, $z_3$ and $z_4$. 
$z_1=\vec{w_1}.\vec{x}+b_1$
$z_2=\vec{w_2}.\vec{x}+b_2$
$z_3=\vec{w_3}.\vec{x}+b_3$
$z_4=\vec{w_4}.\vec{x}+b_4$
> [!SUCCESS] Note
> Here, $w_1$, $w_2$, $w_3$, $w_4$ as well as $b_1$, $b_2$, $b_3$, $b_4$, these are the parameters of softmax regression. 

2- The formula for softmax regression, 
$$a_1=\frac{e^{z_1}}{e^{z_1}+e^{z_2}+e^{z_3}+e^{z_4}}=P(y=1|\vec{x})$$
$$a_2=\frac{e^{z_2}}{e^{z_1}+e^{z_2}+e^{z_3}+e^{z_4}}=P(y=2|\vec{x})$$
$$a_3=\frac{e^{z_3}}{e^{z_1}+e^{z_2}+e^{z_3}+e^{z_4}}=P(y=3|\vec{x})$$
$$a_4=\frac{e^{z_4}}{e^{z_1}+e^{z_2}+e^{z_3}+e^{z_4}}=P(y=4|\vec{x})$$
Whereas on the left, we wrote down the specification for the logistic regression model, these equations on the right are our specification for the softmax regression model. It has parameters $w_1$ through $w_4$, and $b_1$ through $b_4$, and if you can learn appropriate choices to all these parameters, then this gives you a way of predicting what's the chance of y being 1, 2, 3 or 4, given a set of input features x. 

In the general case, y can take on n possible values. In that case, softmax regression will compute to $z_j=\vec{w_j}.\vec{x}+b_j$,
where now the parameters of softmax regression are $w_1, w_2, ..., w_n$ , as well as $b_1, b_2 ..., b_n$. Then finally, we'll compute 
$$a_j=\frac{e^{z_j}}{\sum_{k=1}^Ne^{z_k}}=P(x=j|\vec{x})$$
Notice that by construction that this formula, if you add up a1, a2 all the way through a n, these numbers always will end up adding up to 1. $a_1+a_2+...+a_n=1$

> [!WARNING] Notice
> Softmax regression with $n=2$, so there are only two possible output classes then softmax regression ends up computing basically the same thing as logistic regression. The parameters end up being a little bit different, but it ends up reducing to logistic regression model. But that's why the softmax regression model is the generalization of logistic regression. 

## The cost function for softmax regression
Recall for logistic regression, 
$z=\vec{w}.\vec{x}+b$
$a_1=g(z)=P(y=1|\vec{x})$
$a_2=1-a_1$
Previously, the loss of logistic regression 
$$loss = -y.log(a_1) - (1-y).log(1-a_1)$$
But $a_2=1-a_1$. In other words, the loss if $y=1$ is negative $log(a1)$. If $y=0$, then the loss is negative $log(a2)$, and then same as before the cost function for all the parameters in the model is the average loss, average over the entire training set. 

The loss for softmax regression 
$$a_1=\frac{e^{z_1}}{\sum_{k=1}^Ne^{z_K}}=P(x=1|\vec{x})$$
$$a_N=\frac{e^{z_N}}{\sum_{k=1}^Ne^{z_k}}=P(x=j|\vec{x})$$
$$
L(a_1, a_2, ..., a_N,y) =
\begin{cases}
- \log(a_1), & \text{if } y = 1 \\
- \log(a_2), & \text{if } y = 2 \\
. \\
. \\
. \\
- \log(a_N), & \text{if } y = N \\
\end{cases}
$$
If $y=j$, then the $loss=-log(a_j)$. 
Negative log of a j is a curve that looks like this. 
- a j was very close to 1, then you beyond this part of the curve and the loss will be very small. 
- a j had only a 50% chance then the loss gets a little bit bigger. 
- a j is, the bigger the loss. 
This incentivizes the algorithm to make a j as large as possible, as close to 1 as possible. Because whatever the actual value y was, you want the algorithm to say hopefully that the chance of y being that value was pretty large. Notice that in this loss function, y in each training example can take on only one value.