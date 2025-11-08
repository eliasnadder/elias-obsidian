We'll use examples from demand prediction in which you look at the product and try to predict, will this product be a **top seller** or **not**?

### Example 1
 In this example, you're selling t-shirts and you would like to know if a particular t-shirt will be a top seller.
 - You have collected data of different t-shirts that were sold at different prices, as well as which ones became a top seller. 
 - This type of application is used by retailers today in order to plan better inventory levels as well as marketing campaigns. If you know what's likely to be a top seller, you would plan to just purchase more of that stock in advance. 

![[Screenshot 2025-11-04 225339.png]]
In this example, the input feature x is the price of the T-shirt, and so that's the input to the learning algorithm. 
$$x=price$$
If you apply logistic regression to fit a sigmoid function to the data, then the outputs of your prediction:
$$\frac{1}{1+e^{-(w.x+b)}}$$
![[Screenshot 2025-11-04 225705.png]]

Previously, we had written this as
$$f(x)=\frac{1}{1+e^{-(w.x+b)}}$$
the output of the learning algorithm. 
In order to set up to build a neural network, use the alphabet $a$ to denote the output of this logistic regression algorithm. 
$$a=f(x)=\frac{1}{1+e^{-(w.x+b)}}$$
- The term $a$ stands for activation, and it's actually a term from neuroscience, and it refers to how much a neuron is sending a high output to other neurons downstream from it. 
- It turns out that this logistic regression units or this little logistic regression algorithm, can be thought of as a very simplified model of a single neuron in the brain. 
	- Where what the neuron does is it takes us input the price $x$ 
	- Then it computes this formula on top, and it outputs the number $a$, and it outputs the probability of this t-shirt being a top seller. 
#### Note
> Another way to think of a neuron is as a tiny little computer whose only job is to input one number or a few numbers, such as a price, and then to output one number or maybe a few other numbers which in this case is the probability of the t-shirt being a top seller. 

Given this description of a single neuron, building a neural network now it just requires taking a bunch of these neurons and wiring them together or putting them together. 

### Example 2 (Multiple features)
The features are the price of the t-shirt, the shipping costs, the amounts of marketing of that particular t-shirt, as well as the material quality, is this a high-quality, thick cotton versus maybe a lower quality material

Maybe suspect that whether or not a t-shirt becomes a top seller actually depends on a few factors. 
- First, one is the affordability of this t-shirt. 
- Second is, what's the degree of awareness of this t-shirt that potential buyers have? 
- Third is perceived quality to bias or potential bias saying this is a high-quality t-shirt. 

What I'm going to do is create artificial neurons to try to estimate: 
- **The probability that this t-shirt is perceive as highly affordable.** 
	- Affordability is mainly a function of price and shipping costs because the total amount of the pay is some of the price plus the shipping costs. 
	- Create a little neuron, a logistic regression unit to input price and shipping costs and predict do people think this is affordable? 

- **Is there high awareness of this?** 
	- Awareness in this case is mainly a function of the marketing of the t-shirt. 

- **Do people perceive this to be of high quality**
	- may mainly be a function of the price of the t-shirt and of the material quality. 
	- Price is a factor here because fortunately or unfortunately, if there's a very high priced t-shirt, people will sometimes perceive that to be of high quality because it is very expensive than maybe people think it's going to be of high-quality. 

Given these estimates of affordability, awareness, and perceived quality. Then wire the outputs of these three neurons to another neuron, that then there's another logistic regression unit. That finally inputs those three numbers and outputs the probability of this t-shirt being a top seller. 

In the terminology of neural networks, group these three neurons together into what's called a **layer**. 
### Layer 

![[Screenshot 2025-11-04 233059.png]]
is a grouping of neurons which takes as input the same or similar features, and that in turn outputs a few numbers together. 
- These three neurons form one layer. 
- A layer can have multiple neurons or it can also have a single neuron.
- The output layer outputs the probability predicted of the neural network. 

In the terminology of neural networks we're also going to call affordability, awareness and perceive quality to be **activations**. 
These numbers on affordability, awareness, and perceived quality are the activations of these three neurons in this layer, and also this output probability is the activation of the output neuron. 

This particular neural network therefore carries out computations as follows:. 
1. It inputs four numbers 
2. then this layer of the neural network uses those four numbers to compute the new numbers also called **activation values**. 
3. Then the final layer, the output layer of the neural network used those three numbers to compute one number. 
### Note
> In a neural network this list of four numbers is also called the **input layer**, and that's just a list of four numbers. 

### Choose the input of the neurons

![[Screenshot 2025-11-04 233059.png]]
We had to go through the neurons one at a time and decide what inputs it would take from the previous layer. For example, we said affordability is a function of just price and shipping costs and awareness is a function of just marketing and so on, but if you're building a large neural network it'd be a lot of work to go through and manually decide which neurons should take which features as inputs. 
The way a neural network is implemented in practice each neuron in a certain layer, will have access to every feature, to every value from the previous layer, from the input layer. 

![[Screenshot 2025-11-04 234052.png]]
You can imagine that if you're trying to predict affordability and it knows what's the price shipping cost marketing and material, maybe you'll learn to ignore marketing and material and just figure out through setting the parameters appropriately to only focus on the subset of features that are most relevant to affordability. 

### Vector for the inputs & activation values
- Take these four input features and write them as a vector $\vec{x}$, 
	- and view the neural network as having four features that comprise this feature vector $\vec{x}$. 
- This feature vector is fed to this layer in the middle which then computes three activation values. 
	- That is these numbers and these three activation values in turn becomes another vector which is fed to this final output layer that finally outputs the probability of this t-shirt to being a top seller. 

That's all a neural network is. It has a few layers where each layer inputs a vector and outputs another vector of numbers. 
- For example, this layer in the middle inputs four numbers x and outputs three numbers corresponding to affordability, awareness, and perceived quality. 

### Note
> To give the layer in the middle a name as well, this layer in the middle is called a hidden layer. That terminology comes from that's when you have a training set. In a training set, you get to observe both x and y. 
> Your data set tells you what is x and what is y, and so you get data that tells you what are the correct inputs and the correct outputs. But your dataset doesn't tell you what are the correct values for affordability, awareness, and perceived quality. 
> The correct values for those are hidden. You don't see them in the training set, which is why this layer in the middle is called a hidden layer. 

### Another way of thinking about neural networks

![[Screenshot 2025-11-04 235535.png]]
- is a logistic regression algorithm or logistic regression unit that is taking as input, affordability, awareness, and perceived quality of a t-shirt.
- And use these three features to estimate the probability of the t-shirt being a top seller. This is just logistic regression. 
- But the cool thing about this is rather than using the original features, price, shipping cost, marketing, and so on, is using maybe better set of features, affordability, awareness, and perceived quality, that are hopefully more predictive of whether or not this t-shirt will be a top seller. 

### Neural as logistic regression
One way to think of this neural network is, just logistic regression. But as a version of logistic regression, they can learn its own features that makes it easier to make accurate predictions. 
- In fact, the housing example. If you want to predict the price of the house, you might take the frontage or the width of lots and multiply that by the depth, which was the size of the lawn. There we were doing manual feature engineering where we had to look at the features $x_1$ and $x_2$ and decide by hand how to combine them together to come up with better features. 

- What the neural network does is instead of you needing to manually engineer the features, it can learn its own features to make the learning problem easier for itself. 
- This is what makes neural networks one of the most powerful learning algorithms in the world today. 
#### Summarize
1. the input layer has a vector of features, four numbers in this example, it is input to the hidden layer, which outputs three numbers. 
2. Then the output layer takes its input to three numbers and outputs one number, which would be the final activation, or the final prediction of the neural network. 

#### Note
> One of the really nice properties of a neural network is when you train it from data, you don't need to go in to explicitly decide what other features, such as affordability and so on, that the neural network should compute instead or figure out all by itself what are the features it wants to use in this hidden layer. That's what makes it such a powerful learning algorithm. 

### Number of hidden layers (Multilayer perceptron)
The neural network can contain multiple hidden layers, maybe one, two, or three and so on.

- When you're building your own neural network, one of the decisions you need to make is how many hidden layers do you want and how many neurons do you want each hidden layer to have. This question of how many hidden layers and how many neurons per hidden layer is a question of the architecture of the neural network. 

- But choosing the right number of hidden layers and number of hidden units per layer can have an impact on the performance of a learning algorithm as well. 

- By the way, in some of the literature, you see this type of neural network with multiple layers like this called a **multilayer perceptron**. If you see that, that just refers to a neural network that looks like what you're seeing here on the slide. 
