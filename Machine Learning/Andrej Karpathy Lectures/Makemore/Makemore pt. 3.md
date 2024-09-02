In Python, variables are passed to functions by reference. However, it's important to note that the behavior can seem like pass-by-value for immutable types (like integers, strings, and tuples) because you cannot change the original object. For mutable types (like lists, dictionaries, and sets), changes to the object within the function will affect the original object.

In deep learning, you will always have some idea of what loss value to expect from an initialized NN, because of the loss function and the problem you are solving.

In our example, the initialization is really bad because the loss is incredibly high and then quickly goes down. We would expect the following to be the initialized loss
```python
-torch.tensor(1/27).log()
```
which evaluates to *3.2958*

Where as we are seeing around *27* - this indicates that our initialized network is confidently wrong, assigning high probabilities to certain characters and lower ones to others

we want to avoid a graph of the loss over training to look like a hockey stick

`tanh` function is a squashing functon it takes arbitrary numbers and it squashes them into a range of negative one and one, and it does so smoothly. When computing the gradient at that layer of NN, it's equal to 1 -t^2 where t is the value of the function. So really big and really small inputs to tanh will cause this expression to evaluate t 0. This is a vanishing gradient. It creates dead neurons that will never be activated

kaiming normal - the most common way of initializing the weights of a neural network
		square root of dimensionality of fan_in (input to the network) multiplied by a "gain" that depends on the nonlinearity you're using
