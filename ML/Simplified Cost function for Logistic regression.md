#### $$
L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) =
\begin{cases}
- \log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})), & \text{if } y^{(i)} = 1 \\
- \log(1 - f_{\mathbf{w},b}(\mathbf{x}^{(i)})), & \text{if } y^{(i)} = 0
\end{cases}
$$
Given a predication  $f_{\mathbf{w},b}(\mathbf{x}^{(i)})$ and the target $\mathbf{y}^{(i)}$ 
### $$L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) = -\mathbf{y}^{(i)}log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})) - (1-\mathbf{y}^{(i)})log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))$$
- Completely equivalent to this more complex formula up here

## Why?? 
- y can only take 0 or 1
> In the first case, when $y=1$ 
- $L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) = -1.log(f_{\mathbf{w},b}(\mathbf{x}^{(i)}))=-log(f_{\mathbf{w},b}(\mathbf{x}^{(i)}))$ 
> In second case, when $y=0$  
-  $L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) = -1.log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))=-log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))$ 

## Cost function 
$$J(\vec{w},b)=\frac{1}{m} \sum_{i=0}^{m}L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)})$$$$J(\vec{w},b)=-\frac{1}{m} \sum_{i=0}^{m}[\mathbf{y}^{(i)}log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})) - (1-\mathbf{y}^{(i)})log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))]$$