# Critique 2-2

In the article "Bayesian personalized ranking from implicit feedback" Rendle, S., Freudenthaler, C., Gantner, Z., & Schmidt-Thieme, L. (2009), a generic optimization criterion is presented for personalized ranking from implicit feedback. Traditional problem setting on recommender systems is to predict a preference score of an item for an user. This article uses a different approach where a total order relation is defined over the space of all item-item pairs. Then, training data is arranged in {user, item i, item j} triplets which indicate that the user prefers item i over j through the total order relation previously defined. This problem setting prevents asigning a same score to negative and unknown data.

Then a loss function is defined which is derived from the likelihood function of a bayesian posterior probability function. Together with this optimization criterion, a novel learning algorithm, LearnBPR, was presented. The convergence rate utilizing LearnBPR is significantly better in comparison to user-wise SGD. The optimization criterion with the learning algorithm was applied to MF and kNN models and compared to Weighted Regularized MF, SVD-MF, Cosine-kNN. As baselines a most-popular model was included and the theoretical upper bound on AUC for any non-personalized ranking method. The highest AUC values were obtained both by BPR-MF and BPR-kNN, indicating that the optimization criterion presented on the article outperforms previous optimization techniques.

I consider that this has been the best reading out of all so far. There are several things I want to highlight:

- The definition of the problem, the BPR optimization criterion, and the BPR learning algorithm were cleanly presented. The explanation was detailed but straightforward and held tight to the math and its formalities. As the authors were direct on this topics, it is required for the users to have a strong background in statistics in order to follow along.
  
- Different from all the articles previously read, the proposed technique was applied on different situations at a technical level and on an application level. In the technical aspect, the optimization criteria was used on different models to prove that their approach does not depend on a specific model and its benefits can be seen on several model classes. On the application level, the authors used two datasets which contain data of completely different contexts to guarantee that BPR is indifferent to its applications.

- Opossed to Simon Funk's SVD model tuning, this article presented a systematic, structured approach on hyperparameter tuning that gives more confidence to the fact that their settings are optimal.
  
- Last but not least, the incorporation of a theoretical upper bound for any non-personalized ranking method to their performance comparisons verifies that learning with BPR is indeed showing personalized results which are better than any non-personalized recommendation.
