# Critique

Chapter 8: Evaluating Recommendation Systems, in the recommender systems handbook covers various topics on RecSys evaluation. It is possible to divide the text in two sections. The first describes different types of experimentation: offline, user studies, and online. The last section discusses a set of properties that should be considered on a system evaluation. I will present my overall opinion and thoughts of the entire reading, and a general critique.

Generally I appreciate how careful each topic was addressed. By careful I mean that every time an evaluation strategy or approach was presented, the authors also considered any bias they could introduce, they stated all the precautions on the assumptions being made, and more. This delivers deep insight on the topics discussed and how a decision on system evaluations most of the time has collateral effects to consider (trade-offs). Also, this ideas that compliment what the authors are explaining come from different domains like psychology, statistics, regarding the systems capacity, and economical perspectives. Some quotes that support my opinion are the following:
  
About user studies. Insights given by psychological analysis:

  > However, even when the subjects represent properly the true population of users, the results can still be biased because they are aware that they are participating in an experiment. For example, it is well known that paid subjects tend to try and satisfy the person or company conducting the experiment. If the subjects are aware of the hypothesis that is tested they may unconsciously provide evidence that supports it.

  > When presenting several results to the subject, the results can be displayed either sequentially, or together. In both cases there are certain biases that we need to correct for. When presenting the results sequentially the previously observed results influence the user opinion of the current results. For example, if the results that were displayed first seem inappropriate, the results displayed afterwards may seem better than they actually are. When presenting two sets of results, there can be certain biases due to location. For example, users from many cultures tend to observe results left to right and top to bottom. Thus, the user may observe the results displayed on top as superior.


About online experiments. Insights given by economical/utilitarian aspects:

> Online evaluations are unique in that they allow direct measurement of overall system goals, such as long-term profit or user retention.

> For example, it is tempting to use money as a utility thus selecting a recommender that minimizes user cost. How- ever, under the diminishing returns assumption [56], the same amount of money does not have the same utility for people with different income levels. Therefore, the average cost per purchase, for example, is not a reasonable aggregation across users.

Subtleties worth pointing out:

- On User preference systems A/B comparison:

  > It may also be the case that users who preferred system A, only slightly preferred it, while users who preferred B, had a very low opinion of A. In this case, even if more users preferred A we may still wish to choose B. To measure this we need non-binary answers for the preference question in the user study. Then, the problem of calibrating scores across users arises.

- On using a reference ranking:

  > In cases where we only have usage data, it may be appropriate to construct a reference ranking where items used by the user are ranked above unused items. However, this is only valid if we know that the user was aware of the unused items, so that we can infer that the user actually preferred the used items to the unused items.


As a critique I would say that the main virtue of the article can also be its main flaw. That is how broad it is in terms of the topics discussed and that its fields of study are from different disciplines. For the readers that may want to go further in the topics presented, the reading can be considered as a "jack of all trades, master on none". Is nice to have a multidisciplinary approach to analyze RecSys evaluation methods but some topics from other domains were to specific (e.g. the psychology to the user). Addressing such a different topic from technical RecSys analysis can work as a double edged sword. Either these topics are included superficially in aid for it to be understandable for everybody, or in a more specific rigourous way at the cost that some readers won't understand.