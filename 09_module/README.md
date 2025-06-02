# Module 09: HSTU Recommender Engines

1. Briefly explain the performance between the DLRM and GR models. Would it make sense to only use GR models going forward or do traditional recommender models have justifiable use case? Explain and provide examples of such use cases.

Both of my models (i.e., the DLRM and GR models) performed relatively poorly.  I am not sure why this was the case.  This is the first assignment for which I have extensively used generative AI to code the models.  While I have read through the code and made corrections, I do believe that I don't understand the models as well as if I had coded them on my own.  Regardless, the GR certainly performed better.  But the GR model took more training time (indeed, I needed to train the GR model on dedicated, GPU-enabled remote server, even for this rather small dataset), although this seems to be different from what other researchers have found (Zhai et al 2024).  Regardless, traditional recommender algorithms certainly still have a place. They are more studied, understood, and interpretable, and for relatively small datasets, require less training time. As a result, for small applications or applications that do not need to scale or do not have new, streaming data, traditional recommender systems still have a role to play.

2. Explain and interpret the performance metrics between the DLRM and GR models that you created.

As mentioned in the previous response, both models performed relatively poorly across all the metrics, though the DLRM performed a magnitude of order worse across all metrics. This is to be expected, as the the GR explicitly considers sequential ordering of ranking that likely better captures users' own ratings patterns. 

Zhai, Jiaqi, Lucy Liao, Xing Liu, Yueming Wang, Rui Li, Xuan Cao, Leon Gao, et al. 2024. “Actions Speak Louder than Words: Trillion-Parameter Sequential Transducers for Generative Recommendations.” arXiv. https://doi.org/10.48550/arXiv.2402.17152.