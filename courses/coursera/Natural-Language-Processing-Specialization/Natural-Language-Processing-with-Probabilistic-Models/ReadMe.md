# Word vectors / Word Embeddings

## Several Representations

1. Integers
1. One Hot Vectors
1. Word Embeddings

### One Hot Vectors

**Limitations:**

1. Huge sparse Vector: Space and processing times

1. Don't capture meaning: Another limitation is that this representation doesn't carry the word's meaning. For instance, if you attempt to determine how similar two words are by calculating the distance between their one-hot vectors, then you will always get the same distance between any two pairs of words. 

![image](https://user-images.githubusercontent.com/28102493/96021984-7e0ebe00-0e50-11eb-8d11-f621c65df0ae.png)

### Word Embeddings

Word Embeddings are vectors that's carrying meaning.

Word embeddings represent words in a vector form that's both has a relatively low dimension saying the hundreds to load thousands. Making it practical for calculations and carries the meaning of words, making it possible to determine how semantically closed words are.

![image](https://user-images.githubusercontent.com/28102493/96022636-71d73080-0e51-11eb-97ab-8efa2b7bc64d.png)

![image](https://user-images.githubusercontent.com/28102493/96022764-a4812900-0e51-11eb-9c02-75608ea08ef1.png)

#### Create Word Embeddings

To create word embeddings you always need two things: 
 
 1. A **corpus of text**
 1. and an **embedding method**.
 
 ![image](https://user-images.githubusercontent.com/28102493/96024006-81f00f80-0e53-11eb-8413-36886a444c9b.png)

The context is important as this is what will give meaning to each word embedding, a simple vocabulary list of Shakespeare's most common words would not be enough to create embeddings. 

##### Corpus

The corpus would be a general purpose sets of documents such as Wikipedia articles or it could be more specialized such as an industry or enterprise specific corpus to capture the nuances of the context. For NLP use cases on legal topics, you could use contracts and law books as the corpus. 

##### Embedding method 

The embedding method creates the word embeddings from the corpus. There are many types of possible methods. But in this course, I will focus on modern methods based on machine learning models which are set to learn the word embeddings. The machine learning model performs a learning task and the main byproducts of this task are the word embeddings. For instance the task would be to learn to predict a word based on the surrounding words in a sentence of the corpus, as in the case of the continuous bag of words approach that I will describe in the next videos that you will implement this week. The specific of the tasks are what will ultimately define the meaning of the individual words. I'll get back to this in one of the next videos. The task is said to be self supervised. It is both unsupervised in the sense that the input data, the corpus, is unlabeled. And supervised in the sense that the data itself provides the necessary context which would ordinarily make up the labels. So the corpus is a self-contained data set that contains both, the training data and the data that enables the supervision of the task. 

##### Hyperparameters

Word embeddings can be tuned by a number of hyperparameters. Just like in any machine learning model. One of these hyperparameters is the dimension of the word embedding vectors. In practice this dimension typically ranges from a few hundred to the low thousands. Using higher dimensions captures more nuanced meanings, but is more computationally expensive both as training time and later down the line when using the word embedding vectors. This eventually leads to diminishing returns. 

##### Transformation

Finally, to feed the corpus into the machine learning model the contents of the corpus must first be transformed into a suitable mathematical representation from words into numbers. The representation depends on the specifics of the model, but it is usually based on the simple representations that I presented in the previous video, such as integer based word indices or one hot vectors. In this video you learned about high level process to create context embeddings.
