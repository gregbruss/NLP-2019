# NLP-2019
Project for Natural Language Processing 2019.

# The analogy space of a word embedding
![alt text](https://nlp.stanford.edu/projects/glove/images/comparative_superlative.jpg "Visualizing the glove embedding across analogical relationships, GloVe, 2014")


## Evaluating Word Embeddings using Analogies

### Motivation:
Word embeddings and distributed representations present a powerful way of completing many NLP tasks, and capture fine-grained semantic and syntactic regularities. In this work, I evaluate the distributional space of these embeddings using a well-known analogy task over multiple categories with comparison to a human baseline, and find that performance is highly dependent on the category. An introduction to Global Vectors is also presented, and the analogy task is presented along with a complete implementation.

### Categorical Analogy Dataset
For this task, different categories of analogies were used, and were sourced from the Bigger Analogy Test Set (Gladkova, 2016). The reason for this is that multiple different categories encode different types of semantic relations, and measuring performance on these cross-representational tasks should give insight into the semantic space.The categories were chosen specifically to encode different types of relations. Furthermore, the Bigger Analogy Test Set has been designed to be balanced and representative, in that it covers both derivational morphology and encyclopaedic semantics - analogies that require knowledge about the world. Care has also been taken to reduce homonyms in the dataset - words which have the same sound but different meaning, such as the word "bat" which can be both a winged animal, and a wooden club used in baseball.

The analogy categories chosen for this paper were:

_Country/Capital_: A standard analogy such as “London is to England as Paris is to France"

_Present/Past Verb_: A present test verb form along with its past tense form, such as “Do is to did, as go is to went”

_Adjective/Superlative_: An adjective followed by its superlative form, such as “Big is to Biggest as Strong is to Strongest”.
\section{Model Architecture}
A pre-trained, 50 dimensional GloVe word embedding was used for this task, which was trained on 6 billion tokens from the Wikipedia 2014 dataset. In extensions of this work, one could use different sized embeddings and see how performance differs. A 300-dimensional embedding trained on 42 billion tokens is available. Some tests were run with it, but the computational overhead was too large for this project.

### Issues with Analogy Finding
The overall centrality of cosine similarity in this task is potentially a point of concern, in that it may be the case that the method is evaluating not just linguistic regularity but actually the local neighborhood of the x vector:
\(x = a^*-a+b\)
