# Collaborative Filtering, k-nearest neighbors

For the code used to analyze the dataset, please see the [accompanying Jupyter notebook](./k_nearest_neighbors.ipynb).
 
1. In this module with MovieLens dataset, we predicted ratings. If user's predicted rating is low, then would you show it in your recommendation to the user? What can you do to address this issue?

If our RecSys model is accurate, then we likely should not show it to the user, since the prediction is that the user will not like the movie. But it could also be a good idea to show the recommendation to the user if we are placing high importance to diversity in recommendations.  Indeed, depending on the amount of user data on hand and the accuracy of the model, privileging only high ratings could create a bit of echo chamber and bias into the recommendations.  Having more comprehensive historical data on the user could help solve this issue.  A hybrid approach could also be possible, where collaborative filtering approaches are combined with the content-based approaches.

1. How do you find an optimal number of neighbors to pick for this model?

I did an elbow plot for a few different randomly selected users.  I looked to see when the RMSE reached a low point and the recommended movies remained relatively constant.  I was surprised how much of an effect this hyperparamater had on the  specific recommendations generated.

1. While RMSE is a measure we can use to compare whether predicted ratings match actual ratings and see improvements after adding new features, it is not a robust metric for recommender systems. What are couple of limitations of using RMSE to evaluate recommender systems.

Due to its formulation (i.e., it is **squared** error, even with the root taken at the end), RMSE would, all else being equal, prefer a RecSys that has several incorrect (though relatively small) errors rather than RecSys that had only one large error.  But in this case, it's intuitive to prefer the system that accurately predicted most ratings, but simply got one or two (badly) wrong.  Moreover, since it is always a positive number (i.e., a magnitude, similar to the absolute difference), it cannot capture the direction of error.  In some settings, taking into account the direction of error might be helpful and appropriate (e.g., when ratings are negative to positive).  RMSE also cannot readily account for implicit feedback (e.g., in the forms of site visits or clicks) since implicit feedback is unary data.


### References
 * Aggarwal, Charu C. 2016. _Recommender Systems: The Textbook_. Cham: Springer. https://doi.org/10.1007/978-3-319-29659-3. Work through this alongside the course textbook.
 * Falk, Kim. 2019. _Practical Recommender Systems_. Shelter Island, NY: Manning.
 * Li, Dongsheng, Jianxun Lian, Le Zhang, Kan Ren, Tun Lu, Tao Wu, and Xing Xie. 2024. _Recommender Systems: Frontiers and Practices_. Singapore: Springer Nature Singapore. https://doi.org/10.1007/978-981-99-8964-5. 
 * Ricci, Francesco, Lior Rokach, and Bracha Shapira, eds. 2022. _Recommender Systems Handbook_. New York, NY: Springer US. https://doi.org/10.1007/978-1-0716-2197-4.