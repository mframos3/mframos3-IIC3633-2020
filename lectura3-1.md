# Critique

The article "Performance of Recommender Algorithms on Top-N Recommendation Tasks" presents different alternatives to standard RMSE/MAE based recommender algorithms in the task of selecting top-N items for an user in the system. The following excerpt, in my opinion, reflects the main argument of the article:

    This work shows, through an extensive empirical study, that the convenient assumption that an error metric such as RMSE can serve as good proxy for top-N accuracy is questionable at best.

The questionable assumption of using error metrics for top-N accuracy is the main motivation behind the study, that derived on reformulations of standard neighborhood and latent factors models. This reformulations are focused on adapting the models for top-N recommendations based on accuracy instead of an error metric. First, the authors proposed a testing methodology. Basically, the dataset is split into training and test sets. The test set corresponds to 5-star rated items by an user u paired with 1000 unrated items by u. The model is trained with the training dataset and predictions are made for the items in the test set. The subset of 1001 items (the 5-star rated item + 1000 unrated items) is ordered by predicted rating of its items. The top-N items of this subset are selected. If the 5-star rated item is in the top-N selection, it is registered as a hit. If not, it is registered as a miss. As this methodology outputs number of hits and misses, recall and precision metrics can be defined.

Afterwards, neighborhood models and latent factor models where modified in order to suit the testing methodology previously mentioned. In this context, the models had more flexibility on item ranking as there is no need to output exact rating predictions but just a score that reflects user preference to the item. In this manner, the authors proposed a neighborhood and latent factor models named Non-Normalized Cosine Neighborhood (item-item) and a PureSVD respectively.

Later, this models were compared to non-personalized methods and traditional neighborhood and latent factor models on two datasets in two variations each. This variations were the inclusion/exclusion of the 2% most popular items which affected the novelty of the recommendations. Relevant findings were that in the case of not considering the 2% most popular items, the Top Popular non-personalized algorithm performed better than expected, outperforming personalized RMSE based models. Both by including and exluding the 2%, SVD++ was the best RMSE based model out of all. PureSVD model proposed by the authors got the best results across all tests.

As positive aspects of this article, I want to point out the following:

- The distribution of the dataset was thoroughly discussed and analyzed. It turned out that it was of extreme relevance for the results analysis. This aspect was included on the experiments by the inclusion/exclusion of the 2% mentioned before. This led to explanations on why TopPop had good accuracy (but including trivial reccomendations) and it showed that more latent factors were needed on the exclusion of the top 2%. The interpretation the authors give to this effect is that *"the first latent factors capture properties of the most popular items, while the additional latent factors represent more refined features related to unpopular items."*.
  
- The experimentation with two datasets increases confidence of the results obtained. As the same behavior was observed on both datasets, it communicates that the results do not depend on a specific dataset and it is possible to replicate the same effects on other contexts.
  
- The selection of models for comparison analysis was diverse. It included non-personalized and personalized models, neighborhood and latent factor models and error based and accuracy based models. This varied selection of comparisons for benchmarking reinforces the fact that their proposed models are better than common recommendation algorithms.
  
As a critique I want to point out the following:

- The entire proposal was based strongly on their testing methodology. This methodology was far from a generic, standard and "universal" way of defining the accuracy metric. It feels that is extremely particular and elaborate. We could question every step of the methodology and find no answer. Why making a test set of only 5-star ratings? Why did they grouped each 5-star ratings with 1000 non rated items?.

- Behind the testing methodology there still is some reminiscence of "regression" like characteristics found in error based models on the prediction of ratings. An estimation of the ratings is made on step 2, then a N parameter functions as a threshold that "cuts" the 1001 item batches to finally output a "hit" or "miss". It does not have much "classification" characteristics that would elicit the need of accuracy metrics.

- Classification metrics are being used (recall and precision), but it is not clear in this methodology what cases correspond to true negatives and false positives. It is only mentioned hit (true positive) or miss (false positive). So if we want to incorporate more metrics like specificity, false positive rate or others it is not clear how should we calculate them by using this methodology. The methodology is limited in this sense as it does not let further "classification" like analysis.






