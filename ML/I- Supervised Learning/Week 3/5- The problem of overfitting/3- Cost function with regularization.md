Suppose that you had a way to make the parameters $w_3$ and $w_4$ really small. Say close to 0.
$$w_1x_+w_2x^2+w_3x^3w_4x^4+b$$
Instead of minimizing this objective function, this is a cost function for linear regression. Let's say you were to modify the cost function and add to it $1000.w_3^2+1000.w_4^2$ : 
$$min_{w,b}\frac{1}{2m}\sum_{i=1}^{m}(f_{\vec{w},b}(\vec{x})-y^{(i)})^2+1000w_3^2+1000w_4^2$$
- So with this modified cost function, you could in fact be penalizing the model if $w_3$ and $w_4$ are large. 
- If you want to minimize this function, the only way to make this new cost function small is if $w_3$ and $w_4$ are both small, Because otherwise this $1000.w_3^2$ and $1000.w_4^2$ terms are going to be really big. So when you minimize this function, you're going to end up with $w_3$ close to 0 and $w_4$ close to 0. 

- So we're effectively nearly canceling out the effects of the features execute and extra power of 4 and getting rid of these two terms over here. And if we do that, then we end up with a fit to the data that's much closer to the quadratic function, including maybe just tiny contributions from the features x cubed and extra 4.

### The idea behind regularization. 
- The idea is that if there are smaller values for the parameters, then that's a bit like having a simpler model. Maybe one with fewer features, which is therefore less prone to overfitting. 

- Previously we **penalize** or we say we **regularized** only $w_3$ and $w_4$. But more generally, the way that regularization tends to be implemented is if you have a lot of features, say a 100 features, you may not know which are the most important features and which ones to penalize. 

- So the way regularization is typically implemented is to penalize all of the features or more precisely, you penalize all the $w_j$ parameters and it's possible to show that this will usually result in fitting a smoother simpler, less weekly function that's less prone to overfitting. 

So let's build a model that uses all 100 features. So you have these 100 parameters $w_1, w_2, w_3, ..., w_{100}, b$. 
- Let's penalize all of them a bit and shrink all of them by adding this new term :

$$J(\vec{w},b)=\frac{1}{2m}\sum_{i=1}^{m}(f_{\vec{w},b}(\vec{x})-y^{(i)})^2+\frac{\lambda}{2m}\sum_{j=1}^{n}w_j^2$$
- This lambda $\lambda$ called a **regularization parameter**. So similar to picking a learning rate $\alpha$, you now also have to choose a number for lambda. 

|                                  First term                                   |               Second term               |
| :---------------------------------------------------------------------------: | :-------------------------------------: |
| $min_{\vec{w},b}\frac{1}{2m}\sum_{i=1}^{m}(f_{\vec{w},b}(\vec{x})-y^{(i)})^2$ | $\frac{\lambda}{2m}\sum_{j=1}^{n}w_j^2$ |
### Note 
> **A couple of things I would like to point out by convention:** 
> 1. **Instead of using lambda times the sum of $w_j^2$. We also divide lambda by $2.m$ so that both the 1st and 2nd terms here are scaled by $\frac{1}{2m}$.** 
> 	It turns out that by scaling both terms the same way it becomes a little bit easier to choose a good value for lambda. And in particular you find that even if your training set size growth, say you find more training examples. So m the training set size is now bigger. 
> 
> 2. **We're not going to penalize the parameter b for being large.** 
> 	In practice, it makes very little difference whether you do or not. And some machine learning engineers and actually some learning algorithm implementations will also include
$$J(\vec{w},b)=\frac{1}{2m}\sum_{i=1}^{m}(f_{\vec{w},b}(\vec{x})-y^{(i)})^2+\frac{\lambda}{2m}\sum_{j=1}^{n}w_j^2+\frac{\lambda}{2m}b^2$$
 
So to summarize in this modified cost function, we want to minimize the original cost, which is the mean squared error cost plus additionally, the second term which is called the regularization term. 

#### And so this new cost function trades off two goals: 
1. Trying to minimize this first term encourages the algorithm to fit the training data well by minimizing the squared differences of the predictions and the actual values. 
2. And try to minimize the second term. The algorithm also tries to keep the parameters $w_j$ small, which will tend to reduce overfitting. 

> The value of $\lambda$ that you choose, specifies the relative importance or the relative trade off or how you balance between these two goals. 

### Choosing $\lambda$
Let's take a look at what different values of lambda will cause you're learning algorithm to do. Let's use the housing price prediction example using linear regression. 
$$f_{\vec{w},b}(\vec{x})=w_1x+w_2x^2+w_3x^3+w_4x^4+b$$
#### If $\lambda=0$
then you're not using the regularization term at all because the regularization term is multiplied by 0. And so if lambda was 0, you end up fitting this overly wiggly curve and it overfits.

#### If $\lambda$ to be a really large number, for example $\lambda=10^{10}$,
- then you're placing a very heavy weight on this regularization term on the right. And the only way to minimize this is to be sure that all the values of $w_j$ are pretty much very close to 0. 
- The learning algorithm will choose $w_1$, $w_2$, $w_3$ and $w_4$ to be extremely close to 0 and thus $f(x)=b$ and so the learning algorithm fits a horizontal straight line and **underfits**. 

### Recap 
If $\lambda=0$ this model will overfit and If $\lambda$ is enormous like $10^{10}$ This model will underfit. And so what you want is some value of lambda that is in between that more appropriately balances these first and second terms of trading off, minimizing the mean squared error and keeping the parameters small. 