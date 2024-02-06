
**What is machine learning?**

*June 2021*


![](https://media3.giphy.com/media/hWRpUTECph34EvMzO6/giphy.gif)
Ridiculously powerful human-like machines have captured our collective imagination for long.

So let’s get the formal definition out of the way.

“Machine Learning is the art of getting computers to learn without being explicitly programmed” - Arthur Samuel (1958)
![](https://media3.giphy.com/media/26tP4gFBQewkLnMv6/giphy.gif)
The art of what, again?

If you read the definition above, the part about not explicitly programming the computer is what distinguishes machine learning from traditional programming. In traditional programming, a computer takes data and a program, i.e. an explicit set of instructions, as input and generates an output.
![picture](uploads/1d.png)

On the other hand, in machine learning, a combination of data and the output is used to make the machine learn the program:
![picture](uploads/1a.png)
Note that one thing didn’t change. The *data* is still an input in both cases.
![](https://media0.giphy.com/media/xT9C25UNTwfZuk85WP/giphy.gif)
But how is machine learning performed? For example, how can we make a computer learn to identify that an image contains a cat?
![](https://media3.giphy.com/media/iPj5oRtJzQGxwzuCKV/giphy.gif)

This is harder than it sounds. Human beings are very good at doing this sort of pattern recognition. But to a computer, an RGB image of a cat is just a bunch of pixels. An extremely unique combination of pixels results in an image of a cat. An effective machine learning algorithm needs to be able to automatically identify what are the combinations and patterns of pixels, that when put together, result in a cat appearing in an image.
![](uploads/1c.png)


It’s not trivial for a computer to learn that a bunch of pixels correspond to an image of a cat.
How would you go about teaching such a thing to a computer? Well, there are three components of learning: **Representation, Evaluation, and Optimization**. 

![](uploads/1b.png)
*Any machine/deep learning algorithm* you encounter will contain the above three components. So let’s take it step by step. What do we mean by Representation:

![](uploads/1e.png)
Representation is the heart of any machine learning algorithm. A learner must be represented in some formal language the computer can handle. In practice, this formal language is a mathematical model that takes some input data, performs a computation on it, and returns an output. Neural Networks, Gaussian Processes, Support Vector Machines, and Decision Trees are all examples of representation.

Having a representation is not enough though. All mathematical models have parameters that can change in value. Parameters are just variable values in the model that need to be adjusted for the task to be performed correctly. For example, the tuner knob on your car radio represents a parameter that can be tuned:

The value of the parameters of a model will change depending on the problem being solved. For the radio analogy above, you can imagine that you need to tune the knob to different amounts depending on which channel you want to hear. Therefore, you need a mechanism or a method to identify which set of values for the parameters of the model will result in a learning algorithm that effectively performs the task at hand, e.g. learning whether an image contains a cat or not. In other words, we need an objective function that can distinguish good solutions from bad ones. This is what the evaluation component of our learning engine does. Mean Squared Error, which is an average of the square of the error between the actual output and the machine learning engine prediction, is an example of such an objective function.

Finally, once you have a representation, i.e. some mathematical model, and an evaluation method to identify which parameters might be good choices, you need to be able to search for the set of parameters that lead to the optimal result, i.e. the smallest error between actual output and the machine learning prediction. This is where the Optimization component comes in handy: 

Optimization is a method to search for the best solution. There are many different optimization methods, some depend on computing the gradient or slope of a function, while other approaches such as Genetic Algorithms, take inspiration from how nature identifies the best solutions.

Learning involves finding the optimal parameters that maximize an objective function (e.g. Mean Squared Error) given a certain representation (e.g. Neural Networks) with varying parameters and a set of data (e.g. Dataset containing images with and without cats together with labels of whether the respective image contains a cat) to train the algorithm over.

Hope your learning algorithm manages to tune the parameters just right, so you can enjoy the result!

*Take me [home](https://sameeurrehman.com/)* 