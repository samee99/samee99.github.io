What exactly is machine learning and what would the ultimate learning machine look like?


Ridiculously powerful human-like machines have captured our collective imagination for long. 
So let’s get the formal definition out of the way.

“Machine Learning is the art of getting computers to learn without being explicitly programmed”

Arthur Samuel (1958)

The art of what, again?

If you read the definition above, the part about not explicitly programming the computer is what really distinguishes machine learning from traditional programming. In traditional programming, a computer take data and a program, i.e. an explicit set of instructions, as input and generates an output.


On the other hand, in machine learning, a combination of data and the output is used to make the machine learn the program:


Note that one thing didn’t change. The data is still an input in both cases.


But how is machine learning actually performed? For example, how can we make a computer learn to identify that an image contains a cat.


This is harder than it sounds. Human beings are very good at doing this sort of pattern recognition. But to a computer an RGB image of a cat is just a bunch of pixels. An extremely unique combination of pixels results in an image of a cat. And an effective machine learning algorithm needs to be able to automatically identify what are the combinations and patterns of pixels, that when put together, results in a cat appearing in an image.


It’s not trivial for a computer to learn that a bunch of pixels correspond to an image of a cat.
How would you would go about teaching such a thing to a computer? Well, there are three components of learning:


Any machine/deep learning algorithm you come across will contain the above three components. This point is definitely worth repeating, any learning engine will contain the above three parts. So let’s take it step by step. What do we mean by representation:


Representation is the heart of any machine learning algorithm. A learner must be represented in some formal language the computer can handle. In practice, this formal language is basically some mathematical model that takes some input data, performs a computation on it, and returns an output. Neural Networks, Gaussian Processes, Support Vector Machines and Decision Trees are all examples of representation.

Having a representation is not enough though. All mathematical models have parameters that can change in value. Parameters are just variable values in the model that need to be adjusted for the task to be performed correctly. For example, the tuner knob on your car radio represents a parameter that can be tuned:


The value of the parameters of a model will change depending on the problem being solved. For the radio analogy above, you can imagine that you need to tune the knob different amounts depending on which channel you want to hear. Therefore, you need a mechanism or a method to identify which set of values for the parameters of the model will result in a learning algorithm that effectively performs the task at hand, e.g. learning whether an image contains a cat or not. In other words, we need an objective function that can distinguish good solutions from bad ones. This is what the evaluation component of our learning engine does:


Mean Squared Error, which is basically an average of the square of the error between the actual output and the machine learning engine prediction, is an example of such an objective function.

Finally, once you have a representation, i.e. some mathematical model, and and an evaluation method to identify which parameters might be good choices, you need to be able to search for the set of parameters that lead to the optimal result, i.e. the smallest error between actual output and the machine learning prediction. This is where the Optimization component comes in handy:


Optimization is basically a method to search for the best solution. There are many different optimization methods, some depend on computing the gradient or slope of a function, while other approaches such as Genetic Algorithms, take inspiration from how nature identifies the best solutions.

If we put all of the components together, we can write out the complete learning problem as the below optimization problem:


In other words, learning involves finding the optimal parameters, theta_star, that maximize a certain goodness function (e.g. Mean Squared Error) given a certain representation (e.g. Neural Networks) with varying parameters, theta, and a set of data (e.g. Dataset containing images with and without cats together with labels of whether the respective image contains a cat) to train the algorithm over.

Hope your learning algorithm manages to tune the parameters just right, so you can enjoy the end result!


Or you can go ahead and learn about the different types of machine learning approaches.

References

Pedro Domingos. 2012. A few useful things to know about machine learning. Commun. ACM 55, 10 (October 2012), 78–87. DOI:https://doi.org/10.1145/2347736.2347755
