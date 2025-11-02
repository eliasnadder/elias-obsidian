Sometimes in an application, the algorithm can run into a problem called overfitting, which can cause it to perform poorly.
almost opposite problem called underfitting.

### Example for linear regression
#### Example 1
Predict housing prices
- One thing you could do is fit a linear function to this data.  
$$f(x)=wx+b$$
![[Screenshot 2025-11-01 145629.png]]
- Get a straight line fit to the data. 
- But this isn't a very good model. Looking at the data, it seems pretty clear that as the size of the house increases, the housing process flattened out. ^cc796c
- This algorithm does not fit the training data very well. The technical term for this is the model is **underfitting** the training data. Another term is the algorithm has high [[#^5ab739|bias]].

### Note
>**Bias in technical term**
>the algorithm has underfit the data, meaning that it's just not even able to fit the training set that well. There's a clear pattern in the training data that the algorithm is just unable to capture.

^5ab739

##### Another way to think of this form of bias 
- the learning algorithm has a very strong preconception, or we say a very strong bias, that the housing prices are going to be a completely linear function of the size despite data to the contrary.
- This preconception that the data is linear causes it to fit a straight line that fits the data poorly, leading it to **underfitted** data.

#### Example 2
insert a quadratic function at the data with two features, 
$$w_1x+w_2x^2+b$$
![[Screenshot 2025-11-01 145641.png]]
- get a curve that fits the data somewhat better. 
- Also, if you were to get a new house, that's not in this set of five training examples. This model would probably do quite well on that new house. ^87ad93
- These quadratic models seem to fit the training set not perfectly, but pretty well. I think it would generalize well to new examples.

> The idea that you want your learning algorithm to do well, even on examples that are not on the training set, that's called **generalization**. 
> Technically we say that you want your learning algorithm to generalize well, which means to make good predictions even on brand new examples that it has never seen before.

#### Example 3
 insert a fourth-order polynomial to the data
 $$w_1x+w_2x^2+w_3x^3+w_4x^4+b$$ ^efccc8

![[Screenshot 2025-11-01 145650.png]]

- This seems better because it passes through all of the training data perfectly. 
- In fact, choose parameters that will result in the cost function being exactly equal to zero because the errors are zero on all five training examples. 
- But this is a very wiggly curve, its going up and down all over the place. If you have this whole size right here, the model would predict that this house is cheaper than houses that are smaller than it. We don't think that this is a particularly good model for predicting housing prices. 
- The technical term is that we'll say **this model has overfit the data**, or **this model has an overfitting problem**. Because even though it fits the training set very well, it has fit the data almost too well, hence is overfit.
- It does not look like this model will generalize to new examples that's never seen before. Another term for this is that the algorithm has **high variance**. 

It turns out that if your training set were just even a little bit different, say one holes was priced just a little bit more little bit less, then the function that the algorithm fits could end up being totally different. 

If two different machine learning engineers were to fit this fourth-order polynomial model, to just slightly different datasets, they couldn't end up with totally different predictions or highly variable predictions. That's why we say the algorithm has high variance.

#### Contrasting between this three models
 Contrasting this [[#^efccc8|fourth-order polynomial model]] with the [[#^87ad93|quadratic model]] for the same house, it seems, the quadratic model gives them much more reasonable prediction for price. 
 
 > the goal machine learning is to find a model that hopefully is neither **underfitting** nor **overfitting**. In other words, hopefully, a model that has neither **high bias** nor **high variance**.

#### Recap
- if you have too many features like [[#^efccc8|fourth-order polynomial model]], then the model may fit the training set well, but almost too well or overfit and have high variance. 
- On the flip side if you have too few features, like the [[#^cc796c|first]], it underfits and has high [[#^5ab739|bias]]. 
- In this example, using [[#^87ad93|quadratic]] features $x$ and $x^2$, that seems to be just right. 

### Overfitting in classification 
#### Example 1
Here's a classification example with two features,
$$z=w_1x_1+w_2x_2+b$$
![[Screenshot 2025-11-02 120523.png]]
- where $x_1$ is maybe the tumor size and $x_2$ is the age of patient.
- We're trying to classify if a tumor is malignant or benign, one thing you could do is fit a logistic regression model.
$$f_{\vec{w},b}(\vec{x})=g(z)$$
- It creates a straight line as the decision boundary. This is the line where $z$ is equal to zero that separates the positive and negative examples. 
- This straight line doesn't look terrible. It looks okay, but it doesn't look like a very good fit to the data either. This is an example of **underfitting** or **high bias**

#### Example 2
Add to your features these quadratic terms,
$$z=w_1x_1+w_2x_2+w_3x_1^2+w_4x_2^2+w_5x_1x_2+b$$
![[Screenshot 2025-11-02 120540.png]]
- Look like an ellipse or part of an ellipse. This is a pretty good fit to the data, even though it does not perfectly classify every single training example in the training set.
- Some of these crosses get classified among the circles. But this model looks pretty good. It looks like this **generalized** pretty well to new patients. 

#### Example 3
fit a very high-order polynomial with many features,
$$z=w_1x_1+w_2x_2+w_3x_1^2x_2+w_4x_1^2x_2^2+w_5x_1^2x_2^3++w_6x_1^3x_2+...+b$$
![[Screenshot 2025-11-02 120549.png]]
- then the model may try really hard and contoured or twist itself to find a decision boundary that fits your training data perfectly. 

- Having all these higher-order polynomial features allows the algorithm to choose this really over the complex decision boundary. If the features are tumor size in age, and you're trying to classify tumors as malignant or benign, then this doesn't really look like a very good model for making predictions. 
- This is an instance of **overfitting** and **high variance** because its model, despite doing very well on the training set, doesn't look like it'll generalize well to new examples. 