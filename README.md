# unsupervised-machine-learning
Course Project for DLBDSMLUSL01: Machine Learning – Unsupervised Learning and Feature Engineering

# Document Clustering and Visualization

This project explores the clustering and visualization of a large textual dataset, focusing on scientific abstracts. It applies advanced text preprocessing, feature engineering, clustering, and dimensionality reduction techniques to uncover patterns and insights in the data.

## Table of Contents
- [Overview](#overview)
- [Techniques Used](#techniques-used)
- [Steps](#steps)
  - [1. Preprocessing and Feature Engineering](#1-preprocessing-and-feature-engineering)
  - [2. Clustering](#2-clustering)
  - [3. Topic Modeling](#3-topic-modeling)
  - [4. Dimensionality Reduction](#4-dimensionality-reduction)
- [Results](#results)
- [Conclusion](#conclusion)

## Overview
This project focuses on:
- Extracting semantic insights from textual data (scientific abstracts).
- Grouping similar documents into clusters.
- Visualizing the high-dimensional data in a meaningful, reduced-dimensional space.

The dataset consists of 250,000 textual records, reduced to a subset for efficient processing.

## Techniques Used
The following techniques were employed:
- **TF-IDF Vectorization** for text representation.
- **K-Means Clustering** for grouping documents.
- **Latent Dirichlet Allocation (LDA)** for topic modeling.
- **Dimensionality Reduction** using Truncated SVD, UMAP, and t-SNE for visualization.

## Steps

### 1. Preprocessing and Feature Engineering
- **TF-IDF Vectorization**: Used to represent text numerically, with the following parameters:
  - Maximum vocabulary size: 5,000.
  - N-grams: Unigrams and bigrams.
  - Minimum document frequency: 2.
  - Maximum document frequency: 50%.
- **Sentence-BERT Embeddings**: Generated using the `all-MiniLM-L6-v2` model for dense, semantic-rich representations.

### 2. Clustering
- **K-Means Clustering**:
  - Applied to the TF-IDF matrix and Sentence-BERT embeddings.
  - Number of clusters (‘k’) was experimentally tuned.
  - Clusters were evaluated using silhouette scores and visualized with dimensionality reduction techniques.

### 3. Topic Modeling
- **Latent Dirichlet Allocation (LDA)**:
  - Number of topics: 10.
  - Extracted the most significant words for each topic.
  - Provided overlapping, semantic groupings of documents.

### 4. Dimensionality Reduction
Three methods were used to visualize high-dimensional data:
1. **Truncated SVD**: Reduced TF-IDF vectors to 2D for initial visualization.
3. **t-SNE**: Focused on local structure, showing tighter clusters but with potential global distortions.

## Results
- **Clustering**: K-Means produced identifiable clusters, though overlaps indicated room for improved feature representations.
- **Topic Modeling**: LDA revealed interpretable themes within the data.
- **Visualization**:
  - Truncated SVD showed overlapping clusters.
  - UMAP and t-SNE provided better-defined groupings.

### Example Visualizations
#### Truncated SVD
- Scatterplot showing overlapping clusters in a linear reduced space.

#### t-SNE
- Highly detailed local clustering with distinct groups.

## Conclusion
This project demonstrates the effectiveness of combining clustering, topic modeling, and dimensionality reduction for analyzing large-scale textual datasets. The results highlight:
- TF-IDF as a robust baseline for clustering.
- Sentence-BERT embeddings as a semantically rich alternative.
- UMAP and t-SNE as superior visualization tools for non-linear data structures.

Further refinements, such as testing alternative clustering methods (e.g., DBSCAN) or advanced embeddings, can enhance the interpretability and accuracy of the results.
