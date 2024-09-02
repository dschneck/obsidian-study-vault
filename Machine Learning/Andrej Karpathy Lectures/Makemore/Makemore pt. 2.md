We can think of the C (embedding) matrix as the first layer of our NN. We start with the input (characters) that are then one-hot encoded. This is passed into NN or another way of saying it, we matrix multiple the C matrix with that one hot vector. However, becuase a one hot vector is all zeros for it's entires except for one that is 1, we are essentially just indexing into the C matrix. So, to make things more performant, we skip the matrix multiplication and just directly index C for the character we want

it is generally safe to say that when broadcasting, the dimension that aligns is effectively "squashed out" or reduced. This means that the aligned dimensions are used in the computation and do not appear in the resulting shape.

In Python, when you read a global variable within a function, you don't need to declare it as [`global`](vscode-file://vscode-app/Applications/Visual%20Studio%20Code.app/Contents/Resources/app/out/vs/code/electron-sandbox/workbench/workbench.html "Go to definition"). However, when you want to update a global variable within a function, you need to declare it as global

if I want a list and have a list, always think of list comprehension first

**.** **item() returns the value as a “standard Python number”, while the .****data attribute accesses the internal tensor with its value**

For building up intuition, it is best to start with the concepts of entropy and KL-divergence as defined by the [information theory](http://www.inference.org.uk/itprnn/book.pdf "www.inference.org.uk") and then find a connection to machine learning algorithms (which is what I suspect the OP is after)

Intuitively speaking, entropy is the average amount of “surprise” you get when obtaining samples from a distribution. A severely biased coin (say, in favor of tails) has low entropy because you can expect tails on almost every toss and are rarely “surpised” by a heads outcome. An unbiased coin has high entropy because you don’t have any “edge” in trying to predict a series of its outcomes, i.e. you have a steady rate of “surprise” upon seeing each new outcome.

Next, KL-divergence is a kind of difference between two probability distributions reduced to a single number (something that’s handy for the optimization part of machine learning).

Extending the intuitive definition of entropy above, KL-divergence D(P||Q) is the average amount of “surprise” you get when obtaining samples from the actual distribution P after having assumed that distribution to be Q. It can be shown to be always non-negative and zero only iff the two distributions are exactly the same (i.e. if your assumption is exactly right everywhere).

In the biased coin example, if you assumed the bias to be towards tails but it is actually towards heads, then both assumed and actual distribution entropies will be low but their “difference” (KL-divergence) will still be high — you expect tails but keep getting “surprised” by heads almost every time.

Thus, if you have two distributions, one fixed and the other having some parameters you can tweak, and you’re trying to make them as close to each other as possible, minimizing the KL-divergence is one option.