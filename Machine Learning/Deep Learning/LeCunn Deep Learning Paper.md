[Link](https://www.cs.toronto.edu/~hinton/absps/NatureDeepReview.pdf) to paper.

***"Deep learning allows computational models that are composed of multiple processing layers to learn representations of data with multiple levels of abstraction."***

***"The key aspect of deep learning is that
these layers of features are not designed by human engineers: they
are learned from data using a general-purpose learning procedure"***


***A linear classifier, or any other ‘shallow’ classifier operating on raw pixels could not possibly distinguish the latter two (samoyed dog and white wolf), while putting
the former two in the same category. This is why shallow classifiers
require a good feature extractor that solves the selectivity–invariance
dilemma — one that produces representations that are selective to
the aspects of the image that are important for discrimination, but
that are invariant to irrelevant aspects such as the pose of the animal.
To make classifiers more powerful, one can use generic non-linear
features, as with kernel methods, but generic features such as those
arising with the Gaussian kernel do not allow the learner to general-
ize well far from the training examples. The conventional option is
to hand design good feature extractors, which requires a consider-
able amount of engineering skill and domain expertise. But this can
all be avoided if good features can be learned automatically using a
general-purpose learning procedure. This is the key advantage of
deep learning.***

For smaller data sets,
unsupervised pre-training helps to prevent overfitting40, leading to
significantly better generalization when the number of labelled exam-
ples is small, or in a transfer setting where we have lots of examples
for some ‘source’ tasks but very few for some ‘target’ tasks. Once deep
learning had been rehabilitated, it turned out that the pre-training
stage was only needed for small data sets.