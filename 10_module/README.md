1. How is retrieval latency impacted by two-tower models vs. interaction-based (single-tower) models?

A two-tower model uses two separate deep-neural networks, one for embeddings of users and one for embeddings of items, with both of the embeddings existing in the same dimensional space. These embeddings can be precomputed offline and then used as needed to generate possible recommendations using the very fast cosine similarity. This reduced latency is especially evident in the case when the catalog of items is very large. This approach also scales quite well (Huang 2013).  But there is a tradeoff: a naive two-tower model cannot offer as nuanced recommendations since interaction between the two towers is not incorporated into the training (Yu 2021).

2. What types of features (dense, sparse) are ideal for sharding, and why?

Sparse features are often more ideal for sharding since there is less transfer time and and joining time, but it is also important to have a good partitioning strategy based on the sparsity patterns to ensure equal and efficient partitioning into the shards. Sparse features are often the result of categorical variables, and so care should be taken to make sure the distributions of these variables lead to balanced partitions.   Dense features, often from continuous variables, can be effectively sharded based on ranges or appropriate hashes functions, ensuring a good distribution across shards.

Huang, Po-Sen, Xiaodong He, Jianfeng Gao, Li Deng, Alex Acero, and Larry Heck. 2013. “Learning Deep Structured Semantic Models for Web Search Using Clickthrough Data.” In Proceedings of the 22nd ACM International Conference on Information & Knowledge Management, 2333–38. San Francisco California USA: ACM. https://doi.org/10.1145/2505515.2505665.

Yantao Yu, Weipeng Wang, Zhoutian Feng, and Daiyue Xue. 2021. “A Dual Augmented Two-Tower Model for Online Large-Scale Recommendation.” DLP-KDD, 1122445.1122456. https://doi.org/10.1145/1122445.1122456.