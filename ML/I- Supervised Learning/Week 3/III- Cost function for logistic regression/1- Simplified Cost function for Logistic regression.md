#### $$
L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) =
\begin{cases}
- \log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})), & \text{if } y^{(i)} = 1 \\
- \log(1 - f_{\mathbf{w},b}(\mathbf{x}^{(i)})), & \text{if } y^{(i)} = 0
\end{cases}
$$
Given a predication  $f_{\mathbf{w},b}(\mathbf{x}^{(i)})$ and the target $\mathbf{y}^{(i)}$ 
### $$L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) = -\mathbf{y}^{(i)}log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})) - (1-\mathbf{y}^{(i)})log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))$$

^30d476

- Completely equivalent to this more complex formula up here

## Why?? 
- y can only take 0 or 1
> In the first case, when $y=1$ [[#^30d476|This equation]]
- $L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) = -1.log(f_{\mathbf{w},b}(\mathbf{x}^{(i)}))=-log(f_{\mathbf{w},b}(\mathbf{x}^{(i)}))$ 
> In second case, when $y=0$  [[#^30d476|This equation]] 
-  $L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) = -1.log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))=-log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))$ 

## Cost function 
$$J(\vec{w},b)=\frac{1}{m} \sum_{i=0}^{m}L(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)})$$
After adjusting [[#^30d476|this equation]] in cost function:
$$J(\vec{w},b)=-\frac{1}{m} \sum_{i=0}^{m}[\mathbf{y}^{(i)}log(f_{\mathbf{w},b}(\mathbf{x}^{(i)})) - (1-\mathbf{y}^{(i)})log(1-f_{\mathbf{w},b}(\mathbf{x}^{(i)}))]$$
