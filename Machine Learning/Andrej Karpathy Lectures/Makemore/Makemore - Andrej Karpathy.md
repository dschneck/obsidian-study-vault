Link to the [video](https://www.youtube.com/watch?v=PaCmpygFfXo)

character level language mode - treating each name  in the training data as a sequence of individual characters

each example in the dataset demonstrates explicit rules for the probability of seeing a character given it's location. For example, the word "isabella" in the dataset would suggest that the model learn that 'i' is likely to begin a name and 's' is likely to come after it, etc. Actually, to really encode this with the bigram model then we need to introduce 2 new "characters" that will represent the start and end of a name, characters that will be treated just like the rest of the letters in the alphabet. Start - "<S>" and End - "<E>"


need to learn broadcasting and tensor operations

A tensor with shape `[27]` is a 1-dimensional tensor (vector) containing 27 elements. It has only one dimension, and its size along that dimension is 27.

A tensor with shape `[27, 1]` is a 2-dimensional tensor (matrix) with 27 rows and 1 column. It has two dimensions: the first dimension (rows) has a size of 27, and the second dimension (columns) has a size of 1. This structure allows it to represent column vectors explicitly in contexts where the distinction between a 1D array and a 2D column vector is important, such as in matrix operations.

For example, in a 2D tensor (like a matrix), summing over [`dim=0`] collapses the 
rows (sums vertically), producing a 1D tensor where each element is the sum of the corresponding column. Summing over [`dim=1`] collapses the columns (sums horizontally), producing a 1D tensor where each element is the sum of the corresponding row.

we can compute the likelihood of a name by multiplying the probabilities of the individual bigrams in the name. In the model we've constructed, given that we computed the probabilities through raw count / total for each row, there indeed some probabilites that are 0 - which is not desirable as it blows up our log likelihoodu

to fix the above we can do something called model smoothing, in this example it would be adding a counts for everything, such that nothing is 0