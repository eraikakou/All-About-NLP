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

#### Word Embedding Methods

![image](https://user-images.githubusercontent.com/28102493/96025120-0000e600-0e55-11eb-8700-1667870733d9.png)
![image](https://user-images.githubusercontent.com/28102493/96025159-0beca800-0e55-11eb-9d56-92454dca4516.png)


Here are a few well established methods that you can use to generate word embeddings:

1. **Word2vec by Google**, which initially popularized the use of machine learning, to generate word embeddings. Word2vec, uses a shallow neural network to learn word embeddings. It proposes two model architectures: 

     1. **continuous bag of words**, which is a simple but efficient approach that you will implement this week. The objective of the model is to learn to predict a missing word given the surrounding words. 

     1. **Continuous skip-gram**, also known as the skip-gram with negative sampling, which does the reverse of the continuous bag of words method. The model learns to predict the word surrounding a given input word. 
 
 1. **Global vectors or glove by Stanford,** which involves factorizing the logarithm of the corpuses word co-occurrence matrix, which is similar to the counter matrix you've used before. 
 
1. **fastText by Facebook,** which is based on the skip-gram model and takes into account the structure of words by representing words as an n-gram of characters. This enables the model to support previously unseen words, known as outer vocabulary words, by inferring their embedding from the sequence of characters they are made of and the corresponding sequences that it was initially trained on. For example, it would create similar embeddings for kitty and kitten, even if it had never seen the word kitty before. As kitty and kitten are made of similar sequences of characters. Another benefit of fastText, is that word embedding vectors can be averaged together to make vector representations of phrases and sentences. 

1. Next up, some **more sophisticated modeling approaches**. These methods use advanced deep neural network architectures, to refine the representation of the words meaning according to their contexts. In the previous models a given word always has the same embedding. In these more advanced models, the words have different embeddings depending on their context. This adds supports for polysemy or words with similar meanings. Such as the word plants, which can refer to an organism like a flower, a factory or which can be an adverb, with yet more different meanings. A few examples of advanced models that generate word embeddings are:

   1. **BERT** or bidirectional encoder representations from transformers by Google, 
   1. **ELMO** for embeddings from language models, by the Allen Institute for AI or 
   1. **GPT-2** or generative pre-training 2 by Open AI.

If you want to use these advanced methods, you can find off the shelf pre-trained models on the Internet. You can fine tune these models using your own corpus to generate high-quality, domain, specific word embeddings.
