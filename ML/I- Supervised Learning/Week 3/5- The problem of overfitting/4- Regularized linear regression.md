How to get gradient descent to work with regularized linear regression.
[[3- Cost function with regularization]]
$$min_{\vec{w},b}J(\vec{w},b)=min_{\vec{w},b}[\frac{1}{2m}\sum_{i=1}^{m}(f_{\vec{w},b}(\vec{x})-y^{(i)})^2+\frac{\lambda}{2m}\sum_{j=1}^{n}w_j^2]$$

Previously, we had the following gradient descent algorithm, which is that we repeatedly update the parameters $w_j$, and b.

Gradient descent {
$w_j=w_j-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}=w_j-\alpha.[\frac{1}{m}\sum_{i=0}^{m}[f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)}].x_j^{(i)}]; j=1,2,...,n$
$b=b-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}=b-\alpha.[\frac{1}{m}\sum_{i=0}^{m}(f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)})]$
} simultaneous update

We've added this additional regularization term, the only thing that changes is that the expression for the derivative with respect to $w_j$ ends up with one additional term
$$\frac{\partial J(\vec{w},b)}{\partial w_j}=\frac{1}{m}\sum_{i=0}^{m}[f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)}].x_j^{(i)}+\frac{\lambda}{m}w_j$$
> We don't regularize `b`, so we're not trying to shrink B. That's why the updated `b` remains the same as before

$w_j=w_j-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}=w_j-\alpha.[\frac{1}{m}\sum_{i=0}^{m}[f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)}].x_j^{(i)}+\frac{\lambda}{m}w_j]; j=1,2,...,n$
$b=b-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}=b-\alpha.[\frac{1}{m}\sum_{i=0}^{m}(f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)}))]$

#### Update rule for $w_j$ and rewrite it in another way
$$w_j=1.w_j-\alpha.\frac{\lambda}{m}.w_j-\alpha.[\frac{1}{m}\sum_{i=0}^{m}[f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)}].x_j^{(i)}]$$
then $w_j$ updated as
$$w_j.(1-\alpha.\frac{\lambda}{m})$$
the second term as the usual gradient descent update for unregularized linear regression
$$-\alpha.[\frac{1}{m}\sum_{i=0}^{m}[f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)}].x_j^{(i)}]$$
$\alpha$ is a very small positive number, say 0.01. $\lambda$ is usually a small number, say 1 and m is the training set size, say 50.
$\alpha=0.01$
$\lambda=1$
$m=50$
$$1-\alpha.\frac{\lambda}{m}=1-0.01*\frac{1}{50}=1-0.0002=0.9998$$on every single iteration is you're multiplying $w$ by a number slightly less than 1, and that has effect of shrinking the value of $w_j$ just a little bit.