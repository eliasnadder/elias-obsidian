The demand prediction example where given price, shipping cost, marketing, material, you would try to predict if something is highly affordable. If there's good awareness and high perceived quality and based on that try to predict it was a top seller. 
But this assumes that awareness is maybe binary is either people are aware or they are not. But it seems like the degree to which possible buyers are aware of the t shirt you're selling may not be binary, they can be a little bit aware.

So rather than modeling awareness as a binary number 0, 1, that you try to estimate the probability of awareness or rather than modeling awareness is just a number between 0 and 1. Maybe awareness should be any non negative number. 

## ReLU function
Previously, this equation is used to calculate the activation of that second hidden unit estimating awareness where g was the sigmoid function and just goes between 0 and 1. 
$$a_2^{[1]}=g(\vec{w_2}^{[1]}.\vec{x}+b_2^{[1]})$$
If you want to allow $a_2^{[1]}$ to potentially take on much larger positive values, we can instead swap in a different activation function. It turns out that a very common choice of activation function in neural networks is this function. It looks like this. 

![[Screenshot 2025-12-13 165758.png]]
- If $z<0$, then $g(z) = 0$ to the left and then there's this straight line 45° to the right of 0. 
- And so when $z>= 0$, $g(z)=z$. That is to the right half of this diagram. 
And the mathematical equation for this is 
$$g(z)=max(0,z)$$
And if $a_2^{[1]}$ is g(z) for this value of z, then the deactivation value cannot take on 0 or any non negative value. This activation function has a name. 

More generally you have a choice of what to use for g(z) and sometimes we'll use a different choice than the sigmoid activation function.

## Examples of Activation Functions
![[Screenshot 2025-12-13 170527.png]]
> [!WARNING]
> The linear activation function, people will say we're not using any activation function because if $a = g(z)$ where $g(z)=z$, then a is just equal to this $w.x+b$.
