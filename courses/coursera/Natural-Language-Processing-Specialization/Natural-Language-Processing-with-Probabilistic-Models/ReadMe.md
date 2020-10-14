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
