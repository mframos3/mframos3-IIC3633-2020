# Critique

The article "Document Clustering Based On Non-negative Matrix Factorization" presents a document clustering method that yields much more straightforward results in comparison to other methods based on SVD due to the configuration of the semantic space in which the clusters are set.

The idea behind the work of Wei Xu, Xin Liu and Yihong Gong is to project the document corpus into a k-dimensional semantic space in which each axis corresponds to a particular topic. Then, each document can be represented as a linear combination of the topics. Some topics are related to others so in order to maintain the association between axes and topics, there is no constraint for the axes to be orthogonal to each other. This configuration of the semantic space only needs positive values to represent the documents as it is more natural to represent them as an addition, and not substraction, of several topics.

The reason why it is more straightforward to build the semantic space this way is because it is direct to assign a document to a cluster by just calculating the projection of it on every axis and select the axis that maximizes its value. As the axis represents a topic, it is then assigned to the document and clusters of topics can be built this way with no additional operations. Other methods do not have such direct indication of the partitions so it is necessary to apply additional operations to assign the document to a cluster.

There are two ideas I want to share after reading this article:

- As the proposed method sets an axis for each topic, and some of them can be constructed by a linear combination of others (they are not orthogonal) it is natural to think if there is any relevant addition of cost to the calculations as the space
is being constructed with more axes than its basis. What would happen in a situation where the topics are so related between each other that the amount of extra linearly dependant axes is much greater than size of the basis of that space? The complexity of the method is linear to the amount of topics but it is not clear if the relationships between topics has an impact on performance. This is important as the main virtue of the construction of the semantic space it is performance related.

- The document clustering problem is developed over a simple document characterization based on word frequencies. There are far more dimensions to consider on text classification such as the position of a word in the sentence, the relationship between words, and the importance of each word for the task. For instance, in [1] the exclusivity of words is consider relevant for this analysis. The article "introduces a model which infers estimates of the differential use of words across topics as well as their frequency within topics". This is one example of how broad is the field of text analysis that  could be helpful to characterize any given document. Also context is something that is being captured my NLP models for classification and clustering. In [2] ELMo and BERT word embedding methods are used to classify and cluster topic-dependent arguments (Argument mining). Considering all research on this topics, it may be possible to redesign the strategy of the Non-negative matrix factorization for document clustering with a deeper document characterization that may take in account more aspects than just word frequency.

## References

[1] Bischof, J., & Airoldi, E. (2012). Summarizing topical content with word frequency and exclusivity. <https://icml.cc/2012/papers/113.pdf>

[2] Reimers, N., Schiller, B., Beck, T., Daxenberger, J., Stab, C., & Gurevych, I. Classification and Clustering of Arguments with Contextualized Word Embeddings. <https://arxiv.org/pdf/1906.09821.pdf>

