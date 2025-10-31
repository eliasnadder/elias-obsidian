This [[Simplified Cost function for Logistic regression|equation]] 
$$J(\vec{w},b)=-\frac{1}{m} \sum_{i=0}^{m}[\mathbf{y}^{(i)}log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})) - (1-\mathbf{y}^{(i)})log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))]$$
$w_j=w_j-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}=w_j-\alpha.[\frac{1}{m}\sum_{i=0}^{m}(f_{\vec{w},b}(\vec{x}^{(i)})).x_j^{(i)}]; j=1,2,...,n$
$b=b-\alpha.\frac{\partial J(\vec{w},b)}{\partial w_j}=b-\alpha.[\frac{1}{m}\sum_{i=0}^{m}(f_{\vec{w},b}(\vec{x}^{(i)}))]$
### Some concepts between linear & logistic regression
1. **Monitor gradient descent to make sure it converges**
	You can apply the same method for logistic regression 
2. **Vectorization**
	Use it to make gradient descent runs faster for logistic regression
3. Scaling