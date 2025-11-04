## A- Collect more training examples
fit a model and it has high variance, is overfit. For example, [[1- The problem of overfitting|overfit house price prediction model]]. 

![[Screenshot 2025-11-02 153217.png]]

- To address this problem is to collect more training data. If you're able to get more data, that is more training examples on sizes and prices of houses, then with the larger training set, the learning algorithm will learn to fit a function that is less wiggly.
- Fit a high order polynomial or some of the function with a lot of features.

### Note
> Getting more data isn't always an option. Maybe only so many houses have been sold in this location, so maybe there just isn't more data to be add. But when the data is available, this can work really well.

## B- Select features to include / exclude
a lot of different features of a house of which to try to predict its price, ranging from the size, number of bedrooms, number of floors, the age, average income of the neighborhood, and so on and so forth, total distance to the nearest coffee shop. 
- It turns out that if you have a lot of features like these but don't have enough training data, then your learning algorithm may also overfit to your training set. 
- Instead of using all 100 features, if we were to pick just a subset of the most useful ones, maybe size, bedrooms, and the age of the house. If you think those are the most relevant features, then using just that smallest subset of features, you may find that your model no longer overfits as badly.

> Use your intuition to choose what you think is the best set of features, what's most relevant for predicting the price.

### Disadvantage 
>  the algorithm is throwing away some of the information that you have about the houses. For example, maybe all of these features, all 100 of them are actually useful for predicting the price of a house. Maybe you don't want to throw away some of the information..

## C- Regularization
look at an overfit model,
$$f(x)=28x-385x^2+39x^3-17x^4+100$$
![[Screenshot 2025-11-02 142352.png]]
If you were to eliminate some of these features, if you were to eliminate the feature $x^4$, that corresponds to setting this parameter to 0.
- But the regularization is a way to more gently reduce the impacts of some of the features without doing something as harsh as eliminating it outright.
- It is encourage the learning algorithm to shrink the values of the parameters without necessarily demanding that the parameter is set to exactly 0. 
- Lets you keep all of your features, but they just prevents the features from having an overly large effect, which is what sometimes can cause overfitting.
 - Just reduce the size of the $w_j$ parameters, that is $w_1$ through $w_n$. You will get a curve that ends up fitting the training data much better. 
$$f(x)=13x-0.23x^2+0.000014x^3-0.001x^4+10$$
![[Screenshot 2025-11-02 142404.png]]
#### Note
> It doesn't make a huge difference whether you regularize the parameter b as well. In practice, it should make very little difference whether you also regularize b or not. 

## Recap 
these are the three ways for addressing overfitting. 
1. **Collect more data**. 
	If you can get more data, this can really help reduce overfitting. Sometimes that's not possible.
2. **Selecting and using only a subset of the features**. 
3. **Regularization**
	Reduce the size of the parameters using 
