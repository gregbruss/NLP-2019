# NLP-2019
Project for Natural Language Processing 2019.

#### Installation
    pip install mxnet
    pip install numpy
    pip install gluon
    pip install matplotlib

# The analogy space of a word embedding
![alt text](https://nlp.stanford.edu/projects/glove/images/comparative_superlative.jpg "Visualizing the glove embedding across analogical relationships, GloVe, 2014")

                  Figure 1: "Visualizing the glove embedding across analogical relationships, GloVe, 2014"



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

### Characteristics of the Bigger Analogy Test Set
Bats is:

### balanced and representative
BATS covers inflectional and derivational morphology, and lexicographic and encyclopedic semantics. Each relation is represented with 10 categories, and each category contains 50 unique word pairs. This makes for 99,200 [3] questions for the vector offset method.
### reduced homonymy:
the morphological categories were sampled to reduce homonymy. For example, for verb present tense the Google set includes pairs like walk:walks, which could be both verbs and nouns.
multiple correct answers where applicable. For example, both mammal and canine are hypernyms of dog. In some cases alternative spellings are listed (e.g. organize: reorganize/reorganise).

### Other work on BATS: 
![alt text](http://vecto.space/assets/img/bats_stats.png "BATS Performance, Gladkova 2015")


### Future work
This work has presented a complete implementation of the analogy finding task over multiple categories for a pre-trained word embedding, and evaluated the results in comparison to a human baseline. It was shown that human beings completely outperform this model, but that the model does a fairly good job given the fact that random guessing would almost certainly produce no correct answers. Issues of general evaluation of semantic spaces was discussed, as well as potential markers of bias in the space - namely the distance bias introduced by the prominent role of cosine similarity.

Future work should look into quantitative evaluation of how the performance gap changes as we increase the size of the word vector, perhaps from 50-dimensional to 300-dimensional.

#### For figure information, see:
GloVe models: https://nlp.stanford.edu/projects/glove/
[1] Pennington, J., Socher, R., & Manning, C. (2014). Glove: Global vectors for word representation. In Proceedings of the 2014 conference on empirical methods in natural language processing (EMNLP) (pp. 1532-1543).

http://vecto.space/projects/BATS/



