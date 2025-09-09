# Recommendation Systems

Recommendation systems are algorithms designed to suggest relevant items to users. Here are the main types:

## 1. Popularity-Based Recommendations
- **Approach**: Recommends the most popular items based on overall user interactions (e.g., top-rated, most-viewed).
- **Pros**: No cold start problem, easy to implement.
- **Cons**: Less personalized, may not cater to niche interests.

## 2. Content-Based Recommendations
- **Approach**: Recommends items similar to those a user has liked in the past, based on item attributes (e.g., genre, director, actors).
- **Pros**: No cold start for new items, personalized to user preferences.
- **Cons**: Limited by the quality and availability of item attributes.

## 3. Collaborative Filtering
- **Approach**: Recommends items based on the behavior of similar users.
  - *User-Based*: Finds users with similar tastes and recommends items they liked.
  - *Item-Based*: Recommends items similar to those a user has liked.
- **Pros**: Can capture complex user patterns, no need for item attributes.
- **Cons**: Cold start problem for new users/items, scalability issues with large datasets.

## 4. Hybrid Systems
- **Approach**: Combines multiple techniques (e.g., collaborative + content-based) to enhance accuracy and overcome individual limitations.
- **Benefits**: Better overall performance, reduced cold start issues, and more robust recommendations.


# 📊 Recommendation System Approaches

| Type                  | How It Works                                      | Typical Implementation                         | Libraries / Functions |
|-----------------------|---------------------------------------------------|-----------------------------------------------|-----------------------|
| **Popularity-Based**  | Recommend top-N most popular items overall.        | Simple `groupby` + count or mean rating.       | pandas (`groupby`, `sort_values`) |
| **Content-Based**     | Recommend items similar to those the user liked, based on attributes/features. | Build item feature vectors → compute similarity → KNN search. | scikit-learn (`NearestNeighbors`), cosine similarity |
| **Collaborative Filtering** | Recommend based on user–item interactions (latent factors). | Matrix factorization: SVD, SVD++ (user/item embeddings). | Surprise (`SVD`, `SVD++`), ALS (implicit library) |
| **Hybrid**            | Combine multiple approaches for better accuracy.  | Popularity + Content + Collaborative in ensemble or weighted scheme. | Custom pipeline, hybrid logic |
