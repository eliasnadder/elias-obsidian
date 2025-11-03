We saw that logistic regression can be prone to overfitting if you fit it with [[1- The problem of overfitting|very high order polynomial features]]
$$z=w_1x_1+w_2x_2+w_3x_1^2x_2+w_4x_1^2x_2^2+w_5x_1^2x_2^3++w_6x_1^3x_2+...+b$$
![[Screenshot 2025-11-02 120549.png]]

This was the [[1- Simplified Cost function for Logistic regression|cost function]] for logistic regression.
$$J(\vec{w},b)=-\frac{1}{m} \sum_{i=0}^{m}[\mathbf{y}^{(i)}log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})) - (1-\mathbf{y}^{(i)})log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))]$$
If you want to modify it to use regularization, all you need to do is add to it the following term 
$$J(\vec{w},b)=-\frac{1}{m} \sum_{i=0}^{m}[\mathbf{y}^{(i)}log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})) - (1-\mathbf{y}^{(i)})log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))]+\frac{\lambda}{2m}\sum_{j=1}^{n}w_j^2$$
- When you minimize this cost function as a function of w and b, it has the effect of penalizing parameters $w_1, w_2, ..., w_n$, and preventing them from being too large.
- If you do this, then even though you're fitting a high order polynomial with a lot of parameters, you still get a decision boundary that looks like this.  Something that looks more reasonable for separating positive and negative examples while also generalizing hopefully to new examples not in the training set. 

### How can you actually implement this?  & How can you actually minimize this cost function $j(\vec{w}, b)$ that includes the regularization term?

To minimize, implement gradient descent, as before, we'll carry out the following simultaneous updates over $w_j$ and $b$. 
$$w_j=w_j-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}=w_j-\alpha.[\frac{1}{m}\sum_{i=0}^{m}[f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)}].x_j^{(i)}+\frac{\lambda}{m}w_j]; j=1,2,...,n$$
$$b=b-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}=b-\alpha.[\frac{1}{m}\sum_{i=0}^{m}(f_{\vec{w},b}(\vec{x}^{(i)})-y^{(i)}))]$$
- In fact is the exact same equation, except for the fact that the definition of f is now no longer the linear function, it is the logistic function applied to z. 
- Similar to linear regression, we will regularize only the parameters w, j, but not the parameter b, which is why there's no change the update you will make for b.
