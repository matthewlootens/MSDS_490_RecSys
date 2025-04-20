## Similarity Measures

For the code used to analyze the dataset, please see the [accompanying Jupyter notebook](./similarity_measures.ipynb).


1. What do the averages of the different similarity methods mean for this dataset (e.g.: are smaller or larger averages better)?
   
All three measures indicate the degree to which two users are similar based on information of their movie ratings.  The Jaccard measure exists in $[0, 1]$, with values closer to $1$ indicating a higher similarity.  Cosine similarity exists in $[-1, 1]$, but since since all ratings are positive in this dataset, the cosine similarity measures exit in $[0, 1]$. As with Jaccard similarity, measures closer to $1$ indicate more similar users. Pearson similarity is centered and adjusted for the variance of both sets of users, and it exists in $[-1, 1]$, and expresses the linear relationship between two users.  Ratings closer to $1$ indicate positively associated users, while values closer to $-1$ indicate users that are negatively correlated.

I have calculated average similarity measures for both raw and mean-centered data, both the original dataset and with missing values imputed. As can be seen in the Jupyter notebook, these have differing effects of the average values.

2. Which similarity method would you use in this case?

In this case I would use cosine similarity, but with normalized data.  Normalization will account for differing ways that users tend to rate and make the comparisons between users more meaningful.  It will also allow for negative similarity values, which will help to identify users that are dissimilar (i.e., the angle is more that 90 degrees and thus the vectors form an obtuse angle).

3. Is it better to normalize data for this dataset?
Yes, it is better to normalize the data for this dataset. Normalization helps to reduce the impact of outliers and makes the data more comparable across different users and items. This can lead to more accurate similarity calculations and recommendations. This is especially the case for cosine similarity, we are only measuring the angles, and thus a user rating two movies at 1 would have the same cosine similarity as that of a user rating two movies at 5 (Falk 2019, 160). In general, mean-centering can help to account for differences in how users rate (i.e., some users tend to rate higher overall, and some tend to rate lower overall). 

### References
 * Aggarwal, Charu C. 2016. _Recommender Systems: The Textbook_. Cham: Springer. https://doi.org/10.1007/978-3-319-29659-3. Work through this alongside the course textbook.
 * Falk, Kim. 2019. _Practical Recommender Systems_. Shelter Island, NY: Manning.
 * Li, Dongsheng, Jianxun Lian, Le Zhang, Kan Ren, Tun Lu, Tao Wu, and Xing Xie. 2024. _Recommender Systems: Frontiers and Practices_. Singapore: Springer Nature Singapore. https://doi.org/10.1007/978-981-99-8964-5. 
 * Ricci, Francesco, Lior Rokach, and Bracha Shapira, eds. 2022. _Recommender Systems Handbook_. New York, NY: Springer US. https://doi.org/10.1007/978-1-0716-2197-4.