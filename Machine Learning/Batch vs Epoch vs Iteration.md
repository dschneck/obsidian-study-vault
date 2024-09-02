Batch
	•	A batch is a subset of the entire dataset that is used to train the model during one forward and backward pass.
	•	Training on batches, as opposed to the entire dataset, allows for more efficient computation and faster convergence.
	•	The size of the batch, often referred to as batch size, is a hyperparameter that you can tune. Common batch sizes include powers of two, like 32, 64, 128, etc.
	•	Using a batch allows for stochastic gradient descent (SGD), where each update to the model’s parameters is based on a subset of the data, introducing variability and potentially helping escape local minima.
Epoch
	•	An epoch is a complete pass through the entire training dataset.
	•	During one epoch, the model sees each sample in the training set once.
	•	The number of epochs is a hyperparameter that you set, determining how many times the learning algorithm will work through the entire training dataset.
	•	Multiple epochs are typically needed to sufficiently train a model, as a single pass is usually not enough to achieve optimal performance.
Iteration
	•	An iteration is a single update of the model’s parameters.
	•	In the context of batch training, an iteration corresponds to using one batch of data to perform a forward pass, calculate the loss, perform a backward pass, and update the weights.
	•	The number of iterations per epoch is calculated as the total number of samples in the training dataset divided by the batch size. For example, if you have 10,000 samples and a batch size of 100, there will be 100 iterations per epoch.
Relationships
	•	Iteration: Each iteration processes one batch of data.
	•	Epoch: Each epoch consists of multiple iterations, covering the entire dataset.
	•	Batch Size: Determines the number of iterations per epoch.

Example
Suppose you have a dataset with 1,000 samples, a batch size of 100, and you train for 10 epochs:

	•	Batch: 100 samples processed per iteration.
	•	Iteration: 10 iterations per epoch (since 1000 \, \text{samples} / 100 \, \text{batch size} = 10 ).
	•	Epoch: 10 complete passes through the dataset.

Summary

	•	Batch: Small subset of data used to update the model.
	•	Iteration: One update of the model’s parameters using a batch.
	•	Epoch: One complete pass over the entire dataset.