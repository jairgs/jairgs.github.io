---
title: "Why use matrix factorization?"
excerpt: "The other day I was asked what are the advantages of using matrix factorization and in particular what are the advantages of doing dimensionality reduction in machine learning."
toc: true
toc_sticky: true
header:
  overlay_image: https://cdn.pixabay.com/photo/2020/01/11/14/10/factory-4757647_1280.jpg
  caption: "Photo by Pixabay"
tags: 
  - Machine Learning 
  - Data Science 
  - Feature Engineering
  - Dimensionality Reduction
---

The other day I was asked what are the advantages of using matrix factorization and in particular what are the advantages of doing dimensionality reduction in machine learning.  
In this entry I discuss briefly the whys and some of it's applications.

## Advantages of matrix factorization  
Latent variables representation: to represent the data as each column and each observation having a weight for several latent variables.  
$$U^TM \approx R$$  
where M is of dimensions rows x latent variables and U is of dimensions columns x latent variables. R approximates the original matrix. 
R can be interpreted in product recommendation as rows=people and columns= movies. And the latent variables are factors such as movie sadness, genre, some actors staring etc.

![recommender](/assets/postsImages/recommend.PNG  "Recommender System")

Dimensionality reduction such as in text features where you usually have a very large sparse matrix. 

## Why or when use matrix factorization
Computation time. This is one of the main reasons why you would want to use matrix factorization in highly dimensional datasets. 
Recommender systems for estimation.
Many different representations of the data, reduce and then concatenate. This can be interpreted as a model itself or a naive way of doing ensembling.

![append](/assets/postsImages/append.PNG  "Append many features of different techniques")

Many different representations of the data but then use ensembling
Matrix factorization on transformed data (e.g. log) can give new good features. 

![features](/assets/postsImages/features.PNG  "Feature Engineering")

## Algorithms
- SVD and PCA. Standard matrix factorizations. 
- Truncated SVD. Good for sparse matrices. 
- Non Negative matrix factorization. Good for counts.

## Final remarks
- Use the number of latent variables as a hyperparameter (to be tuned).
- Apply matrix factorization to all data including train and test together before split.


